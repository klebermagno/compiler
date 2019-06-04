# Compiler-example

## Crie uma gramática g4

## Crie seu código nw

## Use ANTLR para gerar o código intermediário confirme abaixo:

## generate .o and .s file:

$ java -jar $(ANTLR) -o output Narwhal.g4

## compile:

$ javac -cp $(ANTLR):output:. Main.java

## Roda o app ANTLR e gera o .ll:

$ java -cp $(ANTLR):output:. Main test.nw > test.ll
	clang test.ll

$ llvm-as -f test.ll   # assemble IR to bitcode file t.bc
$ llc -f test.bc       # compile instructions to assembly code file t.s (x86 on my box)
$ gcc  --std=c++11 -no-pie test.s -o test.native

$ ./teste.native               # execute the program t in current directory

