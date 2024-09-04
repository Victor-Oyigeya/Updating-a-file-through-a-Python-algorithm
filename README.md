# Updating a file through a Python algorithm
## Project description
[Updating the list of IP addresses that are allowed to access restricted content. There are some IP addresses that are on the approved list that are not allowed to access restricted content. We are given a list of IP addresses that are not supposed to be on the list, so we used that information to remove them. ]
## Environment/Labs used
- <b>Jupyter Notebook</b>
## Project Walk-through:
### Assign two variables and open the file that contains the allow list in read mode
[ ![Screenshot 2024-08-13 182733](https://github.com/user-attachments/assets/461aace2-4e0b-4554-b7fb-236b00efacb5)

For the first part of the algorithm, I opened the <b>"allow_list.txt"</b> file. First two variables were assigned. <b>"import_file"</b>, which was assigned the allow list text file, and <b>"remove_list"</b>, which was assigned the list of IP addresses to remove. To open the <b>“allow_list.txt”</b>  file, we start a with statement.  <b>"with"</b> keyword is used in conjuction with the <b>"open()"</b> function to open a file in diferent modes. <b>open()</b> function takes in two parameters,  Imort_file which is a variable storing the allow list text file, and “r” which tells python that we want to read the file. All these information will be stored in a new variable, ‘file’, using the <b>"as"</b> keyword.]
### Read the file contents
[![Screenshot 2024-08-13 213325](https://github.com/user-attachments/assets/bb2a1492-c057-401b-85ee-6d9f7425498d)

The previous code was used to open the allow list text file. To read the file we are going to use the .read() method. The function converts the output of the allow list to a string data and the result was stored in a variable, <b>"ip_addresses"</b> .]
### Convert the string into a list
[ ![Screenshot 2024-08-13 213406](https://github.com/user-attachments/assets/21b0caaf-0d6f-4795-903d-d638463710b1)


.split() is used to convert a string into a list data. The function is used after the variable that stores the string we want to convert. This new information is returned back to the ‘“ip_addresses” variable. ]
### Iterate through the remove list
[ ![Screenshot 2024-08-13 200101](https://github.com/user-attachments/assets/229dc15c-0cb0-40d5-af9f-6a32dd23a7fb)

This section starts with a for loop with a loop variable, “element”, that iterates through the “Ip_addresses” variable . for element in ip_addresses stores elements in “ip_addresses”  in  element variable created in the for loop. Then we write a conditional statement “if element in remove_list inside the for loop to check if there are any list of  IP addresses that are both in the  approved list and the remove list.]
### Remove IP addresses that are on the remove list
[ ![Screenshot 2024-08-13 200827](https://github.com/user-attachments/assets/5466f14d-34cf-49d3-88cb-a9f2278a59b1)

The next line of code in the conditional statement uses the .remove() method to delete the elements in the remove list from the list of approved IP addresses. The element variable stored the list of IP addresses to be removed, so we use it as an argument in the function. The list of removed IP addresses will then be deleted from the list in the “ip_addresses” variable, which stores the list of approved IP addresses.]
### Update the file with the revised list of IP addresses 
[![Screenshot 2024-08-13 184007](https://github.com/user-attachments/assets/d6ad1c86-792b-4fad-b21e-a10f320065a2)

To update the file with the revised list of IP addresses, we must first convert list back to string. Typing in “ “.join(ip_addresses)” will do just that. The .join() method converts a list data to string. After converting to string, we start a with statement to open the allow_list.txt up, and indicate, with, “w”,  that we want to write to the file. This information is stored in the ‘file’ variable. In sixth line of this section, we update the file by passing in the “ip_addresses” variable, which contains the revised list of IP addresses, into the .write() function and place the “file” variable in front to indicate the list we want to update. This will replace all information in the “file” variable.  ]
## Summary
[We updated a list of approved IP addresses by removing those that shouldn’t be on the list. We created an algorithm using functions and statements. “With” keyword is used with “open()” function to open the file for both reading and writing. “.read()” method was used to read the file, while “.write()” was used to replace the files in the allow list with a revised list of IP addresses. The “.split()” method was used to convert string to list, while the “.join()” method was used to convert list to string data, to use for different purposes in the algorithm. A “for” loop is used to iterate through the list in “ip_addresses”, which stored the list of approved addresses, and an “if” statement checks for the condition of whether the elements in the removed list is also in the approved list. If the condition is true, then the “.remove()” method was used to delete any IP address not approved, from the allow list. This updated list was then used to replace all the information in the original text file “allow_list.txt”.]
