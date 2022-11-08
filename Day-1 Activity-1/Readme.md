# CAN-Network-Simulation-in-CANoe-and-CAPL-scripting

## Day-1 Activity-1
### Creation of Database for the THMS 
![THMS Database](https://user-images.githubusercontent.com/115522470/200523768-9902473e-af62-4540-95ac-3423bc6ad86b.png)

## Day-1 Activity-2

### Project Title: Braking system module

#### High Level and Low level Requirements

#### High level Requirements

| **ID** | **Description Category** | **status** |
| --- | --- | --- |
| HLR01 | Brake should be applied for the obstacle detection | Vehicle speed will be reduced and Back light should be ON |

**Low\_level\_Requirements:**

| **ID** | **Description Category** | **status** |
| --- | --- | --- |
| LLR01 | Brake should be slowly applied before 80m of the obstacle | Speed will be reduced slowly & Backlight should be ON | 
| LLR03 | Brake should be applied greatly before 30m of the obstacle | Speed will be reduced greatly & Backlight should be ON | 
| LLR04 | Brake should be applied fully before 5m of the obstacle | Vehicle should be stopped & Backlight should be ON | 

#### Test cases 

| **Req. ID** | **Test\_case** | **Description** | **Input** | **Expected output** | **Actual Output** | **Results** |
| --- | --- | --- | --- | --- | --- | --- |
| LL\_01 | TC\_01 | Brake Pressure applied is less before 80m of the obstacle | Ign\_key is 1 and brake input is case 1 | Brake light should be ON and vehicle speed will reduce slowly. | Brake light is ON
 | Success |
| LL\_02 | TC\_02 | Brake Pressure applied is high before 40m of the obstacle | Ign\_key is 1 and brake input is case 2 | Brake light should be ON and vehicle speed will reduce still more. | Brake light is ON | Success |
| LL\_03 | TC\_03 | Brake pressure applied is very high before 5m of the obstacle | Ign\_key is 1 and brake input is case 3 | Brake light should be ON and vehicle speed will reduce greatly. | Brake light is ON | Success |
| LL\_04 | TC\_04 | Brake should be applied completely before 1m of the obstacle | Ign\_key is 1 and brake input is case 4 | Brake light should be ON and vehicle should stop. | Brake light is ON. | Success |
