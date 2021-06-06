# Lexical Analyzer Of CBaby
The attached project is the first step of simple compiler construction, that generates tokens after lexical analysis of language (defined by rules) called CBaby

## About CBaby Language
A new programming language is taken as an example which introduces the basics of programming using a simpler version of C++ language. The task is to develop a lexical analyzer for this language.

This programming language has basic features to print data, read data, take input
from user perform arithmetic operations and compressions of value. Currently, it
supports only integer and single literal character to store the data. A brief description of main
element take makes up the language is as follow:

1. **Basic type of data:** integer, char
2. **Keywords:** <br />
&nbsp;  &bull;	 **Decision statement:** if elif else <br />
&nbsp;  &bull;	 **Looping statement:** while <br />
&nbsp;  &bull;	 **Read data statement:** in <br />
&nbsp;  &bull;	 **Function declaration statement:** func <br />
&nbsp;  &bull;	 **Write data statement:** print (print and remain on same line), println (print and move to next line) <br />
3. **Arithmetic Operators:** + -
4. **Relational operators:** < <= > >= == /=
5. **Comments:** /* enclose comment in */
6. **Identifier:** a letter followed by any number of letters or digits
7. **Numeric constants:** only integers
8. **Variable declaration Operator:** :
9. **Literal constants:** a letter enclosed in single quotes.
10. **Strings:** only used in print statements(no need to declare variables for them)
11. **Parenthesis, Braces, Square Brackets**
12. **Assignment Operator:** :=
13. **Input Operators:** >>
14. **Semi-Colon, Colon, Comma**

### Example Code
Following is a sample program written in CBaby

```
func Integer: numPrint (Integer: num, Integer: length)
{
	Integer: i, j, first, temp;
	char : a;
	a := 'x';
	print ( "enter number" );
	In >> i;
	println (i);
	i := length;
	while i > 0 :
	{
		first:= 0;
		j := 1;
		while j < i:
		{
			print( j);
			j := j + 1;
		}
		if j == 1:{
		print("one");
		}
		elif j==2:{
			print("two");
		}
		else
		{
			print("others");
		}
		/* this is a comment */
		i:= i - 1;
		/*This is a
		Multiline
		Comment*/
	}
	print ( "temp is ");
	println(temp);
	ret i;
}
```

## Getting Started
You can see the format of all token-lexeme pairs in `documentation.pdf`. The Lex will take a text file containing CBaby source code `test.cbaby` as input, read it line by line, and will generate a text file `tokens.txt` that contains token-lexeme pairs encountered in the given .cbaby file. On starting, the program asks for file path with (.cbaby) as file extention. The lex also prints appropriate and helpful errors when incorrect programs are provided to it.

The following are some test cases and sample output of the code:

#### Wrong Input
<table>
<tr>
<th>test.cbaby</th>
<th>Output</th>
</tr>
<tr>
<td>
<pre>
func void write(char: j)
{
	&^%&^print(j);
}
</pre>
</td>
<td>

```
Enter path/filename for lexical analysis: test.cbaby
Could not identify lexeme pattern in line 3
3       &^%&^print(j);
It is not a part of CBaby language. Please check your file and try again!
```

</td>
</tr>
</table>

#### Correct Input

<table>
<tr>
<th>test.cbaby</th>
<th>Output</th>
</tr>
<tr>
<td>
<pre>
func void write(char: j)
{
	print(j);
}
</pre>
</td>
<td>

```
Enter path/filename for lexical analysis: test.cbaby
Execution successful. Please check textfile for generated tokens!
```

</td>
</tr>
</table>

#### Output of Textfiles

<table>
<tr>
<th>test.cbaby</th>
<th>tokens.txt</th>
<th>tokens(readable).txt</th>
</tr>
<tr>
<td>
func void write(char: j)<br />
{<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;	print(j);<br />
}<br />
</td>
<td>
<pre>
(FUNC,^)
(VOID,^)
(ID,"write")
('(',^)
(CHAR,^)
(':',^)
(ID,"j")
(')',^)
('{',^)
(PRINT,^)
('(',^)
(ID,"j")
(')',^)
(';',^)
('}',^)
</pre>
</td>
<td>

```
func void write(char: j)
(FUNC,^)
(VOID,^)
(ID,"write")
('(',^)
(CHAR,^)
(':',^)
(ID,"j")
(')',^)

{
('{',^)

print(j);
(PRINT,^)
('(',^)
(ID,"j")
(')',^)
(';',^)

}
('}',^)
```

</td>
</tr>
</table>

### Before you Start
The program is made and tested in java version "1.8.0_291". So, you should have Java JDK 8 installed on your system. If not, you can see the following link for installation
<br />
[How to Install JDK 8 (on Windows, Mac OS & Ubuntu)](http://cnaiman.com/COMP170/Orientation/How%20to%20Install%20JDK%208%20%28on%20Windows%2C%20Mac%20OS%2C%20Ubuntu%29%20and%20Get%20Started%20with%20Java%20Programming.html "How to Install JDK 8")


## How to Build and Run
In src folder, enter the following command to compile the code. A binary called `Source.class` will be produced.
```
javac ImplementLex/Source.java
```

To run this file, enter the following in src folder:
```
java ImplementLex.Source
```

## License
Copyright (c) 2021 shakayhere

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
