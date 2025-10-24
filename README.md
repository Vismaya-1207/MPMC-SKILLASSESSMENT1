# MPMC-SKILL ASSESSMENT 1

## Aim
To write and execute  an assembly language program in 8051 to check whether a given  number is a palindrome or not.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software

## Theory 
A palindrome number reads the same forwards and backwards (e.g., 121, 1331).In 8051 Assembly, we can check for palindrome by:

1.Taking the number from memory (or accumulator).

2.Reversing the number (extracting digits using division and modulo by 10).

3.Comparing the reversed number with the original.

4.Displaying result (using a flag or storing it in memory).



## Algorithm
```
A number is a palindrome if it reads the same forwards and backwards (e.g., 1221)
1.Store the number in internal RAM.
2.Start pointer → first digit
3.End pointer → last digit
4.Compare digits at start and end:
5.If equal → move pointers inward
6.If not equal → number is not a palindrome
7.Repeat until all digit pairs are checked.
8.If all pairs match → number is palindrome.
9.Use registers R0 and R1 for start and end pointers.
10.Use R2 as comparison counter.
11.Store the result in internal RAM (01H = palindrome, 00H = not palindrome).

```
## Program
```
ORG 0000H       
START:          
MOV R0, #30H      
    MOV R1, #33H      
    MOV R2, #02        

CHECK_LOOP:
    MOV A, @R0        
    MOV B, @R1        
    CJNE A, B, NOTPAL 
    INC R0            
    DEC R1            
    DJNZ R2, CHECK_LOOP 

PAL:
    MOV 38H, #01      
    SJMP END_PROGRAM

NOTPAL:
    MOV 38H, #00      

END_PROGRAM:
    SJMP END_PROGRAM  

END
```
## Output
## 1.PALINDROME
<img width="742" height="367" alt="image" src="https://github.com/user-attachments/assets/f891aaa8-25c9-438c-9989-7de237db4209" />

<img width="748" height="413" alt="image" src="https://github.com/user-attachments/assets/b09087cd-a2e5-46a8-aed0-c126d0f98305" />

## 2.NOT PALINDROME
<img width="806" height="291" alt="image" src="https://github.com/user-attachments/assets/0dbf6a37-1c25-4ddd-9077-51bb72035b09" />

<img width="690" height="362" alt="image" src="https://github.com/user-attachments/assets/f13944df-3206-403b-9ed4-7053ad21048e" />

## Result

Thus the program to execute whether a number is palindrome or not and thus the output was shown.
