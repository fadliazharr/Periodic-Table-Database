# Periodic Table Element Lookup Script

This is a Bash script that allows users to query information about chemical elements from a PostgreSQL database representing a periodic table.

## What It Does

- Accepts an element's name, symbol, or atomic number as a command-line argument.
- Returns detailed information about the element, including:
  - Atomic number
  - Symbol
  - Name
  - Atomic mass
  - Type
  - Melting and boiling points in Celsius
- If the element does not exist, it notifies the user.
- Contains an internal database-fixing function that ensures the schema and data meet specific constraints.

## How It Works

The script:
- Connects to a PostgreSQL database using the `psql` command-line tool.
- Queries the `elements`, `properties`, and `types` tables using SQL.
- Parses and formats the output using standard shell utilities like `sed`.

## How It Was Built

- Written entirely in Bash.
- Interacts with a PostgreSQL database (`periodic_table`) using `psql`.
- Follows structured data normalization by separating element types into a dedicated `types` table.
- Ensures referential integrity through foreign keys and constraints.

## Tools Used

- **Bash**: Scripting logic and user input handling.
- **PostgreSQL**: Database management and SQL querying.
- **psql**: Command-line interface to interact with PostgreSQL.
- **GNU coreutils**: Tools like `sed` for output formatting.

## Setup Requirements

- PostgreSQL installed and running.
- A database named `periodic_table` with the expected tables and columns.
- User `freecodecamp` with access to the database.

## Usage

```bash
./element.sh hydrogen
./element.sh H
./element.sh 1
