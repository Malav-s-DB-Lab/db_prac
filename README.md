# 🗄️ Database Practice Hub (`db_prac`)

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](../../codespaces/new)
[![Check Your Grade](https://img.shields.io/badge/Grading-View%20Your%20Score-brightgreen)](../../actions)

> An interactive, self-paced database practice repository featuring automated testing, instant grading, and progress tracking.
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

## 🚀 How to Practice (Student Guide)

### 1. Launch Environment (Zero Setup)
Click **[Open in GitHub Codespaces](../../codespaces/new)** or click **Code &rarr; Codespaces &rarr; Create codespace on main**. This opens a pre-configured cloud development environment with Java 17 and database tools ready to run.

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

### 4. Submit & View Your Personal Grade
Whenever you are ready to submit, commit and push your code:
```bash
git add .
git commit -m "Submit problem solutions"
git push
```
👉 **[View Your Grade & Test History](../../actions)**: Check the **Actions** tab of this repository to see your points breakdown (e.g. `Points 9/9`) and test logs for each commit!

---

## 🔓 How to Unlock Official Solutions
To encourage independent problem solving, reference solutions are locked by default:
1. Submit an attempt for **all 9 problems** (`ra-pizza_p1.ra` through `ra-pizza_p9.ra`). *(They do not all need to be 100% correct&mdash;just attempted!)*
2. Commit and push your code to GitHub.
3. The autograding bot will verify that all 9 questions have been attempted, and will **automatically commit the official reference solutions directly into your repository** under the [`Relational_Algebra/solutions/`](Relational_Algebra/solutions/) folder!
4. You can also download them as a zip artifact from your latest run in the **Actions** tab.

> [!IMPORTANT]
> **External Forks & Solution Access Notice:**  
> Anyone can open this project and test their solutions for free. However, if you are practicing on an **external fork**, GitHub security automatically restricts access to the encrypted solutions vault to prevent piracy.  
> If you have attempted all 9 problems and want to unlock the official solutions, please contact the repository owner ([@Malav786](https://github.com/Malav786)) to be invited as an authorized member of **Malav's DB Lab**!

