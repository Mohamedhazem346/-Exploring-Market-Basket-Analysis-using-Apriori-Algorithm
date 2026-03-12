# 🛒 Market Basket Analysis using Apriori Algorithm

This project applies **Market Basket Analysis** using the **Apriori Algorithm** to discover relationships between products that are frequently purchased together in grocery store transactions.

The goal is to extract **Association Rules** that reveal hidden patterns in customer purchasing behavior.

---

# 📊 Project Overview

Market Basket Analysis is a **Data Mining technique** used to identify relationships between items in large transactional datasets.

For example:

- Customers who buy **Bread** often buy **Milk**
- Customers who buy **Coffee** may also buy **Sugar**

These insights help businesses improve:

- Product placement
- Cross-selling strategies
- Marketing campaigns
- Recommendation systems

---

# 🧠 Techniques Used

The project uses **Association Rule Learning** based on:

- **Apriori Algorithm**
- **Support**
- **Confidence**
- **Lift**

These metrics determine the strength of relationships between products.

---

# 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- mlxtend
- NetworkX
- Arabic Reshaper
- python-bidi

---

# 📂 Dataset

The dataset contains **grocery transactions** where each row represents products purchased together.

Example:

milk,bread,butter  
bread,eggs  
milk,bread  

Each transaction is converted into a **binary encoded matrix** before applying the Apriori algorithm.

---

# ⚙️ Project Workflow

## 1️⃣ Data Loading

The dataset is loaded using Pandas.

```python
dataset = pd.read_excel("Egyptian_Grocery_Transactions.xlsx", header=None)
dataset.columns = ['items']
