# session-10

### Task 1: String Declaration & Length using `strlen()`

```c
#include <stdio.h>
#include <string.h>

int main() {
    // Declare and initialize string variable
    char songTitle[] = "Tum Hi Ho";

    // strlen() calculates the number of characters excluding the null terminator '\0'
    size_t length = strlen(songTitle);

    printf("Song Title : %s\n", songTitle);
    printf("Length     : %zu characters\n", length);

    return 0;
}

```

---

### Task 2: Compare Two Usernames using `strcmp()`

`strcmp()` returns `0` if two strings are identical:

```c
#include <stdio.h>
#include <string.h>

int main() {
    char username1[50];
    char username2[50];

    printf("Enter first username: ");
    scanf("%49s", username1);

    printf("Enter second username: ");
    scanf("%49s", username2);

    // strcmp returns 0 when strings match completely
    if (strcmp(username1, username2) == 0) {
        printf("Result: The usernames are identical.\n");
    } else {
        printf("Result: The usernames are different.\n");
    }

    return 0;
}

```

---

### Task 3: Copying a String using `strcpy()`

```c
#include <stdio.h>
#include <string.h>

int main() {
    const char source[] = "Flipkart";

    // Allocate sufficient memory (source length + 1 byte for '\0')
    char shoppingApp[20];

    // Copy source string into destination
    strcpy(shoppingApp, source);

    printf("Value of shoppingApp: %s\n", shoppingApp);

    return 0;
}

```

---

### Task 4: Username Generator (First 5 Characters / Full Name)

```c
#include <stdio.h>
#include <string.h>

int main() {
    char fullName[100];
    char username[6]; // Buffer for up to 5 characters + null terminator '\0'

    printf("Enter your full name: ");
    // Read input until newline
    scanf(" %[^\n]", fullName);

    if (strlen(fullName) <= 5) {
        // If shorter than or equal to 5 characters, copy the full name directly
        strcpy(username, fullName);
    } else {
        // Create a temporary string containing the first 5 characters
        char temp[6];
        for (int i = 0; i < 5; i++) {
            temp[i] = fullName[i];
        }
        temp[5] = '\0'; // Manually terminate the slice

        // Copy the sliced result into username using strcpy
        strcpy(username, temp);
    }

    printf("Generated Username: %s\n", username);

    return 0;
}

```
