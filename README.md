# facebook-login

## Overview
`facebook-login` is a powerful and efficient Python package designed to automate the login process to Facebook accounts using Selenium WebDriver. This package reads account credentials from a file and attempts to log in to each account, providing detailed success or failure reports.

## Features
- **Automated Login**: Automatically logs in to Facebook accounts using provided credentials.
- **Account Management**: Reads multiple accounts from a file for batch processing.
- **Detailed Logging**: Provides detailed logs for success, failure, and errors encountered during the login process.
- **Selenium Integration**: Utilizes Selenium WebDriver for robust and reliable automation.

## Installation

To install the package, use pip:

```bash
pip install facebook-login
```

## Usage

### Importing the Package

First, you need to import the package in your Python script:

```python
import facebook_login
```

### Logging in to Facebook Accounts

1. **Prepare the Accounts File**:
   Create a file (e.g., `accounts.txt`) with the following format, listing your Facebook account credentials:

    ```plaintext
    username=example@gmail.com
    password=example_password
    ```

2. **Use the Package**:
   Use the package to read the accounts from the file and attempt to log in to each account:

    ```python
    from facebook_login import read_accounts_from_file, test_facebook_account

    # Read accounts from file
    accounts = read_accounts_from_file('accounts.txt')

    # Attempt to log in to each account
    for account in accounts:
        test_facebook_account(account['username'], account['password'])
    ```

## API Reference

### Functions

#### `test_facebook_account(username: str, password: str)`

Attempts to log in to Facebook using the provided username and password. This function uses Selenium WebDriver to automate the login process.

**Parameters:**
- `username` (str): The username (email or phone number) of the Facebook account.
- `password` (str): The password of the Facebook account.

**Example:**

```python
from facebook_login import test_facebook_account

test_facebook_account('example@gmail.com', 'example_password')
```

#### `read_accounts_from_file(filename: str) -> list`

Reads account credentials from the specified file and returns a list of dictionaries containing the usernames and passwords.

**Parameters:**
- `filename` (str): The path to the file containing the account credentials.

**Returns:**
- `list`: A list of dictionaries, each containing `username` and `password` keys.

**Example:**

```python
from facebook_login import read_accounts_from_file

accounts = read_accounts_from_file('accounts.txt')
```

## File Format

The file containing the account credentials should be formatted as follows:

```plaintext
username=example@gmail.com
password=example_password
```

Each account's credentials should be specified on two lines, with `username` and `password` keys.

## Logging and Error Handling

The package includes logging to provide information about the login process, including successful logins and errors encountered. This helps in diagnosing issues and understanding the package's behavior.

## Example Script

Here's an example script that demonstrates how to use the package:

```python
import facebook_login

def main():
    # Path to the file containing Facebook account credentials
    file_directory = 'accounts.txt'

    # Read accounts from the file
    accounts = facebook_login.read_accounts_from_file(file_directory)

    # Check if accounts were found in the file
    if not accounts:
        print("No accounts found in the file.")
    else:
        # Attempt to log in to each account
        for account in accounts:
            facebook_login.test_facebook_account(account['username'], account['password'])

if __name__ == "__main__":
    main()
```

## Additional Information

- **Dependencies**: The package depends on the `selenium` library. Ensure that you have the appropriate WebDriver installed (e.g., ChromeDriver for Google Chrome).
- **WebDriver Installation**: Follow the instructions to install the WebDriver for your browser. For Chrome, download and place the `chromedriver` executable in your system's PATH.

## Support

If you encounter any issues or have questions, please open an issue on the GitHub repository or contact the package maintainer.

## Contributing

Contributions are welcome! Please read the contributing guidelines and follow the code of conduct.

## License

This project is licensed under the GPL-3.0 License - see the LICENSE file for details.

## Acknowledgements

- Thanks to the Selenium team for their powerful automation tools.
- Inspired by the need for efficient Facebook account management and automation.

---

By following these steps and using this documentation, users can effectively utilize the `facebook-login` package for their automation needs. Happy coding!
```

This complete `README.md` includes all necessary sections: features, installation, usage examples, API reference, file format, logging, an example script, additional information, support, contributing, license, and acknowledgements. This ensures users have all the information they need in one cohesive document.
