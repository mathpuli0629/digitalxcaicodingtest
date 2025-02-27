# Secret Santa Assignment

## Overview
This program automates the Secret Santa game by randomly assigning each employee a "Secret Child" while ensuring the following rules:
- An employee cannot be their own Secret Santa.
- No employee can be assigned the same Secret Child as the previous year.
- Every employee must have exactly one Secret Child.

## Features
- Reads employee details from a CSV file.
- Ensures no duplicate assignments based on the previous year's data.
- Writes new Secret Santa assignments to a CSV file.
- Uses recursion to handle assignment conflicts.
- Provides error handling for missing or corrupt files.

## Installation
### Prerequisites
- Python 3.x

### Install Dependencies
No additional libraries are required beyond Python's built-in modules.

## Usage
1. **Prepare Input CSV Files**
   - `employees.csv` (List of employees participating in Secret Santa)
     ```csv
     Employee_Name,Employee_EmailID
     Alice,alice@example.com
     Bob,bob@example.com
     Charlie,charlie@example.com
     ```
   - `previous_santa.csv` (Last year's assignments, if available)
     ```csv
     Employee_Name,Secret_Child_Name
     Alice,Bob
     Bob,Charlie
     Charlie,Alice
     ```

2. **Run the Program**
   ```sh
   python secret_santa.py
   ```

3. **Output**
   - `new_santa_assignments.csv` will be generated with new assignments:
     ```csv
     Employee_Name,Employee_EmailID,Secret_Child_Name,Secret_Child_EmailID
     Alice,alice@example.com,Charlie,charlie@example.com
     Bob,bob@example.com,Alice,alice@example.com
     Charlie,charlie@example.com,Bob,bob@example.com
     ```

## Error Handling
- If files are missing or have incorrect formatting, the program prints an error message.
- If valid assignments are not possible, the program retries the randomization process.

