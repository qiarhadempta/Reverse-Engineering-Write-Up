# Easy Peasy
## Challenge Overview

In this challenge, we were given a Windows executable that prompts for username and password. Our goal is to extract
the credentials by analyzing the binary in Ghidra.  
Access the challenge here: https://crackmes.one/crackme/5d295dde33c5d410dc4d0d05

<img width="1900" height="830" alt="image" src="https://github.com/user-attachments/assets/bf8bf3a6-f4fe-4828-a181-99199ae1e1e9" />

---

## Solution

### 1. Load the binary in Ghidra

Create a new project and import the `.exe` file into Ghidra

![Ghidra import](https://github.com/user-attachments/assets/6d9c8aa2-aa82-41ea-9a98-a421beffa3a3)

### 2. Run auto-analysis

Go to Analyze menu, and then click Auto Analyze, make sure all options are checked, then click
Analyze.

![Auto Analyze menu](https://github.com/user-attachments/assets/047c8974-1fbd-4d85-a216-53e20fccce55)  
![Auto Analyze options](https://github.com/user-attachments/assets/cee17aa4-b61f-403b-88d9-a12163ee4a4b)

### 3. Locate the `main` function

In the Symbol Tree panel on the left, search for `main`. This is the program
entry point, so we can analyze it to reveals the application's logic and control flow.

![Symbol Tree - main](https://github.com/user-attachments/assets/64ad4e2a-3847-4b3a-b31f-d04078fc5091)

### 4. Extract the credentials

At address `0x0040155a` inside `main`, the credentials are visible in
plaintext. The username is `iwonderhowitfeelstobeatimetravel` and the password is `heyamyspaceboardisbrokencanyouhelpmefindit`

![Hardcoded credentials in Ghidra](https://github.com/user-attachments/assets/4c82b8f9-195b-41ac-9985-f6e0ab811fbc)

### 5. Log in

Run the `.exe`, and it will take you directly to CMD prompt. Enter the credentials above to
successfully authenticate.

<img width="1444" height="365" alt="image" src="https://github.com/user-attachments/assets/c325d7b4-d7fa-47db-a5c0-92605ee39168" />

---
