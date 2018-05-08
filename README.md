# dasm
Disassemble D binary or D .o file.

Two files.

    ./dasm - shell script.
    /etc/bash_completion.d/dasm - BASH completion for dasm

Example:

    $ ./dasm opcode.o opcode.op_eq_s 
    Disassembly of section .text._D6opcode7op_eq_sFZi:
    0000000000000000 <opcode.op_eq_s()>:
       0:   55                      push   rbp
       1:   48 8b ec                mov    rbp,rsp
       4:   48 89 ce                mov    rsi,rcx
       7:   48 83 c6 08             add    rsi,0x8
       b:   48 89 d7                mov    rdi,rdx
       e:   48 83 c7 08             add    rdi,0x8
      12:   48 39 d1                cmp    rcx,rdx
      15:   75 0a                   jne    21 <opcode.op_eq_s()+0x21>
      17:   48 85 c9                test   rcx,rcx
      1a:   74 0c                   je     28 <opcode.op_eq_s()+0x28>
      1c:   fc                      cld    
      1d:   f3 a6                   repz cmps BYTE PTR ds:[rsi],BYTE PTR es:[rdi]
      1f:   74 07                   je     28 <opcode.op_eq_s()+0x28>
      21:   b8 00 00 00 00          mov    eax,0x0
      26:   eb 05                   jmp    2d <opcode.op_eq_s()+0x2d>
      28:   b8 01 00 00 00          mov    eax,0x1
      2d:   90                      nop
      2e:   5d                      pop    rbp
      2f:   c3                      ret    
