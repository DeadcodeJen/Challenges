## Challenge 3

#### Description
There is a problem with the following code, which can lead to arbirtary code execution.
The goal of this challenge is to spot the problem, and describe it (the problem itself and how to exploit it).

#### Rules
No debugging allowed.

#### Code
```c
#include <stdio.h>
#include <stdlib.h>

char username[512] = {1};
void (*_atexit)(int) =  exit;

void cp_username(char *name, const char *arg)
{
  while((*(name++) = *(arg++)));
  *name = 0; 
}

int main(int argc, char **argv)
{
  if(argc != 2)
    {
      printf("[-] Usage : %s <username>\n", argv[0]);
      exit(0);
    }
   
  cp_username(username, argv[1]);
  printf("[+] Running program with username : %s\n", username);
   
  _atexit(0);
  return 0;
}
```
