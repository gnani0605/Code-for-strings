# Code-for-strings    
#include <stdio.h>
#include <string.h>
#include <stdbool.h>
void rev(char* s) {
    char t[100];
    int len = strlen(s);
    int i = 0;
    while (len > 0) t[i++] = s[len-- - 1];
    t[i] = '\0';
    strcpy(s, t);
}

bool isPalindrome(char* s) {
    int len = strlen(s);
    for (int i = 0; i < len / 2; i++) {
        if (s[i] != s[len - i - 1]) {
            return false;
        }
    }
    return true;
}

int main() {
    char s[100], b[100],res[100];
    int c;
    scanf("%s", s);
    scanf("%s", b);
    c = strcmp(s, b);

    if (c == 0) {
        printf("%d\n", strlen(s));
        strcpy(res, s);
        rev(s);
        printf("%s\n", s);
        strcat(s, res);
        printf("%s\n",s);
    }
    else {
        strcat(s, b); 
        printf("%s\n", s); 
        strcpy(res, s);
        rev(s);
        printf("%s\n", s);
        strcat(s,res);
        printf("%s\n",s);
    }

    if (isPalindrome(s)) {
        printf("The %s is a palindrome.\n",s);
    } else {
        printf("The %s is not a palindrome.\n",s);
    }

    return 0;
}
