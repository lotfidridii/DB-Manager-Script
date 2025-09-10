# 🚀 DB Manager Script
A Bash script to create and delete MySQL or PostgreSQL databases and users, with both interactive menu mode and command-line parameters mode.

## Features
* Create PostgreSQL or MySQL database and user
* Delete PostgreSQL or MySQL database and user
* CLI mode with parameters (-c/-d -p/-m)
* Safe delete with confirmation prompt
* Interactive menu mode with colors and progress bar

## Requirements
* Bash shell
* sudo privileges (for PostgreSQL operations)
* MySQL root access (password required for CLI operations)
* PostgreSQL postgres system user

## Usage
### Interactive Mode
Simply run the script without parameters:
```shell
./dbmanager
```
You will be prompted to:

* Select the database type (PostgreSQL or MySQL)
* Select the operation (Create or Delete)
* Enter database name, username, and password (for creation)
* Confirm deletion (for deletion)

### CLI Mode (Parameters)

| Option | Description            |
| ------ | ---------------------- |
| `-c`   | Create database & user |
| `-d`   | Delete database & user |
| `-p`   | Use PostgreSQL         |
| `-m`   | Use MySQL              |
| `-h`   | Show help              |

##### Examples
Create a PostgreSQL database and user:
```shell
./dbmanager -c -p mydb myuser mypass
```
Delete a PostgreSQL database and user:
```shell
./dbmanager -d -p mydb myuser
```
Create a MySQL database and user:
```shell
./dbmanager -c -m mydb myuser mypass
```
Delete a MySQL database and user:
```shell
./dbmanager -d -m mydb myuser
```
Show help:
```
./dbmanager -h
```
## Behavior
* Interactive mode is used if no parameters are passed.
* CLI mode is used if parameters are provided.
* Delete operation requires explicit confirmation (y or Y).
* Progress bar animation shows during creation or deletion for visual feedback.
## Notes
* For MySQL, the script prompts for the root password during operations.
* For PostgreSQL, the script assumes the current user can run `sudo -i -u postgres psql`.
* Passwords are required only for creation of new users.
