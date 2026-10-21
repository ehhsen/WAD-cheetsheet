JavaScript
JavaScript is a language and can be used in a web page inside the HTML
<script> tag.
Places to get output
There are two places to get output:
1 Console
2 Web page
In VS Code, JavaScript code can be written inside the <script> tag in
an HTML file.
alert(), prompt() and confirm()
These are used to show messages or get input from the user
 alert() displays a message to the user
prompt() shows a prompt where the user can enter a value
confirm() asks the user to confirm something and gives a
  true/false result
  alert("After loading");
  document.write()
document.write() writes content to the web page
The text will be displayed on the page
  If document.write() is used after the page has loaded it can replace the page content
Data types
Primitive types
Primitive types include:
1 Number
2 String
3 Boolean
4 Null
String concatenation
When a number is concatenated with a string, the number becomes part of
the string.
let s1 = "5";
let n = 5;

console.log(n + s1);
The output is "55".
Truthy and falsy values
In JavaScript values are treated as truthy or falsy when used in a
condition.
