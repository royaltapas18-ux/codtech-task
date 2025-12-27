#include <stdio.h>
#include <ctype.h>
#include <string.h>

/* List of keywords */
char keywords[10][10] = {
    "int","float","if","else","while",
    "for","return","char","void","main"
};

/* Check if word is keyword */
int isKeyword(char word[]) {
    for (int i = 0; i < 10; i++)
        if (strcmp(word, keywords[i]) == 0)
            return 1;
    return 0;
}

int main() {
    FILE *fp;
    char ch, buffer[20];
    int i = 0;

    fp = fopen("input.c", "r");   // Input C file
    if (fp == NULL) {
        printf("File not found\n");
        return 0;
    }

    while ((ch = fgetc(fp)) != EOF) {
        if (isalnum(ch)) {
            buffer[i++] = ch;     // Store characters
        } else {
            buffer[i] = '\0';     // End word
            i = 0;

            if (isKeyword(buffer))
                printf("Keyword: %s\n", buffer);
            else if (isalpha(buffer[0]))
                printf("Identifier: %s\n", buffer);

            if (ch == '+' || ch == '-' || ch == '*' || ch == '/')
                printf("Operator: %c\n", ch);
        }
    }
    fclose(fp);
    return 0;
}
