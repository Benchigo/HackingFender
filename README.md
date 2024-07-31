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
