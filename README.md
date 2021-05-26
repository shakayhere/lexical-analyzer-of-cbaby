# Lexical Analyzer Of CBaby
The attached project is the first step of simple compiler construction, that generates tokens after lexical analysis of language (defined by rules) called CBaby

## About CBaby
A new programming language is taken as an example which introduces the basics of programming using a simpler version of C++ language. The task is to develop a lexical analyzer for this language.

<br />

This programming language should have basic features to print data, read data, take input
from user perform arithmetic operations and compressions of value. Currently, it should
support only integer and single literal character to store the data. A brief description of main
element take makes up the language is as follow:

1. **Basic type of data:** integer, char
2. **Keywords:** <br />
&nbsp;  &bull;	 **Decision statement:** if elif else <br />
&nbsp;  &bull;	 **Looping statement:** while <br />
&nbsp;  &bull;	 **Read data statement:** in <br />
&nbsp;  &bull;	 **Function declaration statement:** func <br />
&nbsp;  &bull;	 **Write data statement:** print (print and remain on same line), println (print and move to next line) <br />
3. **Arithmetic Operators:** + -
4. **Relational operators:** < <= / > >= = /=
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

### Sample Code

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

