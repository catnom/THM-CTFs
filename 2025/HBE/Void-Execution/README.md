# void execution challenge (Task 36)

This repository contains files for a binary exploitation challenge called "void execution". the challenge involves exploiting a binary to gain remote code execution.

## Challenge Overview

The challenge appears to involve exploiting a binary called `voidexec` which contains a vulnerability allowing arbitrary code execution. the binary contains a message "Send to void execution:" which likely prompts for user input that can be exploited.

## Exploit Script

The `exploit.py` script uses pwntools to:

1. connect to a remote server

 2. generate shellcode that:

   \> calls the `mprotect` function to make memory executable

   \> sets up a `/bin/sh` executable path

   \> prepares registers for a system call

   \> executes a modified syscall

3. Send the shellcode when prompted
4. Open an interactive shell

## Usage

1. Clone the Repository:
   use the following command to download all the challenge files:
   ```bash
   git clone <https://github.com/catnom/THM-CTFs.git>
   ```

2. Make the binary executable
  run the following command to give execution permission to the binary:
   ```bash
   chmod +x voidexec
   ```


3. modify the exploit.py script to your own ip:
   ```py
   r = remote('your ip', 9008)
   ```

4. run the exploit:
   ```bash
   python3 exploit.py
   ```
\> when the script runs successfully, you should see:

```
[DEBUG] Received 0xa bytes:
    b'\n'
    b'voided!\n'
    b'\n'

response: voided!
```
\> just type
```
cat flag.txt
```
And voila! There's your flag.
\


\
Happy Hacking~
