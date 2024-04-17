# Part One
import java.io.IOException;
import java.net.URI;
import java.util.Arrays;

```
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

<img width="200" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/fe6ce8c9-b712-457d-b697-eef13a6883a8">
<img width="300" alt="image" src="https://github.com/ebyildiz/cse15l-lab-reports/assets/131305803/868aba84-a2c4-489d-a0e1-59f37d1c3c57">
