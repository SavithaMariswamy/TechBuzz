Visual diff and merge tool. 

Aesthetic display of vimdiff output made me look for similar stuffs while using acme diff.   

Vimdiff <file1> <file2>  
It starts with vim and additionally displays the difference between the two files passed through the argument.
 
vimdiff is basically a softlink to vim.  Vim is intelligent enough to differentiate between vim, vimdiff etc….
vimdiff is the easiest way to edit in diff mode.   This would be of much help when we have magnanimous code changes in your private workspace. 


Same functionality as vimdiff can be availed in acme by integrating jmeld to acme.   Below are the steps to do the same. 
1)	Install and Download jmeld
2)	Write a small script which will be called through acme diff –cmd options
Eg.   Acme diff –cmd $HOME/script. 
Basically this scripts invoke jmeld with original and modified files.  Jmeld is invoked to find the diff between the two versions of file passed from acme. 
Script looks something like this. 
[savitham]$more launch
#!/bin/bash
shift
java -jar ~/meld/jmeld $@ 1>/dev/null

Note:  For jmeld to work you need to xserver running on your terminal
