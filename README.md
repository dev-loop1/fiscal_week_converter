

# Fiscal Week Converter

A powerful **Streamlit** web app to **intelligently split weekly data that spans across months**, ensuring accurate and proportional reporting of partial weeks.

---

## Core Features

* **Smart Week Splitting**  
  Automatically separates any fiscal week that crosses a month boundary into two rows.
  *Example: A week starting Jan 29th is split into 3 days for January and 4 days for February.*

* **Proportional Value Distribution**    
  Distributes numerical values (e.g., sales, quantity) across the split weeks based on the number of days in each partial week.

* **Data Integrity Preserved**    
  All non-date and non-numerical columns are duplicated for each partial week, ensuring your data remains complete and consistent.

* **Dual-Engine Performance**    

  * **Pandas** for convenient `.xlsx` (Excel) file processing
  * **Polars** for ultra-fast, parallel `.csv` processing—even with large files

* **Built-in Verification**  
  The app automatically checks that the total sum of your selected value column remains unchanged after processing.

* **Friendly User Interface**    
  A clean and simple Streamlit interface guides you through every step.

---

## Technology Stack

* **Framework:** Streamlit
* **Data Processing:** Pandas, Polars
* **Dependencies:** `streamlit`, `pandas`, `polars`, `numpy`, `openpyxl`

---

## Getting Started (Run Locally)

### Prerequisites

* **Python 3.9+** – [Download here](https://www.python.org/downloads/)
* Alternatively, Python can be downloaded from the Microsoft Store [Download here](https://apps.microsoft.com/detail/9PNRBTZXMB4Z?hl=en-us&gl=US&ocid=pdpshare)
* `pip` (comes with Python)

---

### 1. Clone the Repository

```bash
git clone https://github.com/dev-loop1/fiscal_week_converter.git
cd fiscal-week-converter
```

---

### 2. Create a Virtual Environment (Recommended but not Mandatory)

**On Windows:**

```bash
python -m venv venv
venv\Scripts\activate
```

**On macOS/Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

---

### 3. Install Dependencies

Run:

```bash
pip install -r requirements.txt
```

---

### 4. (Optional) Increase File Upload Limit

If you're working with large files (>10 GB), adjust Streamlit’s upload size limit:

1. Go to the folder named `.streamlit` in the project root.
2. Inside it, there is a file called `config.toml` with the following:

```toml
# .streamlit/config.toml
[server]
maxUploadSize = 100000  # Size in MB (You can adjust the size here)
```

---

### 5. Run the Application

```bash
streamlit run app.py
```

This will launch the app in your browser.

---

## How to Use the App

1. **Upload Your File**  
   Supports both `.csv` and `.xlsx`.

2. **Preview the File**  

   * Preview the first 5 rows of the original data
   * Verify that original values match

3. **Select Columns**  

   * Start Date Column: Column containing the fiscal week’s start date
   * Value Column: Column with the numeric value to prorate (e.g., sales)

4. **Choose Date Format**  
   Make sure the format exactly matches your file (e.g., `YYYY-MM-DD`, `MM/DD/YYYY`, etc.)

5. **Process**  
   Click **"Process File"** to run the conversion.

6. **Review & Download**  

   * Preview the modified data (first 5 rows)
   * Verify that total values match
   * Download the processed file
