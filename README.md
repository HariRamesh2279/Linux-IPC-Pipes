# Linux-IPC--Pipes
Linux-IPC-Pipes


# Ex03-Linux IPC - Pipes

# AIM:
To write a C program that illustrate communication between two process using unnamed and named pipes

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - pipe(), fifo()

### Step 3:

Testing the C Program for the desired output. 

# PROGRAM:

## C Program that illustrate communication between two process using unnamed pipes using Linux API system calls
#include <stdio.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>
#include <unistd.h>

int main()
{
    int fd;
    char msg[] = "Hello through Named Pipe";
    char buf[100];

    mkfifo("mypipe", 0666); // create named pipe

    fd = open("mypipe", O_RDWR);

    write(fd, msg, sizeof(msg));
    read(fd, buf, sizeof(buf));

    printf("Message sent: %s\n", msg);
    printf("Message received: %s\n", buf);

    close(fd);

    return 0;
}




## OUTPUT

## C Program that illustrate communication between two process using named pipes using Linux API system calls

# RESULT:
The program is executed successfully.
