## Reverse Engineering

THM Room link: https://tryhackme.com/room/reverseengineering

---

### Task 1: Debugging and File Permission

In this task, we'll be learning the basics of reverse engineering and assembly. Here are some important things to do before starting the task:
- These files have been compiled with the lowest level of optimisation on Unix based machines and are intended to be run on Linux/Mac.
- Make sure you set up a debugger - it would be good to get comfortable with radare2 which can be downloaded from here. You can also use other debuggers like gdb, which come installed in most Unix based operating systems.
- hen these files have been downloaded, change the permissions of these files using the command chmod +x filename

--- 
### Task 2: crackme1

1. Download the task file
2. use ```strings``` command on the file
>```bash
>strings crackme1.bin
>```

The password is ```hax0r```

--- 

### Task 3: crackme2

```bash
chmod +x crackme2.bin
./crackme2.bin
gdb ./crackme2.bin

```