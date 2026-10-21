Table:

Creation: <table> ...</table> for entering row in table <tr></tr> and to enter data in row <td></td> Example : <table> <tr><td>1</td> <td>2</td><td> 3</td></tr> <tr> <td>4</td>

<td>5</td> <td>6</td></ tr></table>

1 2 3

4 5 6

To merge Columns: <td colspan=”number of columns to merge”> data here</td>

To merge Rows: <td rowspan=”number of rows to merge “> data here</td>

To merge rows and columns in one cell: <td rowspan =” value”, colspan=””>data here</td>

To add caption that is displayed above table :<table> <caption> write here</caption></table>

To apply styling on Columns:

<col id=”give id here”> to give same styling to multiple columns <colgroup id=””> <col> <col></colgroup>

Borders are applied on table and td but is we used border-collapse:collapse then borders can be applied on tr and col;

Forms: it is used to get input from use.

To create it <form method=”get/post” action=”process.php”></form>.

Every form can have on or multiple fieldset and name of fieldset is given.

<form> <fieldset> <legend>Name is here</legend>

<label>Enter Email</label>

<input type=”email” id=””>

</fieldset>





**Form:**
For input Fields:
syntax:
<input     type="text"     placeholder="Enter your name">
For entering text we use type text and for other thing we use these types as follow:
**Type                        usage**
Password            For hidden password
Email                    For enterning email
tel                          For enterning phone number
file                         For submitting  a file.
Search                 For making a search bar.
Radio                    For selecting one option
Check box          For selecting multiple options
Submit                For submiting a form
Reset                   For reset of input fields you filled
Button                 for making a clickable button.
Range                  For making a slider of value
Datetime            For selecting date and time.
Date                     For just selecting date.
Attribute              Purpose
Required              For making field compulsory.
Placeholder        For showing a text inside the field
Checked              For selecting a checkbox/radio button by default
Selected              For selecting an option by default
Value                    For assigning a value .
Name                     For identify what we submit .
For                           we use in label to join label with input filed .in input field we use id. 
                                  Name which we use in for attribute must be same in id to make link                                            
                                 between them.
**CSS Position                                                           Definition**
  Static                       The element is positioned according to the normal flow. This is the default.
 absolute                      The element is removed from normal flow and positioned in relation to its nearest 
                                positioned ancestor. Original space not resrved.
relative                        The element is moved relative to where it would be in   the normal flow.
                                Original space remain resrved.
                                                           
Fixed                          The element is fixed in a specific position in the  window even when 
                                the document is scrolled.
                                                               
 sticky                        The element is positioned in according to the normal flow, and then 
                               offset relative to its nearest scrolling ancestor. This is used to allow 
                               an item to scroll and then stay fixed in position once its scroll position
                               is reached.
