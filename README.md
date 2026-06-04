# Sorting of numbers in a sequence
## Exp 3 (a) : Ascending Order
## Aim :
To write and execute an 8085 program to sort a set of numbers in ascending order.
## Apparatus Required:
•	8085 Online Simulator (8085simulator.github.io or similar)
<br>•	Test input data
<br>•	Instruction set reference
## Algorithm (Ascending Order):
1.	Load count from memory into register C.
2.	Subtract 1 from count and store in B (outer loop counter).
3.	Outer loop (B times):
<br>Point HL to the first data.
<br>Copy C to D (inner loop counter).
<br>Inner loop (D times):
<br>Compare adjacent elements.
<br>If current > next, swap them.
<br>Decrement B and repeat.
4.	End.
## Program:
```
; Input : 2 numbers at 8050H and 8051H
; Output: Sorted in same locations

LXI H,8050H   ; HL -> first number
MOV A,M       ; A = first
INX H         ; HL -> second
CMP M         ; Compare A with second
JC END        ; If first < second → already sorted

; Swap
MOV D,M       ; D = second
MOV M,A       ; Put first into [8051H]
DCX H         ; Back to first
MOV M,D       ; Put second into [8050H]

END: HLT
```
## Output:
<img width="1905" height="893" alt="Screenshot 2025-08-31 205611" src="https://github.com/user-attachments/assets/b9af253a-9a68-4b75-bdb7-d02c695e4d06" />



## Result:
The 8085 assembly language program was successfully executed to sort a set of numbers in ascending order.

## Exp 3 (b) : Descending Order
## Aim:
To write and execute an 8085 program to sort a set of numbers in descending order.
## Apparatus Required:
•	8085 Online Simulator
•	Hex input data
•	Instruction set reference
## Algorithm (Descending Order):
1.	Load the count of numbers from memory into register C.
2.	Subtract 1 from count and store in B.
3.	Outer loop (B times):
<br>Point HL to first number.
<br>Copy count to D.
<br>Inner loop (D times):
<br>Compare adjacent numbers.
<br>If current < next, swap them.
4. Repeat until sorted.
## Program:
```
; Input : 2 numbers at 8050H and 8051H
; Output: Sorted (descending) in same locations

LXI H,8050H   ; HL -> first number
MOV A,M       ; A = first
INX H         ; HL -> second
CMP M         ; Compare A with second
JNC END       ; If A >= second → already descending

; Swap
MOV D,M       ; D = second
MOV M,A       ; Put first into [8051H]
DCX H         ; Back to first
MOV M,D       ; Put second into [8050H]

END: HLT
```
## Output: 
<img width="1918" height="897" alt="Screenshot 2025-08-31 210854" src="https://github.com/user-attachments/assets/190702d4-f68d-4b19-80b6-338082c52337" />

## Result:
The 8085 assembly language program was successfully executed to sort a set of numbers in descending order.
