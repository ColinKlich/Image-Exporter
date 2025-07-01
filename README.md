# Export Images from SQL Databases by MRN

This PowerShell script automates the extraction of image files from multiple SQL Server databases based on a Medical Record Number (MRN). It is designed for environments where images are distributed across several databases and mapped to billing numbers for organizational purposes.

## Features

- **Multi-Database Access:**
  - Searches for images across a configurable list of SQL Server databases.
  - Automatically organizes extracted images into subfolders by MRN and billing number.

- **Security Focus:**
  - Uses parameterized SQL queries to prevent SQL injection.
  - Leverages Windows Integrated Security for database authentication (no passwords in the script).
  - Only users with proper Windows and SQL Server permissions can access the data.

- **Automated Folder Structure:**
  - Images are saved in `./images/<MRN>/<billing_number>/` for easy retrieval and compliance.

## Usage

1. **Configure the Script:**
   - Edit the server/database/table names at the top of the script as needed for your environment.

2. **Run the Script:**
   - Open PowerShell and execute the script.
   - Enter the MRN when prompted.

3. **Output:**
   - Images will be saved as `.jpg` files in the appropriate subfolders under `./images`.

## Requirements

- Windows with PowerShell 5.1 or later
- Access to the specified SQL Servers and databases
- Sufficient file system permissions to write to the output directory

## Security Notes

- The script uses Windows Authentication (`Integrated Security=True`), so only authorized users can access the data.
- All SQL queries are parameterized to mitigate SQL injection risks.
- No credentials are stored in the script.

## Example Folder Structure

```
./images/
  └── 123456/                # MRN
      ├── 987654/           # Billing number
      │   └── 123456_1.jpg
      └── 654321/
          └── 123456_2.jpg
```


## Disclaimer

This script is provided as-is. Ensure you have the necessary permissions and comply with your organization's data security policies before use.
