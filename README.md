# Updating a file through a Python algorithm
## Project description
[Updating the list of IP addresses that are allowed to access restricted content. There are some IP addresses that are on the approved list that are not allowed to access restricted content. We are given a list of IP addresses that are not supposed to be on the list, so we used that information to remove them. ]
## Environment/Labs used
- <b>Jupyter Notebook</b>
## Project Walk-through:

### Assign two variables and open the file that contains the allow list in read mode
[![Screenshot 2024-08-13 182733](https://github.com/user-attachments/assets/461aace2-4e0b-4554-b7fb-236b00efacb5)

For the first part of the algorithm, I opened the <b>"allow_list.txt"</b> file. First two variables were assigned. <b>"import_file"</b>, which was assigned the allow list text file, and <b>"remove_list"</b>, which was assigned the list of IP addresses to remove. To open the <b>“allow_list.txt”</b>  file, we start a <b>with</b> statement. <b>"with"</b> is used to open and close files properly. <b>"with"</b> keyword is used in conjuction with the <b>"open()"</b> function to open a file in different modes. The <b>open()</b> function takes in two arguments,  <b>Imort_file</b> which is a variable storing the allow list text file, and <b>“r”</b> which tells python we want to read the file. All these information will be stored in a new variable, <b>‘file’</b>, using the <b>"as"</b> keyword.]

### Read the file contents
[ To read the contents on the allow list, I used the <b>.read()</b> method.

![Screenshot 2024-08-13 213325](https://github.com/user-attachments/assets/bb2a1492-c057-401b-85ee-6d9f7425498d)

The previous code was used to open the allow list text file in read mode ("r"). In this line, the code is written in the body of the <b>with</b> statement for proper handling. I applied the <b>.read()</b> to the <b>file</b> variable identified in the <b>with</b> statement. The <b>.read()</b> method converts the output of the allow list to a string data and allows me to read it. The result was stored in a variable <b>"ip_addresses"</b> .]

### Convert the string into a list
[![Screenshot 2024-08-13 213406](https://github.com/user-attachments/assets/21b0caaf-0d6f-4795-903d-d638463710b1)


<b>.split()</b> is used to convert a string into a list data. The function is appended to the <b>ip_addresses</b> variable, which converts contents in the varaiable from a string to list data. The purpose of splitting <b>ip_addresses</b> into a list is to make it easier to remove IP addresses from the allow list. This new information is returned back to the <b>ip_addresses</b> variable. ]

### Iterate through the remove list
A key part of my algorithm involves iterating through the IP addresses that are elements in the <b>remove_list</b>. To do this, I incorporated a for loop:


[![Screenshot 2024-09-06 142811](https://github.com/user-attachments/assets/92cfb62e-1d1a-43ab-aa84-7dd029b1cda5)

The <b>for</b> loop in Python repeats code for a specified sequence. The overall purpose of the for loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The <b>"for"</b> keyword starts the for loop. It is followed by the loop variable <b>"element"</b> and the keyword <b>"in"</b>. The keyword <b>"in"</b> indicates to iterate through the sequence <b>"ip_addresses"</b> and assign each value to the loop variable <b>"element"</b>.]

### Remove IP addresses that are on the remove list
[![Screenshot 2024-09-06 143046](https://github.com/user-attachments/assets/b3727780-bcff-450e-a29c-1855f2f8948b)

First, within my for loop, I created a conditional that evaluated whether or not the loop variable element was found in the ip_addresses list. I did this because applying .remove() to elements that were not found in ip_addresses would result in an error. 

In the next line of code within the conditional statement, the .remove() method is applied to ip_addresses and element is passed in as an argument in the function to delete the elements on the remove list from the list of approved IP addresses.

### Update the file with the revised list of IP addresses 
As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the .join() method for this:

[![Screenshot 2024-09-06 141648](https://github.com/user-attachments/assets/b628065d-4379-4ed2-b82c-50996fc7eac7)


The .join() method combines all items in an iterable into a string. The .join() method is applied to a string containing characters that will separate the elements in the iterable once joined into a string. In this algorithm, I used the .join() method to create a string from the list ip_addresses so that I could pass it in as an argument to the .write() method when writing to the file "allow_list.txt". I used the string ("\n") as the separator to instruct Python to place each element on a new line. 

Then, I used another with statement and the .write() method to update the file:
  
![Screenshot 2024-08-13 184006](https://github.com/user-attachments/assets/0ccc65b2-8bda-48e6-8961-abc797fdac51)

This time, I used a second argument of "w" with the open() function in my with statement. This argument indicates that I want to open a file to write over its contents. When using this argument "w", I can call the .write() function in the body of the with statement. The .write() function writes string data to a specified file and replaces any existing file content. 

In this case I wanted to write the updated allow list as a string to the file "allow_list.txt". This way, the restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the .write() function to the file object file that I identified in the with statement. I passed in the ip_addresses variable as the argument to specify that the contents of the file specified in the with statement should be replaced with the data in this variable.

## Summary
[We updated a list of approved IP addresses by removing those that shouldn’t be on the list. We created an algorithm using functions and statements. “With” keyword is used with “open()” function to open the file for both reading and writing. “.read()” method was used to read the file, while “.write()” was used to replace the files in the allow list with a revised list of IP addresses. The “.split()” method was used to convert string to list, while the “.join()” method was used to convert list to string data, to use for different purposes in the algorithm. A “for” loop is used to iterate through the list in “remove_list”, which stored the list of IP addresses we want to remove, and an “if” statement checks for the condition of whether the elements in the allow list is also in the remove list. If the condition is true, then the “.remove()” method was used to remove any IP address not approved, from the allow list. This updated list was then used to replace all the information in the original text file “allow_list.txt”.]
