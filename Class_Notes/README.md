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
- lsof = list of open files
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
    - :.,+10d :- delete
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

### Sub Part 6
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
        - used to convert multiple folders/files to a file
        - no compression
    - zip 
        - used to compress folder and files simultaniously 
        - used majorly with windows
    - you will see pairting of tar like  .tar.gz (.tgz) and .tar.bz2 ( tar for converting files and folders to a single file and gz/bz2 for compression)
- **Bash Scripting**
    - #!/bin/sh in starting to give the bin compiler  (known as shebang)
    - when you run ./scripts.sh 2023ucs0105 parth
        - $0 = name of script 
        - $1 = first argument
        - $2 = second argument
        - $# = no of argument
        - $? = exit code of last cmd
        - $_  = last argument of previous cmd
        - "$@" = All argument as seperate strings
        - "$*" =  All argument as single string
    - while loop
        - i=1 <br/> while [ $i -le $n ]; do 
            - echo $i 
            - i=$(expr $i +1) 
        - done
    - for loop 
        - for (( i=1; i<=nums; i++ )); do
            - sum=$((sum + i))
        - done
    - if
        - if [ $a -lt $b ]; then
            - echo "a is less"
        - elif [ $a -eq $b ]; then
            - echo "equal"
        - else
            - echo "a is more"
        - fi
    - **Always space b/w after ([) and before (])**
    - **COmparators**
        - -eq = equal to
        - -ne = not equal
        - -lt = less than
        - -le = less than or equal 
        - -gt = greater than  
        - -ge = greater than or equal 
        - -e file = check if file exits
        - -d dir =  is directory
        - -s file = file size>0
        - -nt = newer than
        - -ot = older than
    - EOF
        - reads until EOF appears.
            - cat << EOF > newfile.txt
            - this is l1
            - this is l2
            - EOF
    - String substitution happen only when "$s" not in '$s'.

### Sub Part 7
- **grep** 
    - Search for words inside file
    - options 
        - -i = case insensitive
        - -n line number
        - -w word only
        - **-r** recursive like in grep -r "word" .
        - **-E** for incuding extended regrex
- **find** 
    - find [where] (options) "what"
    - options
        - -name for by name
        - -type for by type
            - f = file
            - d = directory
        - -size for by size
        - - mtime =  modified time
- **locate**
    - locate use a build database of files and folders insteads searching the whole filesystem
    - sudo updatedb for updateing the database
    - fast then find


### Sub Part 8
- Pstree = process tree
- echo $$ = process number of kernal
- Nautilus = folder utility
- APT = advanced package tool
- dpkg = debian package for .deb files
- RTC = real time clock
    - sudo timedatectl set-local-rtc 1 =  for changing syning time b/w linux and win
- NTP = network time protocol
    - ps -aux for quick check
    - ps -aef for advance check ( parent - child relation bhi hota hai, mem % etc)
- systemctl list-units
    - Lists all active units (services, sockets, timers, devices, etc.).
    - systemctl list-units | grep "ssh" =  gives running ssh units.
- systemctl list-jobs
    - Lists all pending/running jobs

- lsmod = list of loaded kernal modules in linux
- insmod =  inseart a kernal module in linux
- UNetbootin := an rufus
- to combile a c programm
    - gcc -Wall name_of_file.c -o name_of_exe
- clang better then gcc in error dignostics 
- hostname = name of host like parth-Victus in parth@parth-Victus
    - hostnamectl set-hostname <name_to_give>
    - hostid = print id of host
- wine =  run window software in linux
- lshw  = list all hardware
    - -class for showing particular class of hardware
        - network
        - disk
        - storage
        - processor
- SCSI = small computer technology attachment , advanced version of sata
- PoE = power over ethernet
- ifconfig = manange network interface
    - nmcli - cli for network manager
- iwconfig = just of wireless network 
- MAC address =  media access control address   = 48 bits for each hardware port
- IP = internet protocol = IPv4 32 bits ; IPv6 128 bits.
- CVE = common vulnerabilities and Exposures ( can track in cve.org ).
- diff = can be used to see difference b/w 2 files like diff file1.txt file2.txt
- cmp = give difference in bytes
- vim -d f1.txt f2.txt =  vim in diff mode.
- iostat = give usage of cpu
- netstat -tunapl
    - t = tcp
    - u = udp
    - n = named
    - a = all
    - p = program
    - l = listening
- systemd introduces parallel programming where as init do it in sequentially
- Which give the path it is using for a particular executable in PATH
    - -a give all executable in PATH
      


    


 
    

    





