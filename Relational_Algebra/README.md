# 🍕 Relational Algebra Practice Lab

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](../../../codespaces/new)
[![Check Your Grade](https://img.shields.io/badge/Grading-View%20Your%20Score-brightgreen)](../../../actions)

> An interactive, self-paced Relational Algebra problem set featuring automated testing and instant feedback using GitHub Actions autograding.
> **Curated & Maintained by [Malav's DB Lab](https://github.com/Malav-s-DB-Lab)**

---

## 🚀 Quick Start Guide

### 1. Open in Codespaces (Zero Setup)
Click **[Open in GitHub Codespaces](../../../codespaces/new)** or click **Code** &rarr; **Codespaces** &rarr; **Create codespace on main**. This launches a pre-configured cloud development environment with Java 17 ready to go.

### 2. Solve the Problems
Write your Relational Algebra query for each problem in its corresponding file:
* Problem 1: `ra-pizza_p1.ra`
* Problem 2: `ra-pizza_p2.ra`
* Problem 3: `ra-pizza_p3.ra`
* Problem 4: `ra-pizza_p4.ra`
* Problem 5: `ra-pizza_p5.ra`
* Problem 6: `ra-pizza_p6.ra`
* Problem 7: `ra-pizza_p7.ra`
* Problem 8: `ra-pizza_p8.ra`
* Problem 9: `ra-pizza_p9.ra`

### 3. Test Locally in Codespace Terminal
Run any problem using the `ra.jar` interpreter:
```bash
cd Relational_Algebra
java -jar ra.jar -i ra-pizza_p1.ra
```

### 4. Submit & View Your Personal Grade
Whenever you push your commits to GitHub, the autograding workflow runs automatically:
```bash
git add .
git commit -m "Submit problem solutions"
git push
```
👉 **[View Your Grade & Test History](../../../actions)**: Check the **Actions** tab of this repository to view points earned, test outputs, and submission logs for each commit!

---

## 🗄️ Database Schema

The database models people, their pizza preferences, and pizzeria menus with four relations:

```
Person(name, age, gender)       // name is a key
Frequents(name, pizzeria)       // [name,pizzeria] is a key
Eats(name, pizza)               // [name,pizza] is a key
Serves(pizzeria, pizza, price)  // [pizzeria,pizza] is a key
```

📄 **[View Sample Data & Initial Tables](pizza_data.md)**

If you ever need to reset the database to its clean initial state, run:
```bash
java -jar ra.jar -i sample.ra
```

---

## 📖 Relational Algebra Syntax Guide

For complete operator documentation, examples, and language limitations, see the dedicated reference:
👉 **[Full RA Syntax & Operator Guide](ra_syntax_guide.md)**

### Quick Operator Cheat Sheet:
| Operator | Syntax | Description |
| :--- | :--- | :--- |
| **Selection** | `\select_{cond} R` | Filters rows matching condition `cond` |
| **Projection** | `\project_{attr_list} R` | Selects specified attributes |
| **Natural Join** | `R1 \join R2` | Joins on common attribute names |
| **Theta Join** | `R1 \join_{cond} R2` | Joins matching condition `cond` |
| **Cross-Product** | `R1 \cross R2` | Cartesian product of relations |
| **Set Operations** | `\union`, `\diff`, `\intersect` | Mathematical set operations |
| **Renaming** | `\rename_{new_attrs} R` | Renames attributes of relation |

---

## 🎯 Practice Problems

### Problem 1
Find all pizzas eaten by at least one female over the age of 20.  
*(Save in `ra-pizza_p1.ra`)*

### Problem 2
Find the names of all females who eat at least one pizza served by Straw Hat. *(Note: The pizza need not be eaten at Straw Hat.)*  
*(Save in `ra-pizza_p2.ra`)*

### Problem 3
Find all pizzerias that serve at least one pizza for less than $10 that either Amy or Fay (or both) eat.  
*(Save in `ra-pizza_p3.ra`)*

### Problem 4
Find all pizzerias that serve at least one pizza for less than $10 that both Amy and Fay eat.  
*(Save in `ra-pizza_p4.ra`)*

### Problem 5
Find the names of all people who eat at least one pizza served by Dominos but who do not frequent Dominos.  
*(Save in `ra-pizza_p5.ra`)*

### Problem 6
Find all pizzas that are eaten only by people younger than 24, or that cost less than $10 everywhere they're served.  
*(Save in `ra-pizza_p6.ra`)*

### Problem 7
Find the age of the oldest person (or people) who eat mushroom pizza.  
*(Save in `ra-pizza_p7.ra`)*

### Problem 8
Find all pizzerias that serve only pizzas eaten by people over 30.  
*(Save in `ra-pizza_p8.ra`)*

### Problem 9
Find all pizzerias that serve every pizza eaten by people over 30.  
*(Save in `ra-pizza_p9.ra`)*

---

## 🔓 Solution Unlock System

Official solutions are locked until you have submitted an attempt for all 9 problems (`ra-pizza_p1.ra` to `ra-pizza_p9.ra`). 

Once you commit and push your attempts for all 9 questions:
1. The automated autograder verifies all 9 problems are submitted.
2. It automatically **commits the official reference solutions directly into your repository** under the [`Relational_Algebra/solutions/`](solutions/) folder!
3. You can also download them as a zip artifact from your latest workflow run in the **Actions** tab.

> [!IMPORTANT]
> **External Forks & Solution Access Notice:**  
> Anyone can open this project and test their solutions for free. However, if you are practicing on an **external fork**, GitHub security automatically restricts access to the encrypted solutions vault to prevent piracy.  
> If you have attempted all 9 problems and want to unlock the official solutions, please contact the repository owner ([@Malav786](https://github.com/Malav786)) to be invited as an authorized member of **Malav's DB Lab**!

