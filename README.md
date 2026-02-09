# Os-assignment-3
```
# Sequence Generator Command-Line Tool in C

## 📌 Objective
Create a command-line tool in **C** that generates a sequence of numbers based on user input.

The user provides:
- Start value
- End value
- Optional step value

If step is not provided, it defaults to **1**.

---

## 📌 Program Behavior

### Case 1: Two arguments
```

./seq start end

```
Sequence is generated using default step = 1.

Example:
```

./seq 1 5
Output: 1 2 3 4 5

```

---

### Case 2: Three arguments
```

./seq start end step

```
Sequence uses given step.

Example:
```

./seq 2 10 2
Output: 2 4 6 8 10

```

---

### Case 3: Negative step
Sequence decreases.

Example:
```

./seq 10 1 -1
Output: 10 9 8 7 6 5 4 3 2 1

```

---

## 📌 Error Conditions
Display error when:

1. Step value is **0**
2. Start > End and step is positive
3. Start < End and step is negative
4. Wrong number of arguments

Example:
```

./seq 1 5 -1
Error: Invalid step direction.

````

---

## 📌 Algorithm (Simple Explanation)

1. Read command-line arguments.
2. Convert inputs to integers.
3. Set default step = 1 if not provided.
4. Validate inputs.
5. Use loop:
   - Increment if step positive.
   - Decrement if step negative.
6. Print sequence.

---

## 📌 Simple C Program

```c
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char *argv[]) {
    int start, end, step = 1;

    if (argc < 3 || argc > 4) {
        printf("Usage: ./seq start end [step]\n");
        return 1;
    }

    start = atoi(argv[1]);
    end = atoi(argv[2]);

    if (argc == 4)
        step = atoi(argv[3]);

    if (step == 0) {
        printf("Error: Step cannot be zero.\n");
        return 1;
    }

    if ((start < end && step < 0) ||
        (start > end && step > 0)) {
        printf("Error: Invalid step direction.\n");
        return 1;
    }

    if (step > 0) {
        for (int i = start; i <= end; i += step)
            printf("%d ", i);
    } else {
        for (int i = start; i >= end; i += step)
            printf("%d ", i);
    }

    printf("\n");
    return 0;
}
````

---

## 📌 Compilation & Execution

Compile:

```
gcc seq.c -o seq
```

Run:

```
./seq 1 5
./seq 2 10 2
./seq 10 1 -1
```

---

## 📌 Learning Outcomes

Students learn:

* Command-line arguments in C
* atoi() conversion
* Loop control
* Input validation
* Basic CLI tool creation


```


```
**shell script** that prints a student's **name and roll number**.

Students can create it using their roll number as the file name.

---

## ✅ Simple Shell Script

### Step 1: Create file

Example roll number: **CSE106**

```bash
nano CSE106.sh
```

---

### Step 2: Write script

```bash
#!/bin/bash

echo "Student Name: Rahul Sharma"
echo "Roll Number: CSE106"
```

(Students replace with their own details.)

---

### Step 3: Save file

In nano:

```
CTRL + X
Press Y
Press Enter
```

---

### Step 4: Give permission

```bash
chmod +x CSE106.sh
```

---

### Step 5: Run script

```bash
./CSE106.sh
```

Output example:

```
Student Name: Rahul Sharma
Roll Number: CSE106
```

---

## ✅ Classroom Version (One-line Script)

Students can also write:

```bash
#!/bin/bash
echo "Name: Rahul | Roll: CSE106"
```

---

