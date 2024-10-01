# Description
Are overflows just a stack concern?

## Walkthrough
First we need to download the binary and source code files. Then connect to the instance using netcat. When we connect we get this screen:

![alt text](/Easy/Binary/Images/heap1.png)

Lets look at the source code to understand what is happening. 

**Key Points:**
*Memory Allocations:*
Two heap variables are allocated:
input_data: Holds the user’s input, allocated with a size of 5 bytes (INPUT_DATA_SIZE).
safe_var: A separate heap variable initialized with the string "bico" and allocated with 5 bytes (SAFE_VAR_SIZE).
check_win() Function:

The goal of the challenge is to modify the contents of safe_var to something other than "bico". If the strcmp(safe_var, "bico") != 0, it triggers the win condition, printing "YOU WIN" and revealing the flag from the flag.txt file.
If safe_var remains "bico", it prints a message saying everything is still secure.

*User Interaction:*
Print Heap State: Display memory addresses and contents of input_data and safe_var.
Write to Buffer: The user can input data into the input_data buffer, which is vulnerable.
Print safe_var: Shows the current value of safe_var.
Print Flag: Checks the win condition by calling check_win().

*Heap Overflow Vulnerability:*
A crucial vulnerability lies in the buffer writing (write_buffer()). The size of input_data is only **5 bytes**, but there is no check on the size of the input provided by the user. This allows for a heap buffer overflow, where user input exceeding 5 bytes could overwrite adjacent memory on the heap, specifically the safe_var variable.
If the user overwrites safe_var with something other than "bico", the check_win() function will succeed, printing the flag.

------------------------------------------------------------------------------------------------------------------------------------------------

So our stategy will be to input more than 5 characters to see if we can provoke buffer overflow first.

However, if we select option 1: The heap we can see some interesting data we need to make note of. 

![alt text](/Easy/Binary/Images/heap2.png)

We know input_data and safe_var are separated by 32 bytes. This means any input that is long enough (more than 32 characters) should start to overwrite safe_var. So we need to input 32 + extra characters:

![alt text](/Easy/Binary/Images/heap3.png)

Now when we view safe_var we can see it has been overwritten by those +extra character bytes.
Now we can choose no.4 and get the flag:

![alt text](/Easy/Binary/Images/heap4.png)