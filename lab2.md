## Part One

```
import java.io.IOException;
import java.net.URI;
import java.util.Arrays;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String history ="";`

    public String handleRequest(URI url) {
        String path = url.getPath();
        if (url.getPath().equals("/history")) {
            return String.format("HISTORY\n%s", history);
        } else if (path.contains("/add")) {
            String[] parameters = url.getQuery().split("=");
            System.out.println(Arrays.toString(parameters));
            String message = parameters[1].split("&")[0];
            String user = parameters[2];
            history += user + ": " + message + "\n";
            return history;
        } 
            return "You are missing something";
        }
    } 
    class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
} 
```

### First Picture:
<img width="200" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/fe6ce8c9-b712-457d-b697-eef13a6883a8"> 

+ Which methods in your code are called?
    - `handleRequest` in the `Handler` class and the `main` method in my `Chat Server` class
+ What are the relevant arguments to those methods, and the values of any relevant fields of the class?
    - the argument for user at first is `annoying` and they say 'HI' three times. So the argument for the message was 'HI' and I used the same path 3 times to make the annoying user realistic. Then the argument changes for user to 'mean' and the message to 'CHILL' because it's a mean user.
+ How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
    - the history changes! the history keeps all the messages that has been sent in the server. So it gets updated every time someone uses the server to add a message

### Second Picture:
<img width="300" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/868aba84-a2c4-489d-a0e1-59f37d1c3c57">

+ Which methods in your code are called?
    - `handleRequest` in the `Handler` class and the `main` method in my `Chat Server` class
+ What are the relevant arguments to those methods, and the values of any relevant fields of the class?
    - the argument for user at first is `eyildiz` (me) and I say 'hello, this is my chat server' which is the argument for the message. Then the argument changes for user to 'tutors' and the message to 'good job!' because I did a good job and  the tutors (you) like my server.
+ How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
    - again, the history changes for the same reason. It gets updated with the new messages in the server.
    
## Part Two
+ On the command line of your computer, run `ls` with the absolute path to the private key for your SSH key for logging into ieng6.
      <img width="279" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/36963318-5a73-4bfb-a6a5-ecc1b46d9714">

+ On the command line of the ieng6 machine, run `ls` with the absolute path to the public key for your SSH key for logging into ieng6 (this is the one you copied to your account on ieng6 using ssh-copy-id, so it should be a path on ieng6's file system).
      <img width="611" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/564a3ec2-8baf-4aae-8d16-2a61602527b3">

+ A terminal interaction where you log into your ieng6 account without being asked for a password.
      <img width="546" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/5beb7d1e-71af-4cbd-8a62-832f39361c1c">

## Part 3
Before labs 2 and 3, I didn't know how to create a Server I also did not know how to connect to a remote server. I did the first part of assignment using the remote ieng6 server on vscode and I thought it was really cool to work on a different environment!
