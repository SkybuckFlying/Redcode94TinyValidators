# Redcode94/PMars94/Corewar/ICWS94 Tiny Validators

## How to use these tiny validators to validate your core (ICWS94 draft) executor:

            1. Clone git repository (tiny validators size is 2 GB, git might
               require another 2 GB, 4 GB Virtual Disk on 8 GB RAM Disk
               recommended for 16x speed up performance.
            2. Start your core executor.
            3. Set core size to 16.
            4. Set private space size to 16.
            5. Load instruction program (.red) into the core at position 0.
            6. Load private space sequential numbers (.pspace) into private space at
               position 0.
            7. Set maximum cycles to 3.
            8. Execute the core starting at position 0.
            9. Load core dump into memory (.coredump.red).
            10. Compare executor core to coredump.
            11. Compare executor private space to coredump.
            12. Compare executor threads to coredump.
            13. Compare executor thread positions to coredump.
            14. Verify they are the same if not your executor contains a bug.
            15. Repeat for next instruction.

            .red = input to PMarsW95 v0.9.2-5.23 by Skybuck Flying
            .coredump.red = output from PMarsW95 v0.9.2.5.23 by Skybuck Flying

##   Command prompt example for PMarsW95
## (loading instruction test program, dumping core, and loading private space, core size 16, pspace size 16, cycles 3, max length 10, distance 10):

            pmarsw95 ".\TinyValidators\000001 DAT\000001 DAT.A  Number -2, Number -2.red" -s 16 -S 16 -X ".\TinyValidators\000001 DAT\000001 DAT.A  Number -2, Number -2.coredump.red" -l 10 -d 10 -c 3 -T -Z -Y .\TinyValidators\sequential.pspace

## Git remarks:

            1. Git is slow for many files (400.000+)
            2. Git consumes additional harddisk space for adding/commiting.
            3. Git wastes time on refreshing index after copieing files/git repo (refreshing can be disabled, no experience with it)

## Github remarks:
            4. Github file size limit of 100 MB prevents uploading of large
               virtual harddisk of 2 GB nececessary to contain these files, so
               uploading them seperately.

## Performance advise (use RAM Disk):
            4. Copy virtual harddisk to a RAM Disk.
            5. Mount the virtual harddisk from the RAM Disk.
            6. Access the RAM Disk backed virtual harddisk for increased
               performance.

            (Alternatively git clone can also be done directly to RAM Disk)

## RAM Disk Caution (DATA Loss):
            7. If making any changes make sure to copy virtual harddisk back to a real
               harddisk disk before shutting down the RAM Disk, otherwise all changes lost.

## About PMarsW95 (modifications for validating):
            PMarsW95 is a modification of PMars94 to allow loading of private space
            values and dumping of core. It has additional command line parameters.
            PMarsW95 is not included in this repository.

## About folders:
            Each redcode instruction has it's own folder with all it's variations of
            modifier, addressing mode, negative and positive test values are used.
            Each variation is numbered at the start of the .red filename.
            The folders contain a number at the start which indicates at which
            variation number the instruction starts, this may be handy to refer to
            inner loops of verification programs/debugging.

            In total there are: 212800 instruction variations.

            There is also a special test program to test a "perfect spawn".

## Here is an example of the files:

```
Input textfile name:
.\011201 MOV\011201 MOV.A  Number -2, Number -2.red

Input textfile contents:
nop.f  $-4, $-3
nop.f  $-2, $-1
MOV.A  #-2, #-2
nop.f  $ 1, $ 2
nop.f  $ 3, $ 4

Output textfile filename:
.\011201 MOV\011201 MOV.A  Number -2, Number -2.coredump.red

Output textfile contents:
;warrior[0].tasks: 1
;warrior[0].taskHead[0]: 3
;warrior[0].pspace[0]: 1
;warrior[0].pspace[1]: -7
;warrior[0].pspace[2]: -6
;warrior[0].pspace[3]: -5
;warrior[0].pspace[4]: -4
;warrior[0].pspace[5]: -3
;warrior[0].pspace[6]: -2
;warrior[0].pspace[7]: -1
;warrior[0].pspace[8]: 0
;warrior[0].pspace[9]: 1
;warrior[0].pspace[10]: 2
;warrior[0].pspace[11]: 3
;warrior[0].pspace[12]: 4
;warrior[0].pspace[13]: 5
;warrior[0].pspace[14]: 6
;warrior[0].pspace[15]: 7
00000:   NOP.F  $    -4, $    -3    
00001:   NOP.F  $    -2, $    -1    
00002:   MOV.A  #    -2, #    -2    
00003:   NOP.F  $     1, $     2    
00004:   NOP.F  $     3, $     4    
00005:   DAT.F  $     0, $     0    
00006:   DAT.F  $     0, $     0    
00007:   DAT.F  $     0, $     0    
00008:   DAT.F  $     0, $     0    
00009:   DAT.F  $     0, $     0    
00010:   DAT.F  $     0, $     0    
00011:   DAT.F  $     0, $     0    
00012:   DAT.F  $     0, $     0    
00013:   DAT.F  $     0, $     0    
00014:   DAT.F  $     0, $     0    
00015:   DAT.F  $     0, $     0    

pspace initialization textfile filename:
.\sequential.pspace

pspace initialization textfile contents:
;warrior[0].pspace[0]: -8
;warrior[0].pspace[1]: -7
;warrior[0].pspace[2]: -6
;warrior[0].pspace[3]: -5
;warrior[0].pspace[4]: -4
;warrior[0].pspace[5]: -3
;warrior[0].pspace[6]: -2
;warrior[0].pspace[7]: -1
;warrior[0].pspace[8]: 0
;warrior[0].pspace[9]: 1
;warrior[0].pspace[10]: 2
;warrior[0].pspace[11]: 3
;warrior[0].pspace[12]: 4
;warrior[0].pspace[13]: 5
;warrior[0].pspace[14]: 6
;warrior[0].pspace[15]: 7
```

## Example how to run the modified PMarsW95 executable to load test programs/pspace, set core size, pspace size, cycles and produce coredumps:
ms-dos prompt/batch file command:
```
pmarsw95 ".\011201 MOV\011201 MOV.A  Number -2, Number -2.red" -s 16 -S 16 -X ".\011201 MOV\011201 MOV.A  Number -2, Number -2.coredump.red" -l 10 -d 10 -c 3 -T -Z -Y .\sequential.pspace
```

## command line parameters for PMars95W:
```
PMARSW95 v0.9.2-5.23 created on 5 april 2010 by Skybuck Flying
Corewar simulator with ICWS'94 and Extension 2009
New Features Added: Instruction limit 8000 (-l), Core Dump (-X filename),
Thread Dump (-T), PSpace Dump (-Z), PSpace Load (-Y filename),
Performance (-M), Warrior TextDump (-W), Warrior BinaryDump (-A)
Copyright (C) 1993-95 Albert Ma, Na'ndor Sieben, Stefan Strack and
Mintardjo Wangsaw, Copyright (C) 2009-10 Skybuck Flying (Harald Houppermans :))
Usage:
   pmars [options] file1 [files ..]
   The special file - stands for standard input
Options:
  -r # Rounds to play [1]              
  -e   Enter debugger
  -s # Size of core [8000]             
  -b   Brief mode (no source listings)
  -c # Cycles until tie [80000]        
  -V   Verbose assembly
  -p # Max. processes [8000]           
  -k   Output in KotH format
  -l # Max. warrior length [100]       
  -8   Enforce ICWS'88 rules
  -d # Min. warriors distance         
  -f   Fixed position series
  -F # Fixed position of warrior #2    
  -o   Sort result output by score
  -X $ Dumps core to file $            
  -T   Dumps threads to coredump
  -Z   Dumps pspace to coredump        
  -Y $ Loads pspace from file $
  -M   Performance measurement         
  -W $ Dumps warrior(s) to text file $
  -A $ Dumps warrior(s) to binary file $  
  -S # Size of P-space [1/16th core]
  -= $ Score formula $ [(W*W-1)/S]     
  -@ $ Read options from file $
  ```
  
  ## Skybuck's Corewar Simulator:
  
  Skybuck's Corewar Simulator can be found on the link below which contains more information and links to PMarsW95 which was used to validate this corewar executor/simulator.
  
  The instruction set was later modified to allow more powerfull self-modification of warriors, it remains compliant with the standard if those extensions to the instructions are not used/don't appear in the warriors.
  
  https://www.skybuck.org/Corewars/SkybucksCorewarsSimulator/version%200.18/
  
  Newer versions can be found here:
  
  https://www.skybuck.org/Corewars/SkybucksCorewarsSimulator/
  
  
