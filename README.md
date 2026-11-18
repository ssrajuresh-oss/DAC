# DAC
 INTERFACING DAC WITH 8086 KIT AND GENERATING SAWTOOTH AND SQUARE WAVEFORMS

## AIM
To write an assembly language program in 8086 to generate Sawtooth and Square waveforms using DAC.

---
 
## APPARATUS REQUIRED

| S. No | Item              | Specification   | Quantity |
|-------|------------------|-----------------|----------|
| 1     | Microprocessor kit | 8086            | 1        |
| 2     | Power Supply      | +5 V DC, +12 V DC | 1      |
| 3     | DAC Interface board | -              | 1        |

---

## ALGORITHM

### Measurement of Analog Voltage
1. Send the digital value to DAC.  
2. Read the corresponding analog value at its output.  

### Waveform Generation

#### Square Waveform
1. Send low value (00) to the DAC.  
2. Introduce suitable delay.  
3. Send high value to DAC.  
4. Introduce delay.  
5. Repeat the above procedure.  

#### Sawtooth Waveform
1. Load low value (00) to accumulator.  
2. Send this value to DAC.  
3. Increment the accumulator.  
4. Repeat step (ii) and (iii) until accumulator value reaches FF.  
5. Repeat the above procedure from step 1.  

---

## PROGRAMS

# 8086 Assembly Programs – DAC Interfacing

## Program: Square Wave

| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1000            | MOV AL,00H  | Load 00H in Accumulator           |
| 1003            |  OUT 0C8H,AL | Send through output port         |
| 1005            |  CALL DELAY(1100)  | CALL PROGRAM TO 1100      |
| 1008            |  MOV AL,0FFH |   Load 00H in Accumulator       |
| 100A            |   OUT 0C8H,AL|  Send through output port       |
| 100D            |  CALL DELAY(1100) | CALL PROGRAM TO 1100       |


| Memory Location | Program     | Comments                          |
|-----------------|-------------|-----------------------------------|
| 1100            | MOV CX,0505  | Load 0505H in Accumulator           |
| 1103            |  DEC CX | Decrement CX        |
| 1105           |  JNZ 1104  | RPEAT UNTILL ZERO      |
| 1108            |   RET |   RETURN TO MAIN PROGRAM      |


# Program: Sawtooth wave

## Assembly Program

| Memory Location | Program Instruction   | Comments                        |
|-----------------|-----------------------|---------------------------------|
| `1000`          | `START: MOV AL,00H`  | Load `00H` in accumulator       |
| `1003`          | `LOOP : OUT 0C8H,AL` | Send through output port        |
| `1005`          | `INC AL`             | Increment contents of accumulator |
| `1007`          | `JNC LOOP`           | Jump if no carry (continue loop) |
| `1009`          | `JMP START`          | Go to starting location         |

---

## Tabulation

| Waveform  | Amplitude | Time period | 
|-----------|-----------|-------------|
| Sawtooth  |   2.5 v   |    2.5 ms   | 
| Square    |   5 v     |    4 ms     |
---

## Model Graph

<img width="1176" height="1460" alt="AdobeExpressPhotos_a187b6577909473e869a24ca299f5af9_CopyEdited" src="https://github.com/user-attachments/assets/9cfb3f5e-6ea1-44ee-8858-e2c79ee16069" />




## OUTPUT IMAGE OF DAC(SAWTOOTH WAVE FORM DSO AND SQUARE WAVE FORM DSO)

## Square Wave Form

<img width="1600" height="718" alt="WhatsApp Image 2026-11-04 at 9 44 06 PM" src="https://github.com/user-attachments/assets/70e02388-d38e-4bf2-b92a-c0e2e6215f95" />

## Sawtooth Wave Form
<img width="1476" height="642" alt="WhatsApp Image 2026-11-04 at 9 44 06 PM (1)(1)" src="https://github.com/user-attachments/assets/5770c2ca-cdf7-4746-950f-cd681bd0ab08" />



## Result

Thus, the **DAC was interfaced with 8086** and different **waveforms** were successfully generated.




