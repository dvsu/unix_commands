# Unix Commands

Most commonly used Unix commands

## `scp`

1. Transfer a file to a remote machine

   ```bash
   scp {source} {remote_user_name}@{destination_host}:{directory}
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
   scp -r {source} {remote_user_name}@{destination_host}:{directory}
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
   export {variable_name}={variable_value}
   ```

   ***Examples***

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
   unset {variable_name}
   ```

   ***Examples***

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
   echo ${variable_name}
   ```

   ***Example 1***

   Display an environment variable

   ```bash
   echo $SHELL
   ```

   ***Output***

   ```none
   /bin/bash
   ```

   ***Example 2***

   Display multiple environment variables

   ```bash
   echo $SHELL $USER $LANG
   ```

   ***Output***

   ```none
   /bin/bash ubuntu C.UTF-8
   ```

## `printenv`

1. Show/ display all environment variables

   ***Example***

   ```bash
   printenv
   ```

   ***Output***

   ```none
   SHELL=/bin/bash
   LANG=C.UTF-8
   USER=ubuntu
   ...
   ```
