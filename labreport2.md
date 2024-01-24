## *Ria Singhania, A17331656*
# ChatServer code
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String blank = "blank";
    String output = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return blank;
        } else {
            if (url.getPath().contains("/add-message")) {
                String[] parameters1 = url.getQuery().split("&");
                String[] parameters2 = parameters1[0].split("=");
                String[] parameters3 = parameters1[1].split("=");
                if (parameters2[0].equals("s") && parameters3[0].equals("user")) {
                    output += String.format("%s: %s\n", parameters3[1] , parameters2[1]);
                    return output;
                }
            }
            return "404 Not Found!";
        }
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
<Pictures of using add message>
    
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-24%20at%203.26.58%20PM.png?raw=true)


