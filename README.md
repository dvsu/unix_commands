# Unix Commands

Most commonly used Unix commands

## `scp`

1. Transfer a file to a remote machine

   ```none
   scp {source} {remote_user_name}@{destination_host}:{directory}
   ```

   **_Example_**

   ```none
   scp ./myfile.txt alien@lightyearsaway.com:~/dropmehere
   ```

   **_Output_**

   At remote machine

   ```none
   ~/dropmehere/myfile.txt
   ```

2. Transfer a directory to a remote machine

   ```none
   scp -r {source} {remote_user_name}@{destination_host}:{directory}
   ```

   **_Example_**

   Copying a directory `myfolder` which contains multiple files `file1.txt`, `file2.txt`, and `file3.txt`

   ```none
    scp -r ./myfolder alien@lightyearsaway.com:~/dropmehere
   ```

   **_Output_**

   At remote machine

   ```none
   ~/dropmehere/myfolder/file1.txt
   ~/dropmehere/myfolder/file2.txt
   ~/dropmehere/myfolder/file3.txt
   ```
