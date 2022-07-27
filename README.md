# Unix Commands

Most commonly used Unix commands

## `scp`

1. Transfer a file to a remote machine

   ```bash
   scp [source] [remote_user_name]@[destination_host]:[directory]
   ```

   **_Example_**

   ```bash
   scp ./myfile.txt alien@lightyearsaway.com:~/dropmehere
   ```

   **_Output_**

   At remote machine

   ```none
   ~/dropmehere/myfile.txt
   ```

2. Transfer a directory to a remote machine

   ```bash
   scp -r [source] [remote_user_name]@[destination_host]:[directory]
   ```

   **_Example_**

   Copying a directory `myfolder` which contains multiple files `file1.txt`, `file2.txt`, and `file3.txt`

   ```bash
    scp -r ./myfolder alien@lightyearsaway.com:~/dropmehere
   ```

   **_Output_**

   At remote machine

   ```none
   ~/dropmehere/myfolder/file1.txt
   ~/dropmehere/myfolder/file2.txt
   ~/dropmehere/myfolder/file3.txt
   ```

## `export`

1. Set environment variable

   Environment variable should be capitalized by convention.

   ```bash
   export [variable_name]=[variable_value]
   ```

   **_Examples_**

   Set an environment variable

   ```bash
   export VAR1=SOMEVALUE
   ```

   Set multiple environment variables

   ```bash
   export VAR1=VALUE1 VAR2=123 VAR3=SECRET
   ```

## `unset`

1. Unset environment variable

   ```bash
   unset [variable_name]
   ```

   **_Examples_**

   Unset/ remove an environment variable

   ```bash
   unset VAR1
   ```

   Unset multiple environment variables

   ```bash
   unset VAR1 VAR2 VAR3
   ```

## `echo`

1. Show/ display environment variable value

   ```bash
   echo $[variable_name]
   ```

   **_Example 1_**

   Display an environment variable

   ```bash
   echo $SHELL
   ```

   **_Output_**

   ```none
   /bin/bash
   ```

   **_Example 2_**

   Display multiple environment variables

   ```bash
   echo $SHELL $USER $LANG
   ```

   **_Output_**

   ```none
   /bin/bash ubuntu C.UTF-8
   ```

## `printenv`

1. Show/ display all environment variables

   **_Example_**

   ```bash
   printenv
   ```

   **_Output_**

   ```none
   SHELL=/bin/bash
   LANG=C.UTF-8
   USER=ubuntu
   ...
   ```

## `grep`

1. Search for a word in a file

   **_Command_**

   ```bash
   grep [keyword] [filename]
   ```

   ```bash
   cat [filename] | grep [keyword]
   ```

   **_Example_**

   Assume you are looking for a word _porta_ in a text file _words.txt_ contains the following words.

   ```none
   Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc viverra metus nec est imperdiet venenatis. Nam augue libero, consequat vel luctus id, ultricies eu elit. Sed scelerisque porta metus, et lacinia ipsum posuere et. Quisque risus velit, pretium quis scelerisque sed, sodales convallis mi.
   ```

   ```bash
   grep porta words.txt
   ```

   **_Output_**

   ```none
   Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc viverra metus nec est imperdiet venenatis. Nam augue libero, consequat vel luctus id, ultricies eu elit. Sed scelerisque porta
                                                               -----
   metus, et lacinia ipsum posuere et. Quisque risus velit, pretium quis scelerisque sed, sodales convallis mi.
   ```

2. Search for a keyword in many files (recursively)

   **_Command_**

   ```bash
   grep -R [keyword] [path]
   ```

   **_Example_**

   Assume you are looking for a word _result_ in all files, in current directory, the command is

   ```none
   grep -R result .
   ```

   **_Output Format_** _(if found)_

   ```none
   [filename]:[text]
   ```

## `uniq`

1. Print/ output unique lines extracted from a file

   **_Command_**

   ```bash
   uniq [filename]
   ```

   **_Example_**

   Assume you want to filter out duplicates in _words.txt_ with the following content.

   ```none
   one
   one
   one
   two two
   five five five
   zero zeroooo zero
   ```

   ```bash
   uniq words.txt
   ```

   **_Output_**

   ```none
   one
   two two
   five five five
   zero zeroooo zero
   ```

   **_Note_**

   It does not remove any duplicates on the same line.

## `sed`

1. Replace any matching string with the new string

   **_Command_**

   ```bash
   sed s/[string_lookup]/[new_string]/g [filename]
   ```

   **_Example_**

   Replacing string _one_ with _ten_ and the content of file is

   ```none
   one
   onetwo
   zeroonetwo
   two two
   five five five
   zero zeroooo zero
   ```

   ```bash
   sed s/one/ten/g words.txt
   ```

   **_Output_**

   ```none
   ten
   tentwo
   zerotentwo
   two two
   five five five
   zero zeroooo zero
   ```

   **_Note_**

   It prints the modified content but does not modify the original content in the file.
