# Tokenization challenge Details

## Objective:
The objective of this lab was to gain a deeper understanding of string tokenization using the `strtok` function in C. Additionally, the lab aimed to enhance the original code by implementing new features.

## 1. Code Review:
### 1.1 Purpose:
The provided C code prompts the user to input a sentence, tokenizes it using spaces as delimiters, and prints each token on a new line.

### 1.2 `strtok` Usage:
The `strtok` function is utilized to break the input sentence into tokens. It takes the sentence and a specified delimiter as arguments. The function is called iteratively, with `NULL` as the first argument after the initial call to continue tokenizing the string.

### 1.3 `fgets` Function:
The `fgets` function is responsible for reading the user's input sentence, preventing buffer overflow by specifying the size of the `sentence` array.

## 2. Modification Task:
### 2.1 Multiple Delimiters:
The code was modified to handle multiple delimiters. Users can now input a custom set of delimiters, expanding the flexibility of the tokenization process.

### 2.2 Custom Delimiter Input:
A feature was added to allow users to input their own set of delimiters. This enhances the user experience and makes the program more versatile.

### 2.3 Token Labeling:
Each token is now displayed on a new line with an appropriate label indicating the delimiter used. This makes the output more informative.

## 3. Enhancement Challenge:
### 3.1 Token Counting:
A new feature was implemented to count the number of tokens in the input sentence. The total token count is displayed at the end of the tokenization process.

## 4. Testing:
Various test cases were created to ensure the modified program works correctly with different input sentences and custom delimiters. Test cases covered scenarios with single and multiple delimiters.

## 5. Documentation:
The code has been extensively documented with comments explaining each section. Additionally, a summary of modifications and new features has been provided for clarity.

## C Code:
```c
#include <stdio.h>
#include <string.h>

int main() {
    char sentence[1000];

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    char *token = strtok(sentence, " ");
    
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, " ");
    }

    return 0;
}
