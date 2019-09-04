
# EMBEDDED-SYSTEM-PROGRAMMING-ON-ARM-CORTEX-M3 / M4

##processor Core:
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
Application will run under this mode.It is also called as ***UserMode***
Processor always starts with Thread Mode.

**Handler Mode :**
 Exceptions and Interrupts will run under this mode.So, that means whenever your processor hits with any system exceptions or any interrupts which comes from any peripherals, then the processor will immediately changes its mode to the handler mode and the interrupt service routine associated with that exception or interrupt will be executed under the handler mode.
## Different level access of the processor:
Processor offers two access levels

**-Privilaged Access Level (PAL)**

**-Non-Privilaged Access Level (NPAL**)

  Lets say if your code is running with privileged access level, then your code has full access.That means it has full privilege to access all the processor specific resources and restricted registers.That means, a processor will have some restricted registers.By default code will run in PAL.

  Suppose if your code is running with non-privileged access level, that is NPAL, then your code maynot have access to some of the restricted registers of the processor.

  When the processor is in thread mode.It's possible to move the processor into non-privileged access level.Once you move out of the privileged access level to the non-privileged access level being in thread mode,then it's not possible to come back to the privileged access level unless you change the processors operational mode to handler mode.So, when the processor is executing in handler mode, the access level will always be privileged.
