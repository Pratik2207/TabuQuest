# 🧠 TabuQuest

**TabuQuest** is an AI-powered tabular data question-answering system. It allows users to ask natural language questions (e.g., *"Which product had the highest gross income in Mandalay?"*) and receive relevant answers from structured tabular data like CSV files. This system integrates a retriever + reader pipeline using **sentence-transformers** and **transformers (BERT-based)** to emulate how humans explore and query spreadsheets.

---

## 📌 Key Features

- ✅ Accepts user queries in natural language  
- ✅ Uses sentence embeddings to locate relevant **rows and columns** in tables  
- ✅ Applies **transformer-based QA** (e.g., `distilBERT`) to generate accurate answers  
- ✅ Saves responses and context to an Excel output file  
- ✅ Easy to extend with more models or UI

---

## 🗂️ Project Structure

tabuquest/
├── data/
│ ├── input_table.csv # Main dataset
│ └── QA_dataset_share.xlsx # Optional: Question/Answer evaluation data
├── src/
│ ├── get_relevant_rows_and_cols() # Retriever
│ ├── generate_answer() # Reader
│ └── generate_output() # Pipeline output + saving
├── README.md
├── requirements.txt
└── predicted.xlsx # Output file

yaml
Copy
Edit

---

## ⚙️ Technologies Used

- Python 3.12+
- `pandas`
- `sentence-transformers` (`all-MiniLM-L6-v2`)
- `transformers` (`distilBERT`)
- `scikit-learn`, `torch`
- `openpyxl` (for Excel output)

---

## 🚀 How It Works

1. **User provides a tabular dataset (`input_table.csv`)**  
2. **User asks a question**, e.g.:
3. The system:
- Embeds the query
- Finds top relevant rows/columns using cosine similarity
- Extracts context and passes it into a QA model
4. **Answer is generated and saved to `predicted.xlsx`**

---

## 🧪 Example Outputs


---

## 🛠️ Installation & Setup

```bash
# 1. Clone the repo
git clone https://github.com/Pratik2207/TabuQuest.git
cd tabuquest

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the script (ensure data/input_table.csv exists)
python first.py  # Or use the notebook
