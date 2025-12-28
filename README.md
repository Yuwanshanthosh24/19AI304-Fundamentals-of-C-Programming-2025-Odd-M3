# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
# Date : 27/11/2025
# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:
```
#include <stdio.h>

int main()
{
    int num, rem, i = 0;
    int binary[32]; // Array to store binary digits (32 bits for safety)

    // Step 4: Read decimal number
    printf("Enter a decimal number: ");
    scanf("%d", &num);

    // Handle the special case when num is 0
    if (num == 0)
    {
        printf("Binary: 0\n");
        return 0;
    }

    int temp = num; // Store original number for display

    // Step 6: Convert decimal to binary
    while (num > 0)
    {
        rem = num % 2;
        binary[i] = rem;
        i++;
        num = num / 2;
    }

    // Step 7: Display binary digits in reverse order
    printf("Binary of %d is: ", temp);
    for (int k = i - 1; k >= 0; k--)
    {
        printf("%d", binary[k]);
    }
    printf("\n");

    return 0;
}
```
# Output:
<img width="398" height="272" alt="image" src="https://github.com/user-attachments/assets/37a0e5d3-5737-4159-868a-6011a1f735ae" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Date:27/11/2025
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
# Date : 
# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row `i` from `0` to `m−1`:
- **Step 7.1:** Set `min` as the first element of the row.  
- **Step 7.2:** Scan the row to find its minimum element and store its position in `pos[0]`.  
- **Step 7.3:** Let `j` be the column of this minimum element.  
- **Step 7.4:** Set `max` as the first element of column `j`.  
- **Step 7.5:** Scan column `j` to find its maximum element and store its position in `pos[1]`.  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If `min == max` **and their positions match**, then the element is a **saddle point**.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:
```
#include <stdio.h>

int main()
{
    int i, j, k, m;
    int min, max;
    int pos[2]; // pos[0] = row, pos[1] = column
    int flag = 0; // To check if saddle point exists

    // Step 4: Read order of square matrix
    printf("Enter the order of the square matrix: ");
    scanf("%d", &m);

    int matrix[m][m];

    // Step 5: Read matrix elements
    printf("Enter the elements of the matrix:\n");
    for (i = 0; i < m; i++)
    {
        for (j = 0; j < m; j++)
        {
            scanf("%d", &matrix[i][j]);
        }
    }

    // Step 6: Display the matrix
    printf("The matrix is:\n");
    for (i = 0; i < m; i++)
    {
        for (j = 0; j < m; j++)
        {
            printf("%d\t", matrix[i][j]);
        }
        printf("\n");
    }

    // Step 7: Find saddle point
    for (i = 0; i < m; i++)
    {
        // Step 7.1: Set min as first element of the row
        min = matrix[i][0];
        pos[1] = 0; // Column of min

        // Step 7.2: Find minimum in the row
        for (j = 1; j < m; j++)
        {
            if (matrix[i][j] < min)
            {
                min = matrix[i][j];
                pos[1] = j;
            }
        }

        // Step 7.4: Set max as first element of the column
        max = matrix[0][pos[1]];

        // Step 7.5: Find maximum in the column
        for (k = 1; k < m; k++)
        {
            if (matrix[k][pos[1]] > max)
            {
                max = matrix[k][pos[1]];
                pos[0] = k;
            }
        }

        // Step 8: Check if min equals max and positions match
        if (min == max && pos[0] == i)
        {
            printf("Saddle point found: %d at position (%d, %d)\n", min, i, pos[1]);
            flag = 1;
            break; // If only one saddle point is required
        }
    }

    if (flag == 0)
        printf("No saddle point found in the matrix.\n");

    return 0;
}
```
# Output:
<img width="535" height="400" alt="image" src="https://github.com/user-attachments/assets/116a8bba-3593-4d6c-80a5-1c35af5e1c8f" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Date:27/11/2025
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
# Date : 
# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: `s` to store the input string and `d` to store the reversed string.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]s", s);`
### Step 5: 
  Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.
### Step 6: 
  Initialize a counter `j` for the reversed string.
### Step 7: 
  Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string `d` with the null character `'\0'`.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:
```
#include <stdio.h>

int main()
{
    char s[100], d[100]; // s = original string, d = reversed string
    int i, j, length = 0;

    // Step 4: Read the string (including spaces)
    printf("Enter a string: ");
    scanf("%[^\n]s", s);

    // Step 5: Find length of the string
    while (s[length] != '\0')
    {
        length++;
    }

    // Step 6: Initialize counter for reversed string
    j = 0;

    // Step 7: Copy characters in reverse order
    for (i = length - 1; i >= 0; i--)
    {
        d[j] = s[i];
        j++;
    }

    // Step 8: Terminate the reversed string
    d[j] = '\0';

    // Step 9: Print the reversed string
    printf("Reversed string: %s\n", d);

    return 0;
}
```
# Output:
<img width="355" height="276" alt="image" src="https://github.com/user-attachments/assets/b2453be1-2f5c-406b-a58e-42362bb225e5" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC

# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
# Date : 27/11/2025
# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]", s);`
### Step 5: 
  Calculate the length of the string using `strlen(s)` and store it in `n`.
### Step 6: 
 For each character `s[i]` in the string (from `i = 0` to `n - 1`):
 - If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  
  - Initialize `count = 0`.  
  - Loop through the string again and increment `count` for every occurrence of `s[i]`.  
  - Print `s[i]` and its count.  
  - Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:
```
#include <stdio.h>
#include <string.h>

int main()
{
    char s[100];
    int visited[256] = {0}; // To mark counted characters
    int i, j, n, count;

    // Step 4: Read the string
    printf("Enter a string: ");
    scanf("%[^\n]", s);

    // Step 5: Calculate length
    n = strlen(s);

    // Step 6: Count frequency of each character
    printf("Character frequencies:\n");
    for (i = 0; i < n; i++)
    {
        if (visited[(unsigned char)s[i]] == 0) // If not yet counted
        {
            count = 0;
            for (j = 0; j < n; j++)
            {
                if (s[i] == s[j])
                    count++;
            }
            printf("%c: %d\n", s[i], count);
            visited[(unsigned char)s[i]] = 1; // Mark as counted
        }
    }

    return 0;
}

```
# Output:
<img width="451" height="395" alt="image" src="https://github.com/user-attachments/assets/4953f869-ee03-4f85-8742-d4d0ca62285b" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Date: 27/11/2025
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Date : 
# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `str` to store the input string and a 2D array `words` to store individual words.
### Step 4: 
  Read the input string using `scanf("%[^\n]s", str);`
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to `'\0'`.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:
```
#include <stdio.h>
#include <string.h>

int main()
{
    char str[200];
    char words[50][50]; // Supports up to 50 words of 50 chars each
    int i = 0, j = 0, k = 0, wordCount = 0;

    // Step 4: Read input string
    printf("Enter a string: ");
    scanf("%[^\n]s", str);

    // Step 5: Split string into words
    while (str[i] != '\0')
    {
        if (str[i] != ' ')
        {
            words[wordCount][j++] = str[i];
        }
        else
        {
            if (j != 0) // End of a word
            {
                words[wordCount][j] = '\0';
                wordCount++;
                j = 0;
            }
        }
        i++;
    }
    if (j != 0) // Last word
    {
        words[wordCount][j] = '\0';
        wordCount++;
    }

    // Step 6: Remove duplicates
    for (i = 0; i < wordCount; i++)
    {
        if (words[i][0] == '\0') // Already marked
            continue;
        for (j = i + 1; j < wordCount; j++)
        {
            if (strcmp(words[i], words[j]) == 0)
            {
                words[j][0] = '\0'; // Mark duplicate
            }
        }
    }

    // Step 7: Print unique words
    printf("String with unique words: ");
    for (i = 0; i < wordCount; i++)
    {
        if (words[i][0] != '\0')
            printf("%s ", words[i]);
    }
    printf("\n");

    return 0;
}

```
# Output:
<img width="375" height="316" alt="image" src="https://github.com/user-attachments/assets/c2c72d81-53cd-494c-b256-8810f814dc6c" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

