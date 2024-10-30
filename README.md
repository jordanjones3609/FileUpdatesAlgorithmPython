<h1>Algorithm For File Updates In Python</h1>


<h2>Description</h2>
In my organization, we manage access to restricted content with an allow list of IP addresses, detailed in the <mark>allow_list.txt</mark> file. We also maintain a separate remove list to identify IP addresses that should no longer have access. I developed an algorithm to automate the process of updating the <mark>allow_list.txt</mark> file and removing those IP addresses.
<br />
<br />
My task is to examine the organization’s data in the <mark>employees</mark> and <mark>log_in_attempts</mark> tables. I’ll need to use SQL filters to retrieve records from these datasets and investigate the potential security issues.


<h2>Languages and Utilities Used</h2>

- <b>Python</b>
- <b>Jupyter</b> 


<h2>Program walk-through:</h2>
<h3 align="center">Open the file that contains the allow list</h3>

<p align="center">
The <mark>open()</mark> function in Python lets you access a file. First, you provide the file name (or in this case a variable holding the name). Then, you supply a string to specify how you want to handle the file. For reading the file, pass in <mark>"r"</mark> as the second parameter.
<br/>
<br />
<img src="https://imgur.com/s8Beo06.png" height="80%" width="80%" alt="Python Algorithm Steps"/>
</p>
<br />
<br />

<h3 align="center">Read the file contents</h3>

<p align="center">
The <mark>.read()</mark> method in Python allows you to read a file. To do so, call <mark>file.read()</mark> on the opened file. Then, to display the contents, pass the variable holding the file’s contents as an argument to the <mark>print()</mark> function.
<br/>
<br />
<img src="https://imgur.com/EinO9iB.png" height="80%" width="80%" alt="Python Algorithm Steps"/>
</p>
<br />
<br />

<h3 align="center">Convert the string into a list</h3>

<p align="center">
The <mark>.split()</mark> method in Python converts a string to a list. By default, it splits on whitespace, but you can specify a different character. In this case, the default behavior works well since each IP address in <mark>allow_list.txt</mark> is on a new line, and <mark>.split()</mark> will separate them into a list.
<br/>
<br />
<img src="https://imgur.com/g7zRWoU.png" height="80%" width="80%" alt="Python Algorithm Steps"/>
</p>
<br />
<br />

<h3 align="center">Iterate through the remove list</h3>

<p align="center">
I constructed a for loop to go through <mark>ip_addresses</mark>, starting with the <mark>for</mark> keyword. I then use <mark>element</mark> as the loop variable and <mark>in</mark> for the loop condition.

<br/>
<br />
<img src="https://imgur.com/teCI9ac.png" height="80%" width="80%" alt="Python Algorithm Steps"/>
</p>
<br />
<br />

<h3 align="center">Remove IP addresses that are on the remove list</h3>

<p align="center">
To build the conditional statement, I use the in operator to check if <mark>element</mark> is in <mark>remove_list</mark>. Then to remove <mark>element</mark> from <mark>ip_addresses</mark>, I call the <mark>.remove()</mark> method on <mark>ip_addresses</mark> and pass in <mark>element</mark>, <mark>ip_addresses.remove(element)</mark>.
<br/>
<br />
<img src="https://imgur.com/98mBkFa.png" height="80%" width="80%" alt="Python Algorithm Steps"/>
</p>
<br />
<br />

<h3 align="center">Update the file with the revised list of IP addresses </h3>

<p align="center">
I start the <mark>with</mark> statement by calling <mark>open()</mark>, passing the name of the file and <mark>"w"</mark> to indicate writing. Inside the <mark>with</mark> statement, I'll use <mark>.write()</mark> to replace the file's contents with <mark>ip_addresses</mark>, <mark>file.write(ip_addresses)</mark>.
<br/>
<br />
<img src="https://imgur.com/3WHh3JJ.png" height="80%" width="80%" alt="Python Algorithm Steps"/>
</p>
<br />
<br />

<h3 align="center">Summary</h3>

<p align="center">
I developed an algorithm that removes IP addresses listed in the <mark>remove_list</mark> variable from the <mark>allow_list.txt</mark> file. The process involves opening the file, converting its contents to a string, and then transforming that string into a list stored in the <mark>ip_addresses</mark> variable. I then iterate through each IP address in the <mark>remove_list</mark>. For each address, I check if it exists in the <mark>ip_addresses</mark> list. If it does, I use the <mark>.remove()</mark> method to delete it from <mark>ip_addresses</mark>. Finally, I use the <mark>.join()</mark> method to convert <mark>ip_addresses</mark> back into a string and overwrite the contents of <mark>allow_list.txt</mark> with the updated list.
<br />
<br />
<img src="https://imgur.com/hu36HkB.png" height="80%" width="80%" alt="Python Algorithm Steps"/>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
