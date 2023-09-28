Open the file that contains the allow list
------------------------------------------

For the first part of the algorithm, I opened the "allow_list.txt" file. First, I assigned this file name as a string to the import_file variable:

![Screenshot of Python code that assigns "allow_list.txt" to the import_file variable](https://lh3.googleusercontent.com/Pf841FkYHPg70wYS42SpzGJVWvZRbpaPNO7S5poRAy0ZiREd2QJ5N3WSTO8OYSg8n7TDDTOPeJvwPs77zcClTiy_PQy_tLCKjlnmYt_jf2_1OglwU0hf2pbVobHMEw_komOysTHOOAgz_2fiJLmjW-62RkuOdNVr-aglXOWkF4QkfHW3zh_IMnlIdFq7rVEK194BS28_k-ypVHdNKWRQbQIrnvk1Bk-SBvC0ow)

Then, I used a WITH statement to open the file:

![Screenshot of Python code that uses a with statement to open the file](https://lh4.googleusercontent.com/ADTvJBFj6FFN1yhleaPfBH9jWZfLl6-cigjtEQL1O6iUTE7nwa1-2fpZ0CbVzrpoFoebNPsCe8g_hKhdMp-QfGh7gKj96Re0QPzqXAaxhKp8hVok0ziw1mm1t5d0sHgdq2KsmFVkSHQwGti97nVvVV0-RdqCaMf-ZskDawP4ll4KWCDUkLI0uDKlN78NfeBfwis_f0zved9dI1PJiXFt1oMRnTaRNGDEn33Syg)

In my algorithm, the with statement is used with the .open() function in read mode to open the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to access the IP addresses stored in the allow list file. The WITH keyword will help manage the resources by closing the file after exiting the WITH statement. In the code with open(import_file, "r") as file:, the open() function has two parameters. The first identifies the file to import, and then the second indicates what I want to do with the file. In this case, "r" indicates that I want to read it. The code also uses the as keyword to assign a variable named file; file stores the output of the .open() function while I work within the WITH statement.

Read the file contents
----------------------

In order to read the file contents, I used the .read() method to convert it into the string.

![Screenshot of Python code that includes the .read() method](https://lh5.googleusercontent.com/kPZxz3hT0GBJH8wAe-7LM1i7g8Q7cRPqxuuZWEPRUNK1Um7Q9y0NtsNZBtu87E6cR5IMPDVX6KUhEfE9EDNSuLICKg7cUIZrhg_eTwy65Hrn1Hc_31JxL7op9-lGwJiBDkOAmNXb1fZkEVw97YaVirK_FW8okMnz6yBWkhorzLSoMsCwwGo_amB5lSS7teacWDcJcMbzNADOBTKtfc2TGspL8KIkNuzmh1W6ug)

When using an .open() function that includes the argument "r" for "read," I can call the .read() function in the body of the WITH statement. The .read() method converts the file into a string and allows me to read it. I applied the .read() method to the file variable identified in the with statement. Then, I assigned the string output of this method to the variable ip_addresses.

In summary, this code reads the contents of the "allow_list.txt" file into a string format that allows me to later use the string to organize and extract data in my Python program.

Convert the string into a list
------------------------------

In order to remove individual IP addresses from the allow list, I needed it to be in list format. Therefore, I next used the .split() method to convert the ip_addresses string into a list:

![Screenshot of Python code that includes the .split() method](https://lh6.googleusercontent.com/7DSCX3nNkGiekEOo79KSgoqbVJV7Keg10yxZz6EESJYMqg-H49zFI9ggNDzuaBN3cNp4XqmtkywQLcFC4yRWU9qnERkFI36CaeyhnQsFdGm2F6BO18eDxknwrK_BHHZufQ98eDr1z9e3pCBXGb3AWjQRw-5imX0AJwcfX52vztEnGkO5M847f_nZz_8LXSFNn_BjIopLfg4V_0UTdvqa95gonQ5LfKGJ6y0x4Q)

The .split() function is called by appending it to a string variable. It works by converting the contents of a string to a list. The purpose of splitting ip_addresses into a list is to make it easier to remove IP addresses from the allow list. By default, the .split() function splits the text by whitespace into list elements. In this algorithm, the .split() function takes the data stored in the variable ip_addresses, which is a string of IP addresses that are each separated by a whitespace, and it converts this string into a list of IP addresses. To store this list, I reassigned it back to the variable ip_addresses. 

Iterate through the remove list
-------------------------------

A key part of my algorithm involves iterating through the IP addresses that are elements in the remove_list. To do this, I incorporated a for loop:

![Screenshot of Python code that includes the for loop header](https://lh3.googleusercontent.com/h07mW-frwCbGvATmjhnCYioGznyX4XQRH0idcm4o6HAtUWZe8je4bUuO7K-gBZtmQ2uDs0tcQnherWEdmsknCZSFFVbRImXfr8a8EtgpfmUNQY6onXDST0BBeZNWLyhCC1nnQi2IgwT20eVmTL_EzRvurrnxSLGagGh8pved8CNoH_pSsr-hTimItSgpuaUVRW-9JmNVv_2VC7HiSRbJngPqTIj9NLGzsPFFnA)

The for loop in Python repeats code for a specified sequence. The overall purpose of the for loop in a Python algorithm like this is to apply specific code statements to all elements in a sequence. The for keyword starts the for loop. It is followed by the loop variable element and the keyword in. The keyword "in" indicates to iterate through the sequence ip_addresses and assign each value to the loop variable element. 

Remove IP addresses that are on the remove list
-----------------------------------------------

My algorithm requires removing any IP address from the allow list, ip_addresses, that is also contained in remove_list.  Because there were not any duplicates in ip_addresses, I was able to use the following code to do this:

![Screenshot of Python code that incorporates a conditional and the .remove() method into the body of the for loop](https://lh5.googleusercontent.com/jvUvM9HPOPxX25SPFcbIOxpvdaCnrhq0mXjdrLZNLPbPMJT01QnQJJ8r3Zxdj5_RMeLbUHWWRz1SFOYWj1qn2-t427LRb7dzCDkfOmA-k55nKE0iKYDUlYILp0LQpGB5qdPLzXICtZ7ahF3E7-aEsm7fUR1khRN-zSJhmGpos19ypXKjBxmiYB8sApZUOBNLi3rjZSAo8Efw0u3X_f0aMTWiX4YVBZODf-RKZw)

First, within my for loop, I created a conditional that evaluated whether or not the loop variable element was found in the ip_addresses list. I did this because applying .remove() to elements that were not found in ip_addresses would result in an error.\
Then, within that conditional, I applied .remove() to ip_addresses. I passed in the loop variable element as the argument so that each IP address that was in the remove_list would be removed from ip_addresses.

Update the file with the revised list of IP addresses 
------------------------------------------------------

As a final step in my algorithm, I needed to update the allow list file with the revised list of IP addresses. To do so, I first needed to convert the list back into a string. I used the .join() method for this:

![Screenshot of Python code that includes the .join() method](https://lh4.googleusercontent.com/JAobRg9yeO_JtEoTpeySbQFfXK9kk1TwJHRtj8n8zMVQ_qMJQlqjkkuWLc37TeOQByHI02Tkr5rl84FNbmnSEnIaa1zLnbALUmClAm1Ei1Y152P8s-5fcfOPg5IPoo1JkmF8Mfp-mT5vOBzW1eZXie0OHq9V6wauuU4y8uPiB7xoLtBzI0A7XGGkhgNlk10236VTPxA2VzWRTJVGgQjcqdEC0hbmngTyWfEExQ)

The .join() method combines all items in an iterable into a string. The .join() method is applied to a string containing characters that will separate the elements in the iterable once joined into a string. In this algorithm, I used the .join() method to create a string from the list ip_addresses so that I could pass it in as an argument to the .write() method when writing to the file "allow_list.txt". I used the string ("\n") as the separator to instruct Python to place each element on a new line.

Then, I used another WITH statement and the .write() method to update the file:

![Screenshot of Python code that includes a with statement and the .write() method](https://lh6.googleusercontent.com/qOts2-BZmlo4hXAUjYrLZ3giHc2JC-hNk6-dlxhRKf_J1CayyLJyaVIO1Nd3-nroW1XYRkxo9OCLQL5C4aKurrXmBp4knoX6iVINjSVuRLlqHMjONQpGfEWHMEd3SaPT0VCaI1ZX_OVqMzYnowsxFOsdBRJpO_1Wh8qZNH5B7N-vI8tHYMjQBO27AlASEIY3A7tYTRS_68FN-fxNB-irS2cRzGA5SFSkM731DA)

This time, I used a second argument of "w" with the open() function in my WITH statement. This argument indicates that I want to open a file to write over its contents. When using this argument "w", I can call the .write() function in the body of the WITH statement. The .write() function writes string data to a specified file and replaces any existing file content.

In this case, I wanted to write the updated allow list as a string to the file "allow_list.txt". This way, the restricted content will no longer be accessible to any IP addresses that were removed from the allow list. To rewrite the file, I appended the .write() function to the file object file that I identified in the with statement. I passed in the ip_addresses variable as the argument to specify that the contents of the file specified in the with statement should be replaced with the data in this variable.

Summary
-------

I created an algorithm that removes IP addresses identified in a remove_list variable from the "allow_list.txt" file of approved IP addresses. This algorithm involved opening the file, converting it to a string to be read, and then converting this string to a list stored in the variable ip_addresses. I then iterated through the IP addresses in remove_list. With each iteration, I evaluated if the element was part of the ip_addresses list. If it was, I applied the .remove() method to it to remove the element from ip_addresses.. After this, I used the .join() method to convert the ip_addresses back into a string so that I could write over the contents of the "allow_list.txt" file with the revised list of IP addresses.
