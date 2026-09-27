# 🗄️ Database Practice Hub (`db_prac`)

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/Malav-s-DB-Lab/db_prac)
[![Relational Algebra Autograding](https://github.com/Malav-s-DB-Lab/db_prac/actions/workflows/relational_algebra.yml/badge.svg)](https://github.com/Malav-s-DB-Lab/db_prac/actions/workflows/relational_algebra.yml)

> A modular database practice repository featuring interactive exercises, automated testing, and instant grading feedback.
> **Curated & Maintained by [Malav's DB Lab](https://github.com/Malav-s-DB-Lab)**

---

## 📚 Practice Modules

| Module | Description | Status |
| :--- | :--- | :--- |
| 🍕 **[Relational Algebra](./Relational_Algebra/)** | 9 interactive RA queries over a Pizzeria database with automated test evaluation. | ✅ **Active** |
| 🐬 **SQL Practice** | Intermediate and advanced SQL queries (aggregations, joins, window functions). | 🚧 *Planned* |
| 📐 **Database Normalization & Design** | Functional dependencies, BCNF, and 3NF decomposition exercises. | 🚧 *Planned* |
| ⚡ **Indexing & Query Optimization** | Query execution plans, EXPLAIN analysis, and performance tuning. | 🚧 *Planned* |

---

## 🚀 How to Practice

### 1. Launch Environment (Zero Setup)
Click **[Open in GitHub Codespaces](https://codespaces.new/Malav-s-DB-Lab/db_prac)** or click **Code &rarr; Codespaces &rarr; Create codespace on main**. This opens a pre-configured cloud development environment with Java 17 and database tools ready to run.

### 2. Choose a Module
Navigate into the module directory:
```bash
cd Relational_Algebra
```
Follow the detailed guide in that module's `README.md` to solve the problems.

### 3. Test Locally
Run tests locally inside the module directory:
```bash
# Example for Relational Algebra Problem 1:
cd Relational_Algebra
java -jar ra.jar -i ra-pizza_p1.ra
```

### 4. Submit & Get Graded
Commit and push your solutions to GitHub:
```bash
git add .
git commit -m "Submit problem solutions"
git push
```
The automated grading suite will run under the **Actions** tab on GitHub and generate your score!

### 🔓 Unlocking Reference Solutions
Reference solutions are locked by default to promote independent learning. 
To unlock the reference solutions:
* Submit an attempt for **all 9 problems** (`ra-pizza_p1.ra` through `ra-pizza_p9.ra`).
* Push your code to GitHub.
* Once the automated check verifies all 9 questions have been attempted, the official reference solutions will automatically unlock!

---

> 💡 **Tip for Collaborators & Friends**: Create your own branch (`git checkout -b your-name`) before committing so your solutions remain separate. GitHub Actions autograding will automatically evaluate any branch you push!
