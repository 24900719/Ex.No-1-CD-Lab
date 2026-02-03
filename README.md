# Ex. No : 1

# IMPLEMENTATION OF SYMBOL TABLE

# Register Number :212224040298

# Date :3.2.2026

# AIM:

To write a C program to implement a symbol table.

# ALGORITHM:

1. Start the program.
2. Get the input from the user with the terminating symbol ‘$’.
3. Allocate memory for the variable by dynamic memory allocation function.
4. If the next character of the symbol is an operator then only the memory is allocated.
5. While reading, the input symbol is inserted into symbol table along with its memory address.
6. The steps are repeated till ‘$’ is reached.
7. To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8. Stop the program.

# PROGRAM:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
	int i = 0, j = 0, x = 0, n, flag = 0,k;
	char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

	printf("Enter the Expression terminated by $: ");
	while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
		b[i++] = c;
	}
	b[i] = '\0';
	n = i - 1;

	printf("\nGiven Expression: %s\n", b);

	printf("\nSymbol Table\n");
	printf("Symbol\tType\t\tAddress\n");

	for (j = 0; j <= n; j++) {
		c = b[j];
		if (isalpha((unsigned char)c)) {
			int alreadyExists = 0;
			for (k = 0; k < x; k++) {
				if (d[k] == c) {
					alreadyExists = 1;
					break;
				}
			}

			if (!alreadyExists) {
				d[x] = c;
				printf("%c\tidentifier\t%p\n", c, (void*)&d[x]);
				x++;
			}
		}
	}

	// Clear input buffer
	while ((c = getchar()) != '\n' && c != EOF);

	printf("\nEnter the symbol to search: ");
	srch = getchar();

	for (i = 0; i < x; i++) {
		if (srch == d[i]) {
			printf("Symbol %c Found @ address %p\n", srch, (void*)&d[x]);
			flag = 1;
			break;
		}
	}
	if (flag == 0)
		printf("Symbol Not Found\n");

	return 0;
}
```
# OUTPUT:
![WhatsApp Image 2026-02-03 at 9 15 18 AM](https://github.com/user-attachments/assets/79bdff72-be6e-41ea-9f75-1b94c731a155)
![WhatsApp Image 2026-02-03 at 9 17 05 AM](https://github.com/user-attachments/assets/cfebad5f-8591-4bd7-acdc-ea0e46ae24d4)

# RESULT:

The program to implement a symbol table is executed and the output is verified.
