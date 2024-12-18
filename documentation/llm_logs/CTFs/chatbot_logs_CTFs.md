# Tests done on CTF (LevelsByMacaroni841)
## Tests done on non-stripped binaries.

### Conversation log 1
#### Round 1
**Input**:
```
explain what does this main function do in detail
```
**Decompiled Code (HLIL)**:
```
11c9 | int32_t main(int32_t argc, char** argv, char** envp)
11e4 | printf(\"Enter a string: \")
11fc | char buf_1
11fc | fgets(&buf_1, 0x28, __TMC_END__)
1208 | int32_t rax_1 = strlen(&buf_1)
1208 | 
1214 | if (rax_1 != 6)
1420 |     puts(\"FAILURE-LVL-1: how long is your \u2026\")
1214 | else
1224 |     puts(\"\\n\\n\\nLevel 1 Pass: String lengt\u2026\")
122f |     char var_47
122f |     
122f |     if (var_47 != 0x34)
140f |         puts(\"FAILURE-LVL-2: Maybe the program\u2026\")
122f |     else
123f |         puts(\"Level 2 Pass: the character is a\u2026\")
123f |         
124a |         if (buf_1 != 0x33)
13fe |             puts(\"I think if requires another char\u2026\")
124a |         else
125a |             puts(\"Level 2.5 Pass: You understand t\u2026\")
1269 |             puts(\"you will be prompted to enter a \u2026\")
1278 |             puts(\"The first key and the second key\u2026\")
128c |             printf(\"Enter string #2: \")
12a4 |             void buf
12a4 |             fgets(&buf, 0x28, __TMC_END__)
12a4 |             
12be |             if (strlen(&buf) != rax_1)
13ed |                 puts(\"The string length has to be the \u2026\")
12be |             else
130c |                 for (int32_t i = 0; i s<= 4; i += 1)
12f1 |                     if (*(&buf + i) - 0x30 != ((&buf_1)[i] - 0x30) * 2)
12fd |                         puts(\"FAILURE-LVL-2-Look through the l\u2026\")
1302 |                         break
1302 |                 
1318 |                 puts(\"SUCCESS-LVL-3: You Did it! i hop\u2026\")
1327 |                 puts(\"**i pray for the day crackmes.on\u2026\")
1336 |                 puts(\"If you havent done it before thi\u2026\")
1345 |                 puts(\"For the bonus section you need t\u2026\")
1354 |                 puts(\"When ready type a letter then pr\u2026\")
1368 |                 __isoc99_scanf(&data_2365)
1368 |                 
1374 |                 if (rax_1 != 0x1b39)
13be |                     puts(\"FAILURE-LVL-BONUS: Forcing you t\u2026\")
13cd |                     puts(\"Cutter is actually pretty good f\u2026\")
13dc |                     puts(\"Wowza! https://www.megabeets.net\u2026\")
1374 |                 else
1380 |                     puts(\"SUCCESS-LVL-BONUS: Well damn you\u2026\")
138f |                     puts(\"Should I make more of these?\")
139e |                     puts(\"Probably not with the yanderedev\u2026\")
13ad |                     puts(\"Bye! - saltedMacaroni841\")\n13ad | 
142b | return 0
```
**Output**:
```
The `main` function appears to be a multi-level challenge or validation routine. Here's a detailed breakdown:  
1. Input Prompt: 
The user is prompted to enter a string.\n\n  
2. Level 1 Check:
- The program reads a string into `buf_1` and checks its length.
- If the length is not 6, it prints a failure message for Level 1.
- If the length is 6, it proceeds to Level 2.
3. Level 2 Check;
- It checks if a specific character (`var_47`) is equal to `0x34`.
- If not, it prints a failure message for Level 2.
- If it is, it proceeds to Level 2.5.  
4. Level 2.5 Check:
- It checks if the first character of `buf_1` is `0x33`.
- If not, it prints a failure message.
- If it is, it proceeds to the next stage.  
5. Second Input Prompt:
- The user is prompted to enter a second string.  
6. Level 3 Check:
- It checks if the length of the second string matches the length of the first string.
- If not, it prints a failure message.
- If it matches, it performs a loop to check if each character of the second string, when adjusted, matches twice the corresponding character of the first string.
- If any character fails this check, it prints a failure message and breaks the loop.
- If all checks pass, it prints a success message for Level 3.  
7. Bonus Level Check:
- The user is prompted to enter a value.
- It checks if the length of the first string (`rax_1`) is `0x1b39`.
- If not, it prints a failure message for the bonus level.
- If it matches, it prints a success message for the bonus level.  
Finally, the function returns 0, indicating successful execution.
```
#### Round 2
**Input:**  
```
provide step by step instructions to solve this crackme
```

**Decompiled Code (HLIL):**  
`same as above`

**Output:**
```
Here's a step-by-step guide to solving this crackme based on the `main` function:

1. Level 1: String Length Check  
- Input a string with exactly 6 characters when prompted. This will pass the first check.
2. Level 2: Character Check   
- Ensure that the character at `var_47` is `0x34`. This might be a hardcoded value or a result of some operation. You may need to investigate how `var_47` is set or manipulated before this check.
3. Level 2.5: First Character Check   
- The first character of your input string (`buf_1`) should be `0x33`, which is the ASCII value for '3'. Start your string with '3'.
4. Level 3: Second String Input
- Enter a second string when prompted. Ensure the length of this string matches the first string (6 characters).
- For each character in the second string, ensure that when adjusted by subtracting `0x30`, it equals twice the corresponding character in the first string (also adjusted by `0x30`).
- This implies a mathematical relationship between the characters of the two strings.
5. Bonus Level: Length Check
- The program checks if the length of the first string (`rax_1`) is `0x1b39`. Since this is not possible with a 6-character string, this condition will always fail unless there's a specific manipulation or context not visible in the current decompilation.
6. General Tips   
- Use a debugger to step through the program and observe how variables are set and manipulated.
- Pay attention to any hardcoded values or operations that might affect the checks.
- Consider edge cases and how input might be transformed or validated.
By following these steps, you should be able to navigate through the levels of this 
crackme challenge.
```
### Conversation log 2
#### Round 1
**Input:**  
```
explain what does the main function do and elaborate in detail
```
**Decompiled code (LLIL):**
```
11c9 |  int32_t main(int32_t argc, char** argv, char** envp)
11cd |          push(rbp)
11ce |          rbp = rsp {__saved_rbp}
11d1 |          rsp = rsp - 0x70
11d5 |          rax = &data_2008
11dc |          rdi = rax
11df |          eax = 0
11e4 |          call(printf)
11e9 |          rdx = [&__TMC_END__].q
11f0 |          rax = rbp - 0x40 {buf_1}
11f4 |          esi = 0x28
11f9 |          rdi = rax {buf_1}
11fc |          call(fgets)
1201 |          rax = rbp - 0x40 {buf_1}
1205 |          rdi = rax {buf_1}
1208 |          call(strlen)
120d |          [rbp - 8 {var_10}].d = eax
1214 |          if ([rbp - 8 {var_10}].d != 6) then 17 @ 0x1416 else 21 @ 0x121a
1416 |          rax = &data_25c0
141d |          rdi = rax
1420 |          call(puts)
1420 |          goto 26 @ 0x1425
121a |          rax = &data_2020
1221 |          rdi = rax
1224 |          call(puts)
1229 |          eax = zx.d([rbp - 0x3f {var_47}].b)
122f |          if (al != 0x34) then 30 @ 0x1405 else 34 @ 0x1235
1425 |          eax = 0
142a |          rsp = rbp
142a |          rbp = pop
142b |          <return> jump(pop)
1405 |          rax = &data_2560
140c |          rdi = rax
140f |          call(puts)
1414 |          goto 26 @ 0x1425
1235 |          rax = &data_2050
123c |          rdi = rax
123f |          call(puts)
1244 |          eax = zx.d([rbp - 0x40 {buf_1}].b)
124a |          if (al != 0x33) then 39 @ 0x13f4 else 43 @ 0x1250
13f4 |          rax = &data_2518
13fb |          rdi = rax
13fe |          call(puts)
1403 |          goto 26 @ 0x1425
1250 |          rax = &data_2080
1257 |          rdi = rax
125a |          call(puts)
125f |          rax = &data_20b8
1266 |          rdi = rax
1269 |          call(puts)
126e |          rax = &data_2100
1275 |          rdi = rax
1278 |          call(puts)
127d |          rax = &data_2157
1284 |          rdi = rax
1287 |          eax = 0
128c |          call(printf)
1291 |          rdx = [&__TMC_END__].q
1298 |          rax = rbp - 0x70 {buf}
129c |          esi = 0x28
12a1 |          rdi = rax {buf}
12a4 |          call(fgets)
12a9 |          rax = rbp - 0x70 {buf}
12ad |          rdi = rax {buf}
12b0 |          call(strlen)
12b5 |          [rbp - 0xc {var_14_1}].d = eax
12b8 |          eax = [rbp - 0xc {var_14_1}].d
12be |          if (eax != [rbp - 8 {var_10}].d) then 67 @ 0x13e3 else 71 @ 0x12c4
13e3 |          rax = &data_24f0
13ea |          rdi = rax
13ed |          call(puts)
13f2 |          goto 26 @ 0x1425
12c4 |          [rbp - 4 {i}].d = 0
12cb |          goto 73 @ 0x130c
130c |          if ([rbp - 4 {i}].d s<= 4) then 74 @ 0x12cd else 86 @ 0x130e
12cd |          eax = [rbp - 4 {i}].d
12d0 |          rax = sx.q(eax)
12d2 |          eax = zx.d([rbp + rax - 0x70].b)
12d7 |          eax = sx.d(al)
12da |          edx = (rax - 0x30).d
12dd |          eax = [rbp - 4 {i}].d
12e0 |          rax = sx.q(eax)
12e2 |          eax = zx.d([rbp + rax - 0x40].b)
12e7 |          eax = sx.d(al)
12ea |          eax = eax - 0x30
12ed |          eax = eax + eax
12f1 |          if (edx == eax) then 106 @ 0x1304 else 108 @ 0x12f3
130e |          rax = &data_21d0
1315 |          rdi = rax
1318 |          call(puts)
131d |          rax = &data_2210
1324 |          rdi = rax
1327 |          call(puts)
132c |          rax = &data_2268
1333 |          rdi = rax
1336 |          call(puts)
133b |          rax = &data_22c0
1342 |          rdi = rax
1345 |          call(puts)
134a |          rax = &data_2320
1351 |          rdi = rax
1354 |          call(puts)
1359 |          rax = &data_2365
1360 |          rdi = rax
1363 |          eax = 0
1368 |          call(__isoc99_scanf)
1374 |          if ([rbp - 8 {var_10}].d != 0x1b39) then 112 @ 0x13b4 else 122 @ 0x1376
1304 |          [rbp - 4 {i}].d = [rbp - 4 {i}].d + 1
1304 |          goto 73 @ 0x130c
12f3 |          rax = &data_2170
12fa |          rdi = rax
12fd |          call(puts)
1302 |          goto 86 @ 0x130e
13b4 |          rax = &data_2430
13bb |          rdi = rax
13be |          call(puts)
13c3 |          rax = &data_2480
13ca |          rdi = rax
13cd |          call(puts)
13d2 |          rax = &data_24a8
13d9 |          rdi = rax
13dc |          call(puts)
13e1 |          goto 26 @ 0x1425
1376 |          rax = &data_2368
137d |          rdi = rax
1380 |          call(puts)
1385 |          rax = &data_2390
138c |          rdi = rax
138f |          call(puts)
1394 |          rax = &data_23b0
139b |          rdi = rax
139e |          call(puts)
13a3 |          rax = &data_2415
13aa |          rdi = rax
13ad |          call(puts)
13b2 |          goto 26 @ 0x1425" 
```
**Output:**
```
The main function performs several operations, primarily involving user input and conditional checks. Here's a detailed breakdown:
Setup and Initialization: 
The function sets up the stack frame and reserves space for local variables.
It initializes a buffer and prepares for input operations.
Input Handling:
It uses fgets to read a string from the standard input into a buffer (buf_1).
The length of the input string is calculated using strlen.
Conditional Checks:
The function checks if the length of the input string is 6. If not, it prints a message from data_25c0 and exits.
It checks if the first character of the input is '4'. If not, it prints a message from data_2560 and exits.
It checks if the second character of the input is '3'. If not, it prints a message from data_2518 and exits.
Further Input and Validation:
If the initial checks pass, it prints several messages and prompts for another input using fgets.
It compares the length of this new input with the previous input length. If they don't match, it prints a message from data_24f0 and exits.
Loop and Arithmetic Check:
A loop iterates over the first five characters of the new input.
For each character, it performs arithmetic operations and checks if a condition holds. If any check fails, it prints a message from data_2170 and exits.
Final Validation:
If all checks pass, it performs a final comparison with a specific value (0x1b39). If this fails, it prints several messages and exits.
If successful, it prints a series of messages indicating success.
The function involves multiple input checks and validations, likely as part of a challenge or verification process.
```
