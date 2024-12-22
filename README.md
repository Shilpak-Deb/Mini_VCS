**Author:** &nbsp; Shilpak Deb

Implementation of a mini version control system (VCS) that mimics the basic functionalities of Git

---

## Instructions for Execution:

The following are the steps for how to open the utulize the mini-version control system:

### How to create mygit executable file:

Navigate to inside the **Mini VCS** directory and execute the following command on the terminal:

```bash
make
```

### How to use mygit mini-VCS:

- Copy/Paste the **mygit** executable file inside whichever directory version control must be applied to (_becomes the home directory for mygit operations_).
- Run commands using mygit in the following format:

```bash
./mygit <command> <command args 1> <command args 2> ...
```

- Alternatively, the actual path to **mygit** executable file may be provided without copy/pasting the file itself:
- For example:

```bash
/home/shilpak-deb/Mini VCS/mygit <command> <command args 1> <command args 2> ...
```

---

## Directory Structure:

**Mini VCS**  
 &nbsp; &nbsp; -- makefile  
 &nbsp; &nbsp; -- mygit.h  
 &nbsp; &nbsp; -- main.cpp  
 &nbsp; &nbsp; -- misc.cpp  
 &nbsp; &nbsp; -- ignore.cpp  
 &nbsp; &nbsp; -- fileop.cpp  
 &nbsp; &nbsp; -- init_command.cpp  
 &nbsp; &nbsp; -- hash_object_command.cpp  
 &nbsp; &nbsp; -- cat_file_command.cpp  
 &nbsp; &nbsp; -- write_tree_command.cpp  
 &nbsp; &nbsp; -- ls_tree_command.cpp  
 &nbsp; &nbsp; -- add_command.cpp  
 &nbsp; &nbsp; -- commit_command.cpp  
 &nbsp; &nbsp; -- log_command.cpp  
 &nbsp; &nbsp; -- checkout_command.cpp  
 &nbsp; &nbsp; -- README.md  
 &nbsp; &nbsp; -- mygit

**(_Created on using init command_)**

&nbsp; &nbsp; -- **.mygit /**  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- HEAD  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- index  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- log  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- **commits /**  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- ecc2120710e70cd4b66b6ac19430a3c547731725 &nbsp; &nbsp; _(example commit hash #1)_  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- 9a4e78503fe268c104225667dbce8b8a6f08e3a1 &nbsp; &nbsp; _(example commit hash #2)_  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; -- . . .  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- **objects /**  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- **trees /**  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- a21930e200964ea662f96b80c3039e7c215e48e7 &nbsp; &nbsp; _(example tree hash #1)_  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- 62b9eaf95bb9d28b8420976b12c9be9807e79986 &nbsp; &nbsp; _(example tree hash #2)_  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- . . .  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- **blobs /**  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- 5a55e31ddd87fd89ac478b65fd90b847eb301df7 &nbsp; &nbsp; _(example blob hash #1)_  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- 10b2fd452d51a2aaf65c7785a13c4e6e9af398b2 &nbsp; &nbsp; _(example blob hash #2)_  
 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; -- . . .

---

## Directory Contents & Use:

**( Folder Name**: 2024201072_Assignment4 **)**

### makefile:

- Compiles the entire set of .cpp files in one go and create the '**mygit**' executable file

### header file:

- **mygit.h**: &nbsp; Allows the various functions and external global variables to be accessed from any of the .cpp files

### .cpp files:

- **main.cpp**: &nbsp; Possesses a main function which accepts command line arguments in order to execute **mygit**
- **misc.cpp**: &nbsp; Contains miscellaneous functions used multiple times throughout the program
- **ignore.cpp**: &nbsp; Utilized to check which files/directories can be ignored while carrying various file operations and hash calculations
- **fileop.cpp**: &nbsp; Contains to manipulate files/directories in multiple ways (create, remove, check if exists, file compression/decompression ... etc)
- **init_command.cpp**: &nbsp; Used to implement the **init** command
- **hash_object_command.cpp**: &nbsp; Used to implement the **hash-object** command (also contains a function to calculate SHA1 hash for any file)
- **cat_file_command.cpp**: &nbsp; Used to implement the **cat-file** command
- **write_tree_command.cpp**: &nbsp; Used to implement the **write-tree** command
- **ls_tree_command.cpp**: &nbsp; Used to implement the **ls-tree** command
- **add_command.cpp**: &nbsp; Used to implement the **add** command
- **commit_command.cpp**: &nbsp; Used to implement the **commit** command
- **log_command.cpp**: &nbsp; Used to implement the **log** command
- **checkout_command.cpp**: &nbsp; Used to implement the **checkout** command

### executable files:

- **mygit**: &nbsp; Executable file to run the mini-VCS

### readme file:

- **README.md**: &nbsp; The file you are reading _now_

### .mygit:

&nbsp; &nbsp; &nbsp; &nbsp; Hidden directory (**repository**) to keep track of various changes made to the files/directories inside present working directory over multiple 'versions'

- #### Files:

  - **HEAD**: &nbsp; Keeps track of the current commit's SHA1 hash &nbsp; &nbsp; (_initially empty_)
  - **index**: &nbsp; Temporarily stores data on various files/directories added to staging area before commit &nbsp; &nbsp;(_initially empty_) &nbsp; (_emptied after each successful commit_)
  - **log**: &nbsp; Keeps track of the history of various commits made &nbsp; &nbsp;(_initially empty_)

- #### Directories
  - **commits/**: &nbsp; Stores **commit** objects corresponding to the different commits &nbsp; &nbsp;(_initially empty_)
  - **objects/**  
     &nbsp; &nbsp; &nbsp; &nbsp; ---> **trees/**: &nbsp; Stores **tree** objects corresponding to the different directories &nbsp; &nbsp; (_initially empty_)  
     &nbsp; &nbsp; &nbsp; &nbsp; ---> **blobs/**: &nbsp; Stores **blob** objects corresponding to the different files &nbsp; &nbsp; (_initially empty_)

---

## Functionalities Implemented:

### Commands:

**init** &nbsp; -- &nbsp; _Used to initialize the repository_

- Implemented in: &nbsp; **init_command.cpp**
- Deletes the **.mygit** hidden directory (**repository**) if it is present
- Creates the **.mygit** hidden directory (**repository**) and its various subdirectories and files (all files/subdirectories are empty)

```bash
./mygit init
```

---

**hash-object** &nbsp; -- &nbsp; _utilized to calculate SHA1 hash for a file_

- Implemented in: &nbsp; **hash_object_command.cpp**
- Used to do the following (_based on flags provided_)
  - **no flag**: &nbsp; Calculate SHA1 hash of a file and display it (_file path must be provided)_
  - **-w**: &nbsp; Calculate SHA1 hash of a file and display it along with storing it in a separate **blob** object (f*ile path must be provided*)

```bash
./mygit hash-object <file_path>
./mygit hash-object -w <file_path>
```

- The **blob** object is stored in **.mygit/objects/blobs/**
- The name of the **blob object file** is the same as the **SHA1 hash** calculated previously, with the compressed contents of the original file stored inside it
- There are internal versions of the hash-object command that can return SHA1 hashes for files in a specific path while simulataneously storing them without displaying them to the user

---

**cat-file** &nbsp; -- &nbsp; _utilized to display the decompressed contents of a blob/tree object_

- Implemented in: &nbsp; **cat_file_command.cpp**
- Used to display the following when the corresponding SHA1 hash is provided (_based on flags provided_)
  - **-p**: &nbsp; Decompressed contents of a **blob** or **tree** object
  - **-s**: &nbsp; Size of the decompressed contents of a **blob** or **tree** object
  - **-t**: &nbsp; Type of object: **blob** or **tree**

```bash
./mygit cat-file -p <hash>
./mygit cat-file -s <hash>
./mygit cat-file -t <hash>
```

- The contents of the corresponding **blob** or **tree object file** are read (the _blob_ object files are decompressed first) and that data is utilized to carry out different operations based on the flag provided (as mentioned previously)

---

**write-tree** &nbsp; -- &nbsp; _utilized to create a tree object for the entire current directory_

- Implemented in: &nbsp; **write_tree_command.cpp**
- Used to create a tree object for the current directory and display the its SHA1 hash

```bash
./mygit write-tree
```

- The **tree** object is stored in **.mygit/objects/trees/**
- There are internal versions of the write-tree command that can provide SHA1 hashes for directories in a specific path
- The internal versions of the write-tree and hash-object command are utilized to recursively search through the entire directory based on the path provided and store **blob** or **tree** hashes for the contents of the directory in the following for format:

```bash
<permissions> <object type> <hash> <file/directory name>
```

- While searching through the current directory, the following is done depending on whether files or directories are encountered:
  - **File**: &nbsp; If files are encountered, a **blob** object of the file is created and its hash stored via the internal version of the **hash-object** command
  - **Directory**: &nbsp; If directories are encountered, a **tree** object of the directory is created and its hash stored via recursively calling the internal version of the **write-tree** command
- The contents of the **tree object** thus calculated are stored in a **temp** file
- The hash of this **temp** file is then calculated and the **temp** file renamed to this **tree hash**

---

**ls-tree** &nbsp; -- &nbsp; _utilized to display the contents a tree object via its tree hash_

- Implemented in: &nbsp; **ls_tree_command.cpp**
- Used to display the contents of a tree object based its SHA1 hash and depending on the following flags:
  - **no flag**: &nbsp; Display detailed information
  - **--name-only**: &nbsp; Display only the names of the files/directories present

```bash
./mygit ls-tree <tree hash>
./mygit ls-tree --name-only <tree hash>
```

- Only files/directories present directly inside the directory which the **tree object** represents, are displayed - not the contents of the subdirectories themselves &nbsp; (_similar to the POSIX ls command_)

---

**add** &nbsp; -- &nbsp; _utilized to add files/directories to the staging area brfore commit_

- Implemented in: &nbsp; **add_command.cpp**
- Used to add files/directories to staging area based on the following:
  - **add .**: &nbsp; Adds the entire directory
  - **otherwise**: &nbsp; Adds subdirectories or files

```bash
./mygit add .
./mygit add <file/directory 1> <file/directory 2> ...
```

- Data of file/directory is stored into **index** file (**staging area**) in the following format:

```bash
<permissions> <object type> <hash> <file/directory path>
```

- First checks if the **index** file (**staging area**) is empty - if it is, then a '_snapshot_' of the current directory (i.e. a **tree object**) is stored into **index** first
- The details of the other files/subdirectories is stored next

---

**commit** &nbsp; -- &nbsp; _utilized to commit changes in the staging area_

- Implemented in: &nbsp; **add_command.cpp**
- Used to commit all files/directories in staging area and add a message based on the following flags:
  - **no flag**: &nbsp; A default message is assigned to commit
  - **-m**: &nbsp; A specific message as decided by the user is assigned to commit

```bash
./mygit commit
./mygit commit -m <message>      (without quotes)
./mygit commit -m '<message>'    (in single quotes)
./mygit commit -m "<message>"    (in double quotes)
```

- The SHA1 hash of the **index** file is calculated and a new **commit** object with file name as the calculated hash is created in **.mygit/commits/**
- The contents of the index file is copied to the newly created **commit** object
- The SHA1 hash of the parent commit is obtained from **HEAD** file - if the **HEAD** file is empty (i.e no commits have been made before), then "----------------------------------------" is assigned to it
- The **log** is updated for the new commit with the following information:
  - **Current Commit SHA**: SHA1 hash calculated previously
  - **Parent Commit SHA**: Parent SHA obtained from **HEAD**
  - **Timestamp**: Current date/time
  - **Commiter name**: Name of the current commiter (user name obtained from system)
  - **Message**: User-provided or default message
- The **HEAD** file is updated with the SHA1 hash of the current commit
- The **index** file (**staging area**) is emptied to prepare it for the next commit

---

**log** &nbsp; -- &nbsp; _utilized to display commit history_

- Implemented in: &nbsp; **log_command.cpp**

```bash
./mygit log
```

- The data stored in the **log** file is retrieved and displayed in reverse order (latest first)

---

**checkout** &nbsp; -- &nbsp; _utilized to restore the current directory to a previous commit_

- Implemented in: &nbsp; **add_command.cpp**

```bash
./mygit checkout <commit hash>
```

- The contents of the **commit** object corresponding to the hash provided is read
- The first line of the **commit** object represents the snapshot of the directory before any files were added - this is used to restore the directory to a previous state
- The contents of the current directory is first deleted and data is restored according to the current working directory snapshot (**tree** object) by recursively traversing the contents of the **tree** object
- The files/subdirectories added later are then restored by reading the remaining lines of the **commit** object\*
- The **HEAD** file is updated with the **commit hash** provided by the user

---

## Dependencies:

- This program works only for linux-based operating systems (due to using linux-specific system calls)
- SHA1 is calculated via **openssl/sha.h**
- File compression/decompression is done via **zlib.h**

---
