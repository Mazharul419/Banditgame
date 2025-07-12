# Level 9
## Brief

Performing ls - the data.txt file is within this directory.

Attempting the grep command give me the following message:
<img width="672" height="103" alt="image" src="https://github.com/user-attachments/assets/25dae43b-0fc1-4093-a5ec-4d4530710c4e" />

The grep function does not like to output binary data as it might mess up the terminal - see here:

https://serverfault.com/questions/1150968/why-does-grep-stop-matching-and-error-with-binary-file-matches

A different function is needed - for this I will use the strings function. This will return the location where there are printable strings.


Utilising this command outputs messy text with some coherent strings: 

<img width="621" height="135" alt="image" src="https://github.com/user-attachments/assets/8e07e5c9-c767-4baf-8dad-cd5487494e3c" />
<img width="498" height="141" alt="image" src="https://github.com/user-attachments/assets/273a6bac-ecc8-428a-ad4a-d5ac2a6f66cc" />


To look for the strings where the = sign is I will pipe this into the grep command and search for the "=" sign:

<img width="824" height="200" alt="image" src="https://github.com/user-attachments/assets/ec8b4d39-1bf9-45b9-a53e-13d133cca3b9" />

## Success!

Moving onto level 10 with password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey !

