# Singlish to Sinhala Translation - Automated Test Suite

This repository contains an automated testing framework designed to evaluate the accuracy of a Singlish to Sinhala translation frontend. The test suite covers various linguistic categories, including question forms, slang, digital terms, and mixed-language inputs, based on the provided assignment specifications.

## 🚀 Overview

The primary goal of this project is to automate the validation of 50 test cases using **Playwright** and **Python**. The script reads test data from an Excel file, interacts with the web interface, and records the actual translation output and pass/fail status directly back into the Excel sheet.

**Author Information:**
*   **Student Name:** SEWMINI A A M Y
*   **Student ID:** IT23602946

## 📂 Project Structure

According to the provided image, the extracted project folder is located at:
`C:\Users\Minuri Sewmini\OneDrive\Desktop\IT23602946`

Inside this folder, the following files are required for execution:
*   `IT23602946_test_automation.py`: The core Python script for UI automation.
*   `IT23602946_Test Cases.xlsx`: Excel file containing the Test Data.

## 🛠️ Installation & Setup (One-time)

Before running the automation script, you must install the necessary Python dependencies. Open your Command Prompt or terminal and execute the following commands:

1.  **Install Python Packages:**
    ```cmd
    python -m pip install playwright openpyxl
    ```

2.  **Install Playwright Browsers:**
    ```cmd
    python -m playwright install
    ```

## ⚙️ Execution Instructions

To run the full test suite, follow these steps:

1.  Open your terminal and navigate to the project directory:
    ```cmd
    cd "C:\Users\Minuri Sewmini\OneDrive\Desktop\IT23602946"
    ```

2.  Run the automation script using the following command. This command is configured with optimal timeout and stability settings for best results:

    ```cmd
    python IT23602946_test_automation.py --excel "C:\Users\Minuri Sewmini\OneDrive\Desktop\IT23602946\IT23602946_Test Cases.xlsx" --input-col "Input" --expected-col "Expected output" --wait-ms 10000 --save-every 1 --slow-mo-ms 500
    ```

### ❗ Important Note for Successful Execution:
You must **CLOSE** the Excel file (`IT23602946_Test Cases.xlsx`) before running the command above. The script cannot write results to the file if it is already open.

### Command Arguments Explained:
*   `--excel`: Complete file path to the test case spreadsheet.
*   `--wait-ms`: (10000) A 10-second timeout allows the website enough time to complete complex or long translations.
*   `--save-every 1`: Automatically saves results to the Excel file after *each* row is tested. This prevents data loss if the test is interrupted.
*   `--slow-mo-ms`: (500) Adds a small delay between automated clicks to simulate human behavior, improving UI stability.

## 📝 Checking Results

Once the test completes, you will see a success message. You can then open the Excel file. Verify that the **Actual output** and **Status** columns have been populated automatically by the script.
