# Himanshu notes (important topic with extended version)
## Things to Remember - Himanshu Notes
### Sub Part 1

- SSD := Solid State Drive
- NVM := Non Volatile Memory
- FAT := File Allocation Table
- NTFS:= New Technology File System
- Swap File:= Virtual Memory or Buffer
- MBR := Master Boot Record (at max 4 partitions and at max 2TB storage)
- BIOS := Basic Input Output System (used in MBR)
- GPT := GUID (Globally Unique Identifier) partition table
- UEFI := Unified Extensible Firmware Interface
- GRUB := Dual boot loader (Grand Unified Bootloader)
- Hypervisor := Creation and Manangement of Virtual Machines

### Sub Part 2
- /dev/sdaX := X is the partition number
- SATA := Serial advanced Technology Attachment (connect storage devices to motherboard)
- Greg Kroah-Hartman := Maintainers of linux kernals
- Linus Torvalds checks for bug in pre-final Testings
- uname -a ( See kernal version )
- lsb_release -a ( See distro version )
- kernal.org contains every kernal details


### Sub Part 3
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

- **CPU Parts**
    - Registers ( limited )
    - L1 Cache
    - L2 Cache 
    - RAM
    - ROM ( ssd/nvme )


### Sub Part 4

- **PATH** := list of directories to be traversed to find a utility
- python3 -m http.server : starts a server to access the folder. (-m helps in running the module directly as a script)
- in ls -lrt
    - example
        - -rw-r--r--  1 user group 1234 Apr 25  filename.txt
    - 1st character is type of file
        - \- = **regular file**
        - d = **directory**
        - l = **symbolic link**
        - c = **character device**
        - b = **block device**
    - next 9 char are permissions in 3 chunks 
        - First Chunk rwx is of **User/Owner**
        - Second Chunk rwx is of **Group**
        - Third Chunk rwx is of **Other**
    - S bit
        - **SUID** 
            - Set User ID
            - When file run it runs with root permission
            - s in user section.
            - eg /usr/bin/passwd ( it need root to update passwords )
        - **SGID** 
            - Set Group ID
            - s in group portion
            - file runs as group permission
            - in shared folders
        - **Sticky Bit**
            - User can write to the dir but **only delete their own files**
            - t in **others** section
- pwd for present directory

### Sub Part 5
- VI cmds
    - i for insert mode
    - a :- append
    - o :- new line below
    - yy to copy line
    - Xp :- to paste X times below
    - P :- paste above
    - Xyy :- to copy nest X lines
    - d :- to delete line
    - Xdd :- to delete X lines.
    - u :- to undo last action
    - U :- undo whole line changes
    - x :- delete 1 word
    - cw :- (change word) ( delete 1 word and put u in insert mode)
    - :%s/old/new/gc
        - : entre cli mode
        - % to all lines
        - s substitute
        - g global
        - c confirm before each replace
    - **Mark Tricks**
        - ma :- to create a mark with name a
        - `a :- jump to exect position of mark a
        - 'a :- jump to start of line where mark a was set
        - d'a :- delete from current line to mark a
        - : 'a, 'b d    deletes from lines from mark a to mark b
        - : 'a, 'b y  yank lines from line of mark a to line of mark b
        - : \`a ,\`b y   yank exectly from mark a to mark 
    - . (dot as a command) := can repeat previously done change to new line
- passwd -S : check password status
    - eg :- passwd -S parth
        - parth L 04/25/2025 0 99999 7 -1
    - L : locked
    - NP : no passwd
    - P : passwd set
    - passwd -l parth : locks parth
    - passwd -u parth : unlocks parth
    - passwd -e parth : removes password
    - passwd parth : change passwd 

- sudo vs su
    - sudo := (super doer) give roots power for the command
    - su := switch user ( it switch to root if no user is provided)
    - su - := switch to root + **run a new shell as root ( meaning you are in /root and have /root 's path variable etc)**
    - sudo -i:= run a shell as root ( and in /root so roots ~/.bashrc and etc)
    - sudo -s == su == just switch to root but shell is in your user
    - sudo -u == su - 
- Endianness
    - how multi-byte data is stored
    - Big Endian 
        - MSB (Most Significant Byte) to lowest address
        - used in Big datasets ( eg isro's chadrayan2's class dataset ( which i used in my isro ps ))
        - feels natural
    - Little Endian
        - LSB (Least Significant Byte) to lowest address
        - used normally in intel and amd cpus (almost everything).
    - eg
        - Num is 0x12345678 (12 is MSB)
        - 12 34 56 78 : Big
        - 78 56 34 12 : Little

## Sub Part 6
- compgen : for completion match 
    - compgen -A command l 
        - return all commands starting with l
        - -A means which action where we defined commands
        - can also use compgen -c l 
- date := command for data and time related shit
- Uptime := to check the uptime of laptop or system
- tree := print directory tree
- **cut**
    - cut -d',' -f1,2,4 data.txt
        - -d :- delimiter
            - -c character 
                - useage cut -c1-5 file.txt
            - -b byte
                - useage cut -b1-5 file.txt
        - -f1,2,4 :- gives 1, 2 and 4th field after using the delimter
-
- **cron**
    - sudo vi /etc/crontab := for system-wide crontab file
        - format :- MIN HOUR DOM MON DOW USER COMMAND (DOM = Day of month , DOW = Day of Week)
        - \* in any column means every like \* in DOM means every day( given its \* in DOW also other wise every monday if 1 in DOW)
    - crontab -e := for user wise crontab file
        - format :- MIN HOUR DOM MON DOW COMMAND (dont need user)

- **file compression**
    - gzip ( gzip and gunzip)
        - can only compress single file
        - usually combined with tar 
        - fast compression but lower compress ratio
    - bzip2 
        - can only compress single file
        - slow compression but higher compress ratio
        - also combined with tar
    - tar
        - used to convert multiple folders to a file
        - no compression
    - zip 
        - used to compress folder and files simultaniously 
        - used majorly with windows
    - you will see pairting of tar like  .tar.gz (.tgz) and .tar.bz2 ( tar for converting files and folders to a single file and gz/bz2 for compression)
-

    


 
    

    





