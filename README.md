# Arithmetic-operation-using-8086
# 8086 Assembly Language Programs for Arithmetic Operations

## AIM

To write and execute Assembly Language Programs to perform arithmetic operations for the 8086 microprocessor.

---

## APPARATUS REQUIRED

* Personal Computer with MASM Software

---

## 1. ADDITION

#### Algorithm

1. Initialize memory location in HL register.
2. Store 1st data.
3. Increment HL to enter 2nd data.
4. Move 2nd number to accumulator.
5. Decrement HL.
6. Add value in memory with accumulator.
7. Store result.
8. Stop.


## FLOW CHART
<img width="707" height="1024" alt="image" src="https://github.com/user-attachments/assets/b5a7062d-e294-47cd-9683-a40de25e82de" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
ADD AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | -------------------------|
|  2000                   |  12                      |
|  2001                   |  34                      |
|  2002                   |  12                      | 
|  2003                   |  34                      |

| MEMORY LOCATION (INPUT) | DATA (OUTPUT)             |
| ----------------------- | ------------------------- |
|  2004                   |  68                       |
|  2005                   |  24                       |
|  2006                   |  00                       | 

#### Manual Calculation
![WhatsApp Image 2025-09-22 at 08 55 17_fc1867b1](https://github.com/user-attachments/assets/e53c55cd-80e9-4658-9f0a-978eea477d6d)



---

## OUTPUT IMAGE FROM MASM SOFTWARE
![WhatsApp Image 2025-09-22 at 07 32 24_0e03d0e0](https://github.com/user-attachments/assets/8e7a6f2d-04b2-4750-a610-d75d8fd260b7)


## 2. SUBTRACTION

#### Algorithm

1. Initialize memory and store 1st data.
2. Increment to get 2nd data.
3. Move 2nd data to accumulator.
4. Subtract memory content.
5. Store result.

## FLOWCHART

<img width="578" height="797" alt="image" src="https://github.com/user-attachments/assets/564c3c7a-33ce-4a1c-8920-beb5c24b9b47" />


#### Program
```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV CL,00H
MOV AX,[SI]
MOV BX,[SI+02H]
SUB AX,BX
JNC L1
INC CL
L1:
MOV [SI+04H],AX
MOV [SI+06H],CL
MOV AH,4CH
INT 21H
CODE ENDS
END
```


#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
|  2000                   | 57                       |
|  2001                   | 79                       |
|  2002                   | 26                       |
|  2003                   | 35                       |

| MEMORY LOCATION (INPUT) | DATA (OUTPUT)             |
| ----------------------- | ------------------------- |
|  2004                   |  31                       | 
|  2005                   |  44                       |
|  2006                   |  00                       | 


#### Manual Calculations

![WhatsApp Image 2025-09-22 at 08 56 04_70c2ab61](https://github.com/user-attachments/assets/8de23819-4999-4fd9-8c23-c9f35f28e394)


---


## OUTPUT SCREEN FROM MASM SOFTWARE
![WhatsApp Image 2025-09-22 at 07 53 10_0ed622a3](https://github.com/user-attachments/assets/c8955f19-f887-465f-8729-be33e89ecb18)


## 3. MULTIPLICATION

#### Algorithm

1. Initialize memory and store operands.
2. Move operands to registers.
3. Multiply.
4. Store result.

##FLOWCHART

<img width="569" height="906" alt="image" src="https://github.com/user-attachments/assets/88be88ff-2896-4a88-b73d-84ccffd2fcf9" />



#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
MUL BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) |  DATA (OUTPUT)           |
| ----------------------- | ------------------------ |
|  2000                   | 12                       |
|  2001                   | 34                       |
| 2002                    | 12                       |
| 2003                    | 34                       |

| MEMORY LOCATION (INPUT) | DATA (OUTPUT)             |
| ----------------------- | ------------------------- |
|  2004                   |  90                       |
|  2005                   |  5A                       |
|  2006                   |  4B                       | 

#### Manual Calculations

![WhatsApp Image 2025-09-22 at 08 58 02_fc281d15](https://github.com/user-attachments/assets/36c533fa-4eba-4219-9678-f1639b126a4e)


---

## OUTPUT SCREEN FROM MASM SOFTWARE
![WhatsApp Image 2025-09-22 at 08 05 42_9cafe9ce](https://github.com/user-attachments/assets/e4589f9e-2d27-4503-b7a7-cea879bf523f)


## 4. DIVISION

#### Algorithm

1. Load memory location of operands.
2. Perform division.
3. Store result.

   ## FLOWCHART
<img width="1065" height="802" alt="image" src="https://github.com/user-attachments/assets/25b4a483-0d42-494b-8639-1af3ea17191b" />


#### Program

```asm
CODE SEGMENT
ASSUME CS: CODE, DS: CODE
ORG 1000H
MOV SI,2000H
MOV DX,0000H
MOV AX,[SI]
MOV BX,[SI+02H]
DIV BX
MOV [SI+04H],AX
MOV [SI+06H],DX
MOV AH,4CH
INT 21H
CODE ENDS
END
```

#### Output Table

| MEMORY LOCATION (INPUT) | DATA (INPUT)             |
| ----------------------- | ------------------------ |
| 2000                    |   70                     |
| 2001                    |   25                     |
| 2002                    |   35                     |
| 2003                    |   12                     |

| MEMORY LOCATION (INPUT) | DATA (OUTPUT)             |
| ----------------------- | ------------------------- |
|  2004                   |  00                       |
|  2005                   |  02                       |
|  2006                   |  01                       | 


#### Manual Calculations

![WhatsApp Image 2025-09-22 at 08 58 09_80699d80](https://github.com/user-attachments/assets/4dd149f1-d5ff-4b20-8206-68f1b86b3c56)


---
## OUTPUT FROM MASM SOFTWARE
![WhatsApp Image 2025-09-22 at 09 00 42_49502f68](https://github.com/user-attachments/assets/b97c706d-659e-4d91-9f21-37571b10812b)



## RESULT

Thus, the Assembly Language Programs for 8086 to perform arithmetic operations (Addition, Subtraction, Multiplication, and Division) using both direct and indirect methods were successfully written and executed using MASM.

