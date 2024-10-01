# Description
Can you use your knowledge of format strings to make the customers happy?

## Walkthrough
Download the source code and binary files. Then connect to the host using nc. 

![alt text](/Easy/Binary/Images/formatstring0a.png)

When we connect we get the option to feed the customers a selection of foods. 

Lets look at the source code to get a better understanding:

*Buffer Size:*
The BUFSIZE is set to 32, which is the size of the buffer used for user input (choice1 and choice2).
The flag buffer is set to FLAGSIZE (64 bytes), and the flag is read from flag.txt.

*Signal Handler (sigsegv_handler):*
If a segmentation fault (SIGSEGV) occurs, the sigsegv_handler is triggered, printing the flag. This is important because it indicates the challenge might involve causing a segmentation fault to reveal the flag.

*Burger Menu Logic:*
The program has two customers: Patrick and Sponge Bob.
The user is asked to input a burger for each customer. The input is compared against a predefined menu using the on_menu() function.

*Critical Functionality:*
In serve_patrick(), if the number of characters printed with printf(choice1) is greater than 2 * BUFSIZE (64 characters), it calls serve_bob(). This seems to be the part where you can influence the flow of the program, likely through input manipulation.
In serve_bob(), there’s another menu check, and after the user inputs a choice, it prints the burger choice using printf(choice2).

------------------------------------------------------------------------------------------------------------------------------------------------

So by looking at this code we can tell we can try and get the flag by causing a buffer overflow with the selection of options given.

1. Patrick's Burger Choice:
The program gave three burger options: Breakf@st_Burger, Gr%114d_Cheese, and Bac0n_D3luxe.
When we enter Gr%114d_Cheese, the program calculates the length of this input.
If the length printed by printf() exceeds twice the buffer size (2 * BUFSIZE), which is 64 bytes, it calls the serve_bob() function. This essentially checks if the input is long enough to overflow the buffer, but since this choice didn't exceed the limit, we moved to the next customer.
2. Bob's Burger Choice:
For Bob, we were presented with another set of burger options: Pe%to_Portobello, $outhwest_Burger, and Cla%sic_Che%s%steak.
We input Cla%sic_Che%s%steak, a long enough string to overflow the buffer.
The program used printf(choice2) without a format string. This is a format string vulnerability, as it printed the input we provided directly, without proper validation. As a result, our input (Cla%sic_Che%s%steak) caused a memory corruption or segmentation fault.

This allowed us to get the flag. 