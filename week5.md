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
