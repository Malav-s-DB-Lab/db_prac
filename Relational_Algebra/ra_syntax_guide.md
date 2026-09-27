# 📖 *RA* Relational Algebra Syntax & Operator Guide

> A comprehensive reference for the *RA* relational algebra interpreter developed by [Prof. Jun Yang](http://www.cs.duke.edu/~junyang/) at Duke University.

---

## 💡 Overview

*RA* is a relational algebra interpreter that translates relational algebra queries into SQL queries, then executes the SQL on an underlying relational database engine (SQLite by default).

### Basic Rules:
* The simplest relational algebra expression returns the contents of a single relation: just write `relName`.
* **Case-Insensitive**: Relation and attribute names are case-insensitive (e.g., `pizzeria` is identical to `PIZZERIA`).
* **Operator Prefix**: Every relational algebra operator starts with a backslash (`\`).
* **Whitespace & Formatting**: The syntax is insensitive to whitespace, and queries may span multiple lines. Comments start with `/* ... */` or `//`.

---

## 🍕 Database Context

This guide applies queries over the Pizzeria database schema:

```text
Person(name, age, gender)       // name is a key
Frequents(name, pizzeria)       // [name,pizzeria] is a key
Eats(name, pizza)               // [name,pizza] is a key
Serves(pizzeria, pizza, price)  // [pizzeria,pizza] is a key
```

📄 **[View Sample Data](pizza_data.md)**

---

## 🛠️ Relational Algebra Operators

| Operator | Syntax | Description | Example |
| :--- | :--- | :--- | :--- |
| **Selection** | `\select_{cond} R` | Filters rows in relation `R` satisfying condition `cond`. | `\select_{name='Amy' or name='Ben'} Person` |
| **Projection** | `\project_{attr_list} R` | Keeps only the specified attributes from `R`. | `\project_{pizza} (\select_{pizzeria='Applewood'} Serves)` |
| **Cross-Product** | `R1 \cross R2` | Cartesian product of all tuples in `R1` and `R2`. | `Person \cross Frequents` |
| **Natural Join** | `R1 \join R2` | Joins relations on identically named attributes. | `Person \join Frequents` |
| **Theta Join** | `R1 \join_{cond} R2` | Joins relations satisfying an explicit join condition. | `Person \join_{age>price} Serves` |
| **Set Union** | `R1 \union R2` | Returns tuples present in either `R1`, `R2`, or both. | `Person \union Person;` |
| **Set Difference** | `R1 \diff R2` | Returns tuples in `R1` that are not in `R2`. | `Person \diff Person;` |
| **Set Intersection** | `R1 \intersect R2` | Returns tuples present in both `R1` and `R2`. | `Person \intersect Person;` |
| **Renaming** | `\rename_{new_attrs} R` | Renames the attributes of relation `R`. | `\rename_{name1,age1,gender1} Person` |

---

## 🔍 Detailed Operator Examples

### 1. Selection (`\select_{cond}`)
Filters rows matching boolean conditions. Follows SQL boolean logic:
* String literals must be enclosed in single or double quotes (`'Amy'`, `"Dominos"`).
* Boolean operators: `and`, `or`, `not`.
* Comparison operators: `<=`, `<`, `=`, `>`, `>=`, `<>` (not equal).
```ra
\select_{gender='female' and age > 20} Person;
```

### 2. Projection (`\project_{attr_list}`)
Outputs only the specified list of attributes (eliminates duplicate rows automatically):
```ra
\project_{pizza, price} Serves;
```

### 3. Natural Join (`\join`)
Automatically matches and equates all attributes with the same name across two relations:
```ra
Person \join Frequents;
// Result schema: (name, age, gender, pizzeria)
```

### 4. Theta Join (`\join_{cond}`)
Joins two relations using an arbitrary comparison condition:
```ra
Person \join_{age > price} Serves;
```

### 5. Set Operators (`\union`, `\diff`, `\intersect`)
Computes mathematical set operations:
```ra
// All people who eat mushroom pizza diff people who eat pepperoni pizza
(\project_{name} (Person \join (\select_{pizza='mushroom'} Eats)))
\diff
(\project_{name} (Person \join (\select_{pizza='pepperoni'} Eats)));
```

> ⚠️ **Warning on Set Operators**: *RA* allows set operations on any two subexpressions that have the same **number** of attributes, even if their names differ. For clear and unambiguous results, use `\rename` to match schemas before using `\union`, `\diff`, or `\intersect`.

### 6. Renaming (`\rename_{new_attr_names}`)
Renames attributes sequentially. Essential when performing self-joins or cross-products to avoid attribute name collisions:
```ra
\rename_{name1, age1, gender1} Person 
\cross 
\rename_{name2, age2, gender2} Person;
```

---

## 🧩 Complex Query Example

**Question**: *Find all pizzas eaten by at least one person who does not frequent the 'Dominos' pizzeria.*

```ra
\project_{pizza} (
   ((\project_{name} Person)          // 1. All people
    \diff
    (\project_{name}                  // 2. People who frequent Dominos
        \select_{pizzeria='Dominos'}
             Frequents)
   \join Eats))                        // 3. Join remaining people with Eats to find their pizzas
```

---

## ⚠️ Important Limitations of *RA*

1. **Relation Renaming**: `\rename` only supports renaming of **attributes**, not relations.
2. **Ambiguous Attributes**: If a subexpression produces multiple attributes with the same name, you cannot reference them downstream without first renaming them using `\rename`.
3. **No Dot Notation**: The standard `relName.attrName` notation is neither needed nor supported. Use `\rename` to disambiguate column names.
4. **Attribute Ordering**: Attribute order matters in set operations (`\union`, `\diff`, `\intersect`). Always verify matching column sequences.
5. **Error Messages**: Because *RA* compiles relational algebra queries into SQL, errors from invalid expressions are returned directly by the underlying DBMS engine.
