# NeedCat
### Description: This is your first beginning entrypoint that you must know how to make a connection with some TCP Connection program.

We are given a netcat command to begin with:
```
nc minictf.ucs.or.id 4432
```
Upon connecting, terminal displayed the following:
```
proof of work:
curl -sSfL https://pwn.red/pow | sh -s s.AAAAAQ==.f+Grd33BEGpfSmiUI5lIlg==
solution:
```
As we could see, we must curl the given entries to https://pwn.red.pow on a separate terminal window. Doing that gives us the following Base64 encoded message: 
```
s.De0QhruYvCGgfqDDeoBiSZOXBvvq087nx6y37lRfU+tlyjfP9UHuuDs2Bq4cdnBfpJ8o51HPFE6JbolW1dLRTVNA1YFe6YmxzYgOD15itDq4c3O7eYG/KTzUJzcISz67m65SrgWQNnF4+wxzaDSpJGk0d6Lof5I7iYM5NbEIMVQBzfQYlVnfsIUYsVeLgDdfOJPTvGHYS/KmbPNrKJLYNw==
```
Submitting them to the original nc terminal, we got the flag after a pleasant introductory animation.

Flag: ```UCS{just_1ntro_for_y0u_h0w_t0_connect_1nto_TCP_CONNection}```
