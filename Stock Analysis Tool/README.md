# Stock Analysis Tool

## Overview of Features

### **Data Sources**
The program fetches data both **online** (e.g., Yahoo Finance) and **offline** (from local files), giving flexibility based on user preference.

### **Stock Metrics Analyzed**
- **Fundamental Analysis**:
  - **Debt-to-Equity ratio**: Measures a company's financial leverage.
  - **Price-to-Earnings (P/E) ratio**: Indicates if a company's stock is over- or undervalued.
  - **Price-to-Sales (P/S) ratio**: Evaluates a company's stock price relative to its sales.
- **Technical Analysis**:
  - **Price Development**: Percentage change in stock price over the last 30 days.
  - **Highest and Lowest Prices**: Recorded stock prices during the last 30 days.
  - **Beta Value**: Measures the stock's volatility compared to the overall market (OMX index).

### **Interactive Display Options**
- **GUI**: A user-friendly interface built using `tkinter` for visualizing stock metrics.
- **Terminal**: Command-line menus for displaying data.

---

## How the Program Works

### **Workflow**

![Figure1](./Diagram/Aktieköp.jpg)

The program follows this flow:
1. **Data Retrieval**:
   - **Online**: Fetch real-time data from Yahoo Finance.
   - **Offline**: Load historical data and fundamentals from local files (e.g., `kurser.txt`, `fundamenta.txt`).
2. **Object Creation**:
   - Creates `Stock` objects for each company, storing fundamental and technical metrics.
3. **Data Display**:
   - Users can choose between GUI or terminal-based interfaces to explore:
     - **Fundamental Analysis**.
     - **Technical Analysis**.
     - **Beta-based Ranking**.

### **Key Functionalities**
1. **Fetch Data**:
   - **Online**: `get_fundamentals_data_online()` and `get_history_data_online()`.
   - **Offline**: `get_fundamentals_data_offline()` and `get_history_data_offline()`.
2. **Analyze Data**:
   - Calculate metrics like price trends and beta using methods like `calculate_betha()` in the `Stock` class.
3. **Display Options**:
   - **Terminal Menus**: Navigate through text-based menus.
   - **GUI**: Use dropdowns and buttons to explore metrics interactively.

---

## Example Usage

### **Terminal Workflow**
1. Run the program:
   ```bash
   python Aktieköp.py
   ```
2. Follow the interactive prompts:
   - Choose to fetch data **online** or **offline**.
   - Select analysis options from the **Main Menu**:
     - View **fundamental data**.
     - Explore **technical trends**.
     - Rank companies based on **beta value**.

### **GUI Workflow**
1. Select the GUI option at startup.
2. Interact with dropdown menus and buttons to:
   - View **technical** and **fundamental analysis** for selected companies.
   - Display beta-based rankings.

---

## Key Components

### **Stock Class**
The core object representing each company, storing metrics such as:
- **Fundamental data**: Debt-to-Equity, P/E, P/S.
- **Technical data**: Price trends, beta value.
- **Methods**:
  - `calculate_betha()`: Computes beta by comparing stock returns with the OMX index.
  - `calculate_course_development()`: Calculates percentage price change over 30 days.

### **Modules**
- **Data Fetching**:
  - `get_history_data_online()`: Fetches historical stock prices from Yahoo Finance.
  - `get_fundamentals_data_offline()`: Reads fundamental metrics from local files.
- **User Interaction**:
  - `show_main_menu()`: Displays the terminal-based main menu.
  - `gui_menu()`: Creates an interactive GUI with `tkinter`.

---

## Requirements

### **Dependencies**
- `yfinance`: Fetch online stock data.
- `pandas_datareader`: Retrieve historical stock prices.
- `tkinter`: Build the graphical user interface.

### **Installation**
Install the required libraries using:
```bash
pip install yfinance pandas_datareader
```