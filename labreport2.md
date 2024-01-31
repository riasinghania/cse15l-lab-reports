## *Ria Singhania, A17331656*
# Part 1
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
# Pictures of using `add message`

`\add-message?s=I am Ria&user=Ria`
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-24%20at%203.26.44%20PM.png?raw=true) 
* Specific method used was the `add-message:<string>&user:<string>` 
* The values for the two `<string>` arguments were `I am Ria` and `Ria`
* The string I use to keep track of all the chats, `output`,  increased.
* The different arrays like `parameters1` reset each time I use a command.

`\add-message?s=Hey, I'm Tess&user=Tess`
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-24%20at%203.26.58%20PM.png?raw=true)
* Specific method used was the `add-message:<string>&user:<string>` 
* The arguments for the two `<string>` arguments  were `Hey, I'm Tess` and `Tess`
* The string I use to keep track of all the chats, `output`, increased again.
* The different arrays like `parameters1` reset each time I use a command.

# Part 2
# private key
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-24%20at%204.36.07%20PM.png?raw=true)
# public key 
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-24%20at%204.36.07%20PM.png?raw=true)
# Logging into ssh account without being asked for password
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-24%20at%204.36.07%20PM.png?raw=true)

# Part 3
So far Lab has been very helpful for learning how to navigate terminal and my computer much more efficiently. I have learned how to see what directory I am via the `ls` command. Also this past week of working with servers has been super interesting. Understanding how to get queries from a URL has been valuable. I am now able to create servers that keep the information in them and when you use different commands it will still keep the old stuff. 







