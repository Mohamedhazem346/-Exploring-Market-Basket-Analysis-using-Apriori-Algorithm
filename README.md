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
2️⃣ Data Preprocessing 
Split each transaction into a list of items.
transactions = dataset.iloc[:,0].astype(str).str.split(',').tolist()
3️⃣ Transaction Encoding Transactions are converted into a binary matrix using TransactionEncoder.
from mlxtend.preprocessing import TransactionEncoder

te = TransactionEncoder()
te_ary = te.fit_transform(transactions)

data_encoded = pd.DataFrame(te_ary, columns=te.columns_, dtype=int)
 4️⃣ Frequent Itemsets
Apply Apriori Algorithm to extract frequent itemsets.
from mlxtend.frequent_patterns import apriori

frequent_itemsets = apriori(
    data_encoded,
    min_support=0.1,
    use_colnames=True
)
5️⃣ Association Rules
Generate rules based on Confidence.
from mlxtend.frequent_patterns import association_rules

rules = association_rules(
    frequent_itemsets,
    metric='confidence',
    min_threshold=0.3
)
6️⃣ Strong Rules Filtering
Filter strong rules using:
Confidence > 0.7
Lift > 1.5
📈 Visualizations
The project includes two types of visualizations.

📊 Top 20 Association Rules by Lift

A bar chart showing the strongest association rules based on Lift value.

The chart highlights the most influential product relationships.

Output file:

Top20_Lift_BarChart.png

🌐 Network Graph of Association Rules

A Network Graph visualizes relationships between products.

Nodes represent products

Edges represent association rules

Edge color represents Lift strength

Output file:

Top20_Lift_NetworkGraph.png
👨‍💻 Author
Name: Mohamed Hazem
LinkedIn:https://www.linkedin.com/in/mohamed-hazem-0513a82b5/
