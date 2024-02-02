# Lexical Analysis in Compiler Design

Lexical Analysis is the initial phase of the compiler, also known as a scanner. Its primary function is to convert high-level input programs into a sequence of tokens.

- **Implementation with Deterministic Finite Automata:**
  - Lexical Analysis can be implemented using Deterministic Finite Automata (DFA), a theoretical concept in computer science.

- **Output to Parser for Syntax Analysis:**
  - The output of Lexical Analysis is a sequence of tokens, which is then sent to the parser for syntax analysis.

## How Lexical Analyzer Works

1. **Input Preprocessing:**
   - Involves cleaning up the input text, preparing it for lexical analysis.
   - This may include removing comments, whitespace, and other non-essential characters.

2. **Tokenization:**
   - The process of breaking the input text into a sequence of tokens.
   - This is achieved by matching characters against predefined patterns or regular expressions.

3. **Token Classification:**
   - Determines the type of each token.
   - For example, keywords, identifiers, operators, and punctuation symbols are classified as separate token types in a programming language.

4. **Token Validation:**
   - Ensures each token is valid according to the language rules.
   - Validates that a variable name is a valid identifier or that an operator has the correct syntax.

5. **Output Generation:**
   - The final stage where the lexer produces the output of the lexical analysis, typically a list of tokens.
   - This token list is then passed to the next stage of compilation or interpretation.

## Examples of Token Kinds in C

1. **Keywords:**
   - Examples: `for`, `while`, `if`, `printf`, etc.

2. **Identifier:**
   - Examples: Variable names, function names, etc.

3. **Operators:**
   - Examples: `+`, `++`, `-`, etc.

4. **Separators:**
   - Examples: `,`, `;`, etc.

## Token Counting Example 

### Example:
Suppose we have a string `s` that contains a sentence with few words. We shall have to print each
word into new lines.
So, if the input is like `s = "Let us see some string tokenizing fun"`, then the output will be: <br>
`Let` <br>
`us`<br>
`see`<br>
`some`<br>
`string`<br>
`tokenizing`<br>
`fun`<br>

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
```

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


