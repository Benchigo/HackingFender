# Password Compromise Detection and Notification

## Overview
This project is designed to detect compromised user accounts from a CSV file containing passwords, notify the boss about the success of the mission, and scramble the passwords to prevent further misuse.

## Features
- **Compromised User Detection**: Reads a CSV file (`passwords.csv`) to identify compromised user accounts.
- **Notification**: Creates a JSON file (`boss_message.json`) to notify the boss about the success of the mission.
- **Password Scrambling**: Generates a new CSV file (`news_passwords.csv`) with scrambled password data.

## Files
- `passwords.csv`: Input CSV file containing user passwords.
- `compromised_users.txt`: Output text file listing all compromised users.
- `boss_message.json`: Output JSON file containing a message to the boss.
- `news_passwords.csv`: Output CSV file with scrambled password data.

## Usage
1. **Detect Compromised Users**:
   - The script reads the `passwords.csv` file and extracts the usernames of compromised accounts.
   - The compromised usernames are written to `compromised_users.txt`.

2. **Notify the Boss**:
   - A JSON file (`boss_message.json`) is created with a message indicating the success of the mission.

3. **Scramble Passwords**:
   - A new CSV file (`news_passwords.csv`) is generated with scrambled password data to prevent further misuse.

## Code Explanation
```python
import csv
import json

# List to store compromised usernames
compromised_users = []

# Read the passwords CSV file
with open('passwords.csv', 'r') as password_file:
    password_csv = csv.DictReader(password_file)
    for password_row in password_csv:
        compromised_users.append(password_row['Username'])

# Write compromised usernames to a text file
with open("compromised_users.txt", "w") as compromised_user_file:
    for compromised_user in compromised_users:
        compromised_user_file.write(compromised_user + '\n')

# Notify the boss by creating a JSON file
with open('boss_message.json', "w") as boss_message:
    boss_message_dict = {
        "recipient": "The boss",
        "message": "Mission Success"
    }
    json.dump(boss_message_dict, boss_message)

# Scramble the passwords and write to a new CSV file
with open('news_passwords.csv', 'w') as new_password_obj:
    slash_null_sig = """
 _  _     ___   __  ____             
/ )( \   / __) /  \(_  _)            
) \/ (  ( (_ \(  O ) )(              
\____/   \___/ \__/ (__)             
 _  _   __    ___  __ _  ____  ____  
/ )( \ / _\  / __)(  / )(  __)(    \ 
) __ (/    \( (__  )  (  ) _)  ) D ( 
\_)(_/\_/\_/ \___)(__\_)(____)(____/ 
        ____  __     __   ____  _  _ 
 ___   / ___)(  )   / _\ / ___)/ )( \
(___)  \___ \/ (_/\/    \\___ \) __ (
       (____/\____/\_/\_/(____/\_)(_/
 __ _  _  _  __    __                
(  ( \/ )( \(  )  (  )               
/    /) \/ (/ (_/\/ (_/\             
\_)__)\____/\____/\____/
"""
    new_password_obj.write(slash_null_sig)

## Requirements
Python 3.x
csv module (standard library)
json module (standard library)
## How to Run
Ensure you have Python 3.x installed.
Place the passwords.csv file in the same directory as the script.
Run the script using the command: python script.py
Check the output files: compromised_users.txt, boss_message.json, and news_passwords.csv.
## License
This project is licensed under the MIT License.

```
