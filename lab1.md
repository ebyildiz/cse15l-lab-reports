# Lab Report 1

### `cd`
- *Share an example of using the command with no arguments.*
  + <img width="366" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/3a15c191-8309-48db-a909-a84c8cbd63e0">
  + the directory before was `lecture1` and after putting in `cd` with no arguments, it went back to the home directory
  + `cd` is used for going to a specific directory and if it's used with no arguments, it goes back to the main directory since there was no directoy specified as an argument
  + output is not an error
- *Share an example of using the command with a path to a directory as an argument.*
  + <img width="352" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/e779cad0-c328-4962-af2c-85613294f64a">
  + the directory before was the home directory and when I used `cd` with the argument `lecture1` it switched the directory to the `lecture1` folder
  + since this time, `cd` was used with a specific directory as an argument, it switched to the specified directory as it functions to do so
  + output is not an error
- *Share an example of using the command with a path to a file as an argument.*
  + <img width="335" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/a42b5f62-7528-4c3e-9b9a-16bfc01f8a80">
  + the directory in this case stays the same because the git bash gives an error saying `bash: cd: lecture1/Hello.java: Not a directory`
  + the reason for this error is because `cd` is used to switch directories, it can open a specific folder for you or go back to the previous or home directory. However, in this case we gave a file path as an argument which cd is not functioned to open
  + output is an error like mentioned above

### `ls`
- *Share an example of using the command with no arguments.*
  + <img width="460" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/b024d473-0de7-49cb-a786-86a400013169">
  + the absolute path does not change at all as `ls` is not functioned to switch directories like `cd`: it's still the home directory
  + the output is all the files and folders that are in the current directory without no arguments
  + output is not an error
- *Share an example of using the command with a path to a directory as an argument.*
  + <img width="316" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/3e84ed6d-6210-4908-b675-0226ecf2db24">
  + the absolute path does not change at all as `ls` is not functioned to switch directories like `cd`
  + the output is all the files and folders that are in the directory that we put as an argument
  + output is not an error
- *Share an example of using the command with a path to a file as an argument.*
  + <img width="362" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/14fc32a5-a0f0-4592-93c3-1e7f37490124">
  + the absolute path does not change at all as `ls` is not functioned to switch directories like `cd`
  + the output it the file's name. The reason for this might be because `ls` give the name of the contents of a given argument. If a file is given as an argument, since the contents of this file is the file itself, it would make sense why the output is the given file's name.
  + output is not an error


### `cat`
- *Share an example of using the command with no arguments.*
  + <img width="266" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/ef982610-c883-45d6-a3db-93938aaee366">
  + without no input, `cat` expects you to still put an input so basically nothing happens
  + it makes sense since `cat` is a command for getting information regarding a specific file/files in a folder. If you don't give it any path, it can't give you any information so it still expects you to enter a path
  + output is not an error
- *Share an example of using the command with a path to a directory as an argument.*
  + <img width="260" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/9cc3b11b-efd8-4428-8449-869d892953ad">
  + with an argument as a path to a directory, cat just tells you that the given argument is a directory
  + the reason for this output is because cat is supposed to give information about a specific file, for directories, it only tells you that this argument given is a directory 
  + output is not an error
- *Share an example of using the command with a path to a file as an argument.*
  + <img width="568" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/4f841f8f-f617-4581-a027-96c932051bfb">
  + with an argument as a path to a file, `cat`  works as it functions to. It outputs the content of the given file.
  + output is not an error

