## LAB REPORT 4

### screenshot

<img width="471" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/8567b388-b17c-46fd-bfd5-4262ff9eead8">
<img width="503" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/be075812-2b44-4233-8f31-ee9f753d95ff">





### keys used

`ssh<space>eyildiz@ieng6.ucsd.edu<enter>`

`git<space>clone<space>git@github.com:ebyildiz/lab7-cse15l.git<enter>`

`cd<space>lab7-cse15l<enter>`

`sh<space>test.sh<enter>`

`vim<space>ListExamples.java<enter>`

`/cha<enter>JLLL<backspace>2<esc>:wq<enter>`

`sh<space>test.sh<enter>`

`git<space>commit<space>-m<space>"fixed"<enter>`

`git<space>push<enter>`

### summary

+ `ssh` helped me connect to the ieng6 server, then I cloned the github repository that I forked using `git clone` and then the ssh link. After that, I changed my directory to the github folder to test my java files.
+ `sh` helped me test my ListExamples.java file using the lines in `test.sh`. After this, some tests will fail due to an error in ListExamples
+ At this point, I used `vim` to edit my java file. `vim` allows users to edit their files faster, from the command line only.
    - After using `vim` and going into the file.
    - Inside `vim` there is a function `/` which is a way to search for a specific string in the given file. The string I was searching for was "cha" which allowed me to go to the specific comment where the error is that starts with "change". AFter pressing enter, I was able to locate to the point in that comment. I used this command to decrease the amount of keys used to navigate through the file.
    - I used the keys "J" and "L" to locate to the error in the file (the line after the specified comment)
    - Once I was at the point of error, I deleted "1" and replaced it with "2" as the comment told me to do so using regular backslash and the key "2".
    - At this point I'm done with the file, so I pressed <esc> to go back to normal mode in vim. Then I pressed ":wq" to save and quit the file.
+ Now I am back at the terminal, so I test my file again using `sh`, and all tests pass!!
+ I commit my changes using `git command -m` with the message of my choice "fixed", and then I push my changes into my repository using `git push`, which perfectly updates my github repository with the change I made to ListExamples.java!!
