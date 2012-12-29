jvmBASIC
========

A BASIC to JVM bytecode compiler

jvmBASIC is a bytecode compiler which is capable of consuming a BASIC file (.bas) and producing a JVM .class file. The JVM class file exposes a public class named after the input file and a public method "program()" which contains the generated bytecode.  The generated .class file also exposes a "void main()" method which enables the BASIC program to be run from the command line.

In order to use the generated .class file from Java code, the public class members "inputStream" and "outputStream" must be set, in order for the BASIC program to consume input and produce output.

---------

The modules are:

* jvmBasicc - The jvmBASIC compiler
* jvmBasicrt - the jvmBASIC runtime library
* jvmBasicwww - A simple web server that uses BASIC programs to generate HTML over HTTP
* jvmBasicmojo - A maven mojo that compiles all .bas files found at /src/main/basic to .class files
* examples - a simple directory of examples
* demo - a simple .BAS program which can be compiled to produce a .jar and run to produce output

---------

Notes on the implementation

* The Parser and Lexer are created by [ANTLR](http://www.antlr.org) via an ANTLR grammar. 
* The generated bytecode is created by ObjectWeb [ASM](http://asm.ow2.org/)
* Currently screen functions such as "CLEAR" are not implemented

---------

Getting started

* cd to the "demo" directory
* Optionally edit the BASIC file "bottlesofbeer.bas"
* run "update.sh" to copy the jvmBasicc.jar and jvmBasicrt.jar files into the demo directory
* run "run.sh" to compile the BAS file, produce a jar and run the jar

---------

Looking at the compiled code

To view the generated class at the command line, use javap.  For example to view the generated output for "bottlesofbeer.bas" type

`javap botttlesofbeer`

to produce more verbose output from javap use

`javap -c bottlesofbeer`






 


