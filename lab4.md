# LAB REPORT 4

## steps

### 4) Log into ieng6
   
`ssh<space>eyildiz@ieng6.ucsd.edu<enter>`

<img width="791" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/dc21bf56-3d09-45f9-b4d5-80f67cd00777">

<img width="753" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/7056f719-7d2a-4b67-8dfc-88f9203012f6">


### 5) Clone your fork of the repository from your Github account (using the SSH URL)
   
`git<space>clone<space>git@github.com:ebyildiz/lab7_newfork.git<enter>`

<img width="898" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/923f5847-d6ba-4701-98d5-cf6104315b89">

<img width="597" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/51ad4fc1-b752-4890-a46a-cb8847afc39a">

### 6) Run the tests, demonstrating that they fail

`cd<space>lab7_newfork<enter>`

<img width="406" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/395c2a43-2927-4618-8918-393505051b24">

`sh<space>test.sh<enter>`

<img width="596" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/17488b72-5e75-4429-be6c-196f8e66ece6">

### 7) Edit the code file to fix the failing test

+ `vim<space>ListExamples.java<enter>`

<img width="421" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/3fcaedd3-5935-4f48-a175-908e5bbfcafd">

<img width="706" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/56b77eb7-4e5d-41a2-94d5-29f620372014">

+ `/cha<enter>JLLLI<backspace>2<esc>:wq<enter>`

   - after pressing `/cha` : 

<img width="389" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/04891b5b-4b24-47fb-a079-9f95b2b20bbf">

   - after pressing `JLLLI`:

<img width="325" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/81f50b47-69d7-4163-b840-89ab4da0d96c">

   - after pressing `<backspace>2`

<img width="409" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/33c95ba9-46bc-495c-890c-317fd745d8ac">

   - `<esc>` and `:wq`

<img width="403" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/b525a20f-6adf-4e3f-8a93-e61f4bbdc536">

   - `<enter>` finally

<img width="506" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/f46ca762-a412-4540-8766-14b0b330aca4">

### 8) Run the tests, demonstrating that they now succeed

- `sh<space>test.sh<enter>`

<img width="351" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/447efb5f-cddc-4c63-9d4a-f9161ed5d424">

### 9) Commit and push the resulting change to your Github account (you can pick any commit message!)

- `git<space>commit<space>-m<space>"fixed"<enter>`

<img width="509" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/9b27eeab-a039-4ddc-8efc-2b8d6967bc77">


- `git<space>push<enter>`

<img width="335" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/29504571-2272-47de-8afd-16b748633248">


## summary

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
