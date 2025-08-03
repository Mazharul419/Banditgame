# Level 12

# Brief

<img width="1647" height="287" alt="image" src="https://github.com/user-attachments/assets/1eabb33a-cce4-4927-8c4c-5ad58553829e" />

NOTE 12/07: 

Honestly this was extremely confusing - so I went through the walkthrough.

The walkthrough was confusing - I will come back to this another time...

FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

01/08: WE ARE SO BACK - Time to give it another try!


## 1. making temporary directory

A temp directory is first made to work on.
<br>
To do this the `mktemp` command is used to make a `.tmp` directory:

    bandit12@bandit:~$ mktemp -d                                                                                   
    /tmp/tmp.wRalTKVqgp

The location of the `data.txt` file needs to be found - using `ls`:

    bandit12@bandit:~$ ls                                                                                          
    data.txt

This is the correct directory - using the `cp` command the file is copied to the temp directory:

cp command uses the following syntax:

    cp [...file/directory-sources] [destination]

`[...file/directory-sources]` is the current file path - noted by `./data.txt`
`[destination]` is the tmp directory path `/tmp/tmp.wRalTKVqgp`

Substituting:

    $ cp ./data.txt /tmp/tmp.wRalTKVqgp

Checking the temp directory to see if this was successful:

     bandit12@bandit:~$ cd /tmp/tmp.wRalTKVqgp                                                                      
     bandit12@bandit:/tmp/tmp.wRalTKVqgp$ ls
     data.txt 

Success! The file can now be worked on.

<br>

## 2. Investigating and reversing hexdump of file

To see the contents of the file the `cat` and `head` command are used:

    bandit12@bandit:/tmp/tmp.wRalTKVqgp$ cat data.txt | head                                                       
    00000000: 1f8b 0808 84c9 8768 0203 6461 7461 322e  .......h..data2.                                            
    00000010: 6269 6e00 0142 02bd fd42 5a68 3931 4159  bin..B...BZh91AY                                            
    00000020: 2653 592b 25cc 1e00 0017 7fff f9df a1ff  &SY+%...........                                            
    00000030: f67f f7ff befe dded befd efaf dcff b7ff  ................                                            
    00000040: bff7 abbd bf6f eb0f b79f bbf9 b001 3998  .....o........9.                                            
    00000050: 1034 0c80 01a3 d40d 1a06 8680 6800 0c80  .4..........h...                                            
    00000060: 0003 41a0 01a3 41a3 4188 1a68 3400 01a0  ..A...A.A..h4...                                            
    00000070: 7a80 01a3 2686 87a1 9432 7a88 1a32 1a68  z...&....2z..2.h                                            
    00000080: d343 41a6 4068 6868 0d00 d1a3 1000 1a00  .CA.@hhh........                                            
    00000090: 0d03 4680 64f5 068d 1a0d 191a 3403 4c80  ..F.d.......4.L. 

<br>

The file has hexdump applied to it - which is used to present data in a easy-to-read way for analysis.

To reverse the hexdump to get the original file - the `xxd -r` command is used:

    $ xxd -r data.txt compresseddata
    $ ls
    compresseddata  data.txt

The original data looks like this:

    $ cat compresseddata | head                                                  
    CngH ՟VE.@#ƒU]1,0|$':54\O7_P-(94   8?"&tZ|TI˖ZsEB-&x?d]9Q&A)`^Ǽ@4萷#QP@[[ʎ@딋^a3/>Z6+y
    {YW6k~XDӨsX&x^I     @˳\\ z#!SÍꤜTf$:r-Q��*&)0?M!-Va<ѠtB*=o#V0U(S9VPx+C/[\ч=0:v~YR@VڥV#_U|

This is ready to be decompressed.

## 3. Decompressing file #1 - gzip to bzip2

To decompress the file - the file type is required to know the appopriate decompression command

Using `file` this can be found out straight away:

    $ file compresseddata
    compresseddata: gzip compressed data, was "data2.bin", last modified: Mon Jul 28 19:03:32 2025, max compression, from Unix, original size modulo 2^32 578

The first part - `...gzip compressed data...` shows this is a gzip file.

The appopriate command is `gzip -d <file>` 

Substituting:

    $ gzip -d compresseddata
    gzip: compresseddata: unknown suffix -- ignored 

gzip does not recognise the `compresseddata` file as a gzip file. To ensure it does the `.gz` suffix needs to be added.

The `mv` command is used to do this:

    $ mv compresseddata compresseddata.gz
    $ ls                                                                        
    compresseddata.gz  data.txt

This is complete - reattempting the decompression:

    $ gzip -d compresseddata.gz
    $ ls                                                                        
    compresseddata  data.txt

This is complete - the new file type is:

    $ file compresseddata
    compresseddata: bzip2 compressed data, block size = 900k

It is bzip2 - onto the next decompression!

## 4. Decompressing file #2 - bzip to gzip

Prior to decompressing - the file will be renamed with the .bz2 extension:

    $ mv compresseddata compresseddata.bz2

As stated above - the file is bzip2 - the command to decompress is:

    $ bzip2 -d <file>

Substituting and executing:

    $ bzip2 -d compresseddata.bz2
                                    
    $ ls                                                                        
    compresseddata  data.txt    


This is complete - the new file type is:

    $ file compresseddata
    compresseddata: gzip compressed data, was "data4.bin", last modified: Mon Jul 28 19:03:31 2025, max               compression, from Unix, original size modulo 2^32 20480

It is gzip once more - onto the next decompression!

## 5. Decompressing file #3 - gzip to tar

Since the file is a gzip - the steps are the same as earlier:

    $ mv compresseddata compresseddata.gz
    $ ls
    compresseddata.gz  data.txt
    $ ls compresseddata  data.txt

The file is a tar file:

    $ file compresseddata 
    compresseddata: POSIX tar archive (GNU)

## 5. Decompressing file #3 - gzip to tar



## AWESOME!!!

### The level is complete - onto the next!


  
