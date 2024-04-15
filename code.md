section .text
        global _start

_start:  
        mov ecx, [var1]   ;assign var1 (5) to ecx
        cmp ecx, 0
        je exit          ; jump if 0
        mov eax, 1       ; set eax to 1 so ecx doesn't  multiply by 0 
loop:

        imul eax, ecx  ; multiply ecx * eax 
        dec ecx        ; decrease it by 1 every loop
        cmp ecx,0      ; compares ecx when its 0 and if it is stops it
        jg loop        

exit:

        mov eax,1
        int 0x80


section .data
var1 dd 5
section .bss
result resw 1



