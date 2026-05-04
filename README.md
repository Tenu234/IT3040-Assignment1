# IT3040 – ITPM Assignment 1
## Transliteration Accuracy Testing

**Module:** IT3040 – IT Project Management  
**Option:** Option 1 – Transliteration Accuracy Testing  
**Application Under Test:** https://www.pixelssuite.com/chat-translator

---

## Project Structure

```
IT3040-Assignment1/
│
├── test_automation/
│   ├── test_automation.py               # Main Playwright test script
│   └── Assignment 1 - Test cases.xlsx  # Test cases with results
│
└── README.md
```

---

## Prerequisites

- Python 3.10 or higher
- pip (Python package manager)
- Internet connection (to access the live application)

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/IT3040-Assignment1.git
cd IT3040-Assignment1
```

### 2. Upgrade pip

```bash
python -m pip install -U pip
```

### 3. Install required dependencies

```bash
python -m pip install playwright openpyxl
```

### 4. Install Playwright browsers

```bash
python -m playwright install
```

---

## Verify Installation

Run these commands to confirm everything is installed correctly:

```bash
python -m pip --version
python -m playwright --version
python -c "import openpyxl; print(openpyxl.__version__)"
python -m playwright install --dry-run
```

---

## Running the Tests

Navigate to the project folder and run:

```bash
python test_automation/test_automation.py
```

### Optional flags

Flag

headless -  Run without opening browser window 
wait-ms -Wait time (ms) for translation to load
retries - Number of retries per test case  8 
retry-wait-ms - Wait time (ms) between retries  1000 
save-every N Save Excel results every N rows 0 

### Example with flags

```bash
python test_automation/test_automation.py --wait-ms 8000 --retries 10 --save-every 5
```

---

## Output

Results are saved back into the Excel file:

```
test_automation/Assignment 1 - Test cases.xlsx
```

Each row is updated with:
- **Actual output** – the translation returned by the application
- **Status** – `PASS`, `FAIL`, or `COLLECTED`

---

## Test Case Summary

- Total test cases: **50**
- All test cases are **negative** (cases where the system fails to correctly transliterate)
- TC IDs begin with `Neg_`
- Covers all **24 Singlish input types** specified in Appendix 1

---

## Dependencies

| Package | Purpose |
|---------|---------|
| `playwright` | Browser automation for UI testing |
| `openpyxl` | Reading and writing Excel test case file |
