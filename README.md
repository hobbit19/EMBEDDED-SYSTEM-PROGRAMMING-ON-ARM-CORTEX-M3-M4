
# EMBEDDED-SYSTEM-PROGRAMMING-ON-ARM-CORTEX-M3 / M4 by Swaraj

## Processor Core:
- Nothing But The CPU.
- Consists Of Many Cores.(Core Means Alu And Instruction Decoder And So...)

## Features of the cortex M0/M3/M4 Processor:
- Operational Mode of the processor
- Different level access of the processor
- Register set of the processor
- Banked Stack design.
- Exceptions and Exception handling.
- Interrupt handling.
- Bus interfaces and bus matrix.
- Memory system and memory architecture of the processor.
- Ligned and Alligned data transfer
- Bootloader and IAP.

## Operational Mode of the processor:
Processor gives two operational modes:

**-   Thread mode**

**-   Handler mode**

**Thread mode :**
Application will run under this mode. It is also called as ***UserMode***
Processor always starts with Thread Mode.

**Handler Mode :**
 Exceptions and Interrupts will run under this mode. So, that means whenever your processor hits with any system exceptions or any interrupts which comes from any peripherals, then the processor will immediately changes its mode to the handler mode and the interrupt service routine associated with that exception or interrupt will be executed under the handler mode.
## Different level access of the processor:
Processor offers two access levels

**-Privilaged Access Level (PAL)**

**-Non-Privilaged Access Level (NPAL**)

  Lets say if your code is running with **privileged access level**, then your code has full access.That means it has full privilege to access all the processor specific resources and restricted registers.That means, a processor will have some restricted registers. By default code will run in PAL.

  Suppose if your code is running with **non-privileged access level**, that is NPAL, then your code maynot have access to some of the restricted registers of the processor.

  When the processor is in thread mode. It's possible to move the processor into non-privileged access level.Once you move out of the privileged access level to the non-privileged access level being in thread mode,then it's not possible to come back to the privileged access level unless you change the processors operational mode to handler mode. So, when the processor is executing in handler mode, the access level will always be privileged.

## Cortex-M processor core registers.
![alt text](https://github.com/swarajsomala/EMBEDDED-SYSTEM-PROGRAMMING-ON-ARM-CORTEX-M3-M4/blob/master/Images/Registers.PNG)

1. R0 to R12 registers are for general purpose.
2. All the registers, all the core registers are 32 bit wide.
3. R13 is a stack pointer which is used to track the stack memory.beside this R13 register, 2 more registers are mentioned, that is PSP which stands for Processor Stack Pointer and MSP which stands for Main Stack Pointer and these registers are called as banked version of Stack pointer.
4. The register R14 is called as the **LR**, LR stands for Link Register.
It stores the return information for subroutines, function calls, and exceptions. On reset, the processor sets the LR value to 0xFFFFFFFF.
5. **Program Counter (PC)** is register R15. It contains the current program address. On reset, the processor loads the PC with the value of the reset vector, which is at address 0x00000004.Bit[0] of the value is loaded into the EPSR T-bit at reset and must be 1.
6. **Program Status Register**
The Program Status Register (PSR) combines:

• Application Program Status Register (APSR)

• Interrupt Program Status Register (IPSR)

• Execution Program Status Register (EPSR).

![alt text](https://github.com/swarajsomala/EMBEDDED-SYSTEM-PROGRAMMING-ON-ARM-CORTEX-M3-M4/blob/master/Images/PGstatusRegister.PNG)

   *Application Program Status Register (APSR)* : 
   The APSR contains the current state of the condition flags from previous instruction executions.
   
          N : Negative flag

          Z : Zero flag

          C : Carry or borrow flag

          V : Overflow flag

          Q : DSP overflow and saturation flag

   *Interrupt Program Status Register (IPSR)*: 
   The IPSR contains the exception type number of the current Interrupt Service Routine (ISR).
