**XMC2GoPWMpong**
=============

tutorial ver 1.0.0

**DESCRIPTION:**<br>
 This example demonstrate the PWMSP001 App.<br>
 The Period Match Interrupt of PWMSP001 will be used to determine the duty cycle of the LEDs 1 & 2.<br>
 The on-board LED 1 (Port 1.0) will be bright with duty cycle from 0% to 100%.<br>
 The on-board LED 2 (Port 1.1) will be bright with duty cycle from 1000% to 0%.<br>
 The NVIC002 App needs to be connected accordingly for the PWMSP001/0 & PWMSP001/1 period match interrupt.<br>
  
**REQUIREMENTS:**<br>
- J-Link Drivers installed on PC
- J-Link v4.59 or above
- XMC1100 XMC 2Go CPU Card
- alternatively XMC1200 or XMC1300 Boot kit can be used

**SETUP:** Connect the USB cable with XMC1100 or XMC1200 or XMC1300 CPU card.<br>

**HOW TO CREATE THE PROJECT:**
- 1 Instantiate PWMSP001 App and NVIC002 App from App Selection View
- 2 In PWMSP001, Select Edge-Aligned Mode, enter the PWM freq as 1000 Hz, Select Period Match Initialization in 
	 PWM Configuration Tab.
- 3 In NVIC002_0 App, Select "Enable Interrupt At Initialization".
    Enter the "pwm_period_interrupt" in the User defined Interrupt Handler.
- 4 Make the following Signal Connection:
   - Connect the "Period Match Interrupt" signal of PWMSP001/0 and PWMSP001/1 to the "Interrupt Node" 
     signal of NVIC002/0 App.
- 5 Manual Pin assignment: This is to define the board specific I/O constraints
	 In this case, PWMSP001/0 pin_directoutput resource is assigned to port P1.0 as first LED flasher.
	 PWMSP001/1 pin_directoutput resource is assigned to port P1.1 as second LED flasher.
- 6 Call PWMSP001_Start after Dave_Init().
- 7 Define the "PWM_Period_Interrupt" interrupt handler function in the code.
- 7 Generate the code and build the project.
- 8) Download and run the project.
