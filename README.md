# 3-Tier Architecture Generator 🚀

![.NET](https://img.shields.io/badge/.NET-Framework%204.8-blueviolet) ![C#](https://img.shields.io/badge/C%23-11.0-blue) ![SQL Server](https://img.shields.io/badge/Database-SQL%20Server-green) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A C# console application that automatically generates a complete 3-tier architecture solution (DTO, DAL, BLL, and ConsoleApp) based on your SQL Server database schema. It creates CRUD operations with interfaces for better maintainability and extensibility.

## 📝 Description

This tool connects to your SQL Server database, analyzes the schema (tables, columns, primary keys, foreign keys, and identity columns), and generates a Visual Studio solution with:

- **DTO Layer**: Data Transfer Objects for each table, including interfaces.
- **DAL Layer**: Data Access Layer with repositories and interfaces for CRUD operations.
- **BLL Layer**: Business Logic Layer with services and interfaces.
- **ConsoleApp**: A console application for interactive CRUD management on the generated entities.

The generated code uses async/await for database operations and handles nullable fields, identity columns, and basic validation. It's designed for .NET Framework 4.8 and assumes single primary keys per table for simplicity.

## ✨ Features

- 🔍 Automatically fetches database schema via SQL connection.
- 🛠 Generates full C# projects with project files (.csproj) and solution file (.sln).
- 📊 Supports CRUD operations (Create, Read, Update, Delete) in DAL and BLL.
- 🔑 Handles primary keys, foreign keys, identity columns, and nullable types.
- 🖥 Interactive console app for managing data (list, view, add, update, delete).
- ⚙️ Configurable via App.config for connection strings.
- 📁 Outputs a ready-to-open Visual Studio solution.

## 📋 Requirements

- **.NET Framework 4.8** installed.
- **SQL Server** database access (Windows or SQL authentication).
- **Visual Studio** (to open and build the generated solution).
- Permissions to read database schema (INFORMATION_SCHEMA and sys.columns).

No additional NuGet packages required—the code uses System.Data.SqlClient.

## 🛠 Installation

1. Clone the repository:
   ```
   git clone https://github.com/MohmdAliMohmd/three-tier-generator](https://github.com/MohmdAliMohmd/AsyncInterfaceCodeGen.git
   ```

2. Open the solution in Visual Studio and build the project.

3. Run the console app from bin/Debug or directly in VS.

## 🔧 Usage

1. Run the executable:
   ```
   ThreeTierGenerator.exe
   ```

2. Enter database details:
   - Server name (e.g., localhost).
   - Database name.
   - Authentication (Windows or SQL credentials).

3. Provide the output folder path for the generated solution.

4. The tool will:
   - Connect to the database.
   - Generate the 4 projects (DTO, DAL, BLL, ConsoleApp).
   - Output the solution path and reference instructions.

5. Open the generated .sln in Visual Studio:
   - Add project references as prompted (ConsoleApp → BLL → DAL → DTO).
   - Update App.config in ConsoleApp with your connection string if needed.
   - Build and run ConsoleApp to manage data.

### Example Output

After generation, you'll have folders like:
- `DTO/`: Contains DTO classes and interfaces.
- `DAL/`: Repositories with SQL queries.
- `BLL/`: Services calling DAL.
- `ConsoleApp/`: Interactive CRUD menu.

Run ConsoleApp:
- Select a table.
- Perform operations like listing records or adding new ones.

## ⚠️ Limitations

- Assumes single primary key per table (no composite keys supported yet).
- Basic type mapping (e.g., all unknown SQL types map to string).
- No support for views, stored procedures, or complex relationships.
- ConsoleApp uses dynamic reflection for generality—may not handle all edge cases.
- Tested on SQL Server; may need adjustments for other DBMS.

For enhancements, feel free to contribute!

## 🤝 Contributing

Pull requests are welcome! For major changes, open an issue first.

1. Fork the repo.
2. Create a feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Open a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Built with ❤️ by [MohmdAliMohmd]. If you find this useful, give it a ⭐ on GitHub!
