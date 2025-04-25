# Linux_Class
## Things to Remember - Himanshu Notes
### Sub Part1

- SSD := Solid State Drive
- NVM := Non Volatile Memory
- NTFS:= New Technology File System
- Swap File:= Virtual Memory or Buffer
- MBR := Master Boot Record (at max 4 partitions and at max 2TB storage)
- BIOS := Basic Input Output System (used in MBR)
- GPT := GUID (Globally Unique Identifier) partition table
- UEFI := Unified Extensible Firmware Interface
- GRUB := Dual boot loader (Grand Unified Bootloader)
- Hypervisor := Creation and Manangement of Virtual Machines

### Sub Part2
- /dev/sdaX := X is the partition number
- SATA := Serial advanced Technology Attachment (connect storage devices to motherboard)
- Greg Kroah-Hartman := Maintainers of linux kernals
- Linus Torvalds checks for bug in pre-final Testings
- uname -a ( See kernal version )
- lsb_release -a ( See distro version )
- kernal.org contains every kernal details


### Sub Part3
- After power on
    - POST (Power ON Self Test)
    - BIOS/UEFI
    - Bootloader
    - os select(if grub)
    - boot into OS
- Ram Modules have types
    - SIMM
        - Single In-Line Memory Module
        - 30-72 pins
        - IBM PCs & Pentium 1,2
        - 32-bit
    - DIMM 
        - Dual In-Line Memory Module
        - 168,184,240,288 pins
        - high speed as obivious
        - DDR3, DDR4, DDR5 
        - 64-bit
- Intel Optane vs Virtual Ram
    - OPTANE
        - Optane is a high speed storage technology that is faster then ssd/nvme but slower then ram
        - used in system with low ram
    - Virtual Ram
        - faking ssd/nvme as ram
        - software trick

- CPU Parts
    - Registers ( limited )
    - L1 Cache
    - L2 Cache 
    - RAM
    - ROM ( ssd/nvme )

### Sub Part4





