## *Ria Singhania, A17331656*
# **cd**
<br>

`no argument`

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-10%20at%203.33.31%20PM.png?raw=true)

The working directory when the command was run was `lecture1`, which contained its own directory within it. 
I got the output of sending me home because when there is no argument the `cd` command just sends you out of all directories. So the command basically cleared the directories within the command line, sends you `home`. In this case the command took us out of `lecture1`. 
No error. 

<br>

`to a directory`

<br>

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-10%20at%203.27.07%20PM.png?raw=true)

The working directory when the command was run was no directory, or `home`. The command `cd lecture1` sent me to the `lecture1` directory. This contained another directory and some files. I got that output because `cd` sends the user to whatever directory is provided as an argument. In this case the command took us to `lecture1`. No error.

<br>

`to a file`

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-10%20at%203.39.44%20PM.png?raw=true)

The working directory when the command was run was `lecture1`, which contained its own directory within it. I got that output because when there is no argument the `cd` command just sends you out of all directories. So the command basically cleared the directories within the command line, sends you `home`. In this case the command took us out of `lecture1`. Error.

# **ls**
<br>

`no argument`

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%2011.06.20%20AM.png?raw=true)

The working directory when the command was run was `lecture1`, which contained a directory and some files. 
I got the output of all of the contents within `lecture1`. So the command basically lists everything within a directory. In this case the command listed everything within `lecture1`. 
No error. 

<br>

`to a directory`

<br>

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%2011.06.35%20AM.png?raw=true)

The working directory when the command was run was `lecture1`, which contained a directory and some files. 
I got the output of all of the contents within `messages` because I provided `messages`, a directory, as an argument after `ls`. So the command basically lists everything within a given directory. In this case the command listed everything within `messages`. 
No error. 

<br>

`to a file`

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%2011.07.44%20AM.png?raw=true)

The working directory when the command was run was `messages`, which contained some files. By using ls `es-mx.txt`, the output was the name of the file.
So the command basically outputs the name of the file provided. In this case it was `es-mx.txt`.
No error. 

# **cat**
<br>

`no argument`

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%2011.34.13%20AM.png?raw=true)
![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%2011.34.16%20AM.png?raw=true)

The working directory when the command was run was `lecture1`, which contained a directory and some files. 
I got the output of a curser, meaning `cat` was ready to take whatever I inputted. I typed out `hello guys` and hit enter, making it repeat my inputted text. So the command without an argument waits for the user to type out something and repeats it all when enter is pressed.
No error. 

<br>

`to a directory`

<br>

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%2011.29.51%20AM.png?raw=true)

The working directory when the command was run was `lecture1`, which contained a directory and some files. 
I got the output that messages is a drectory when I used `messages` as the argument. So the command cannot list anything because a directory is not the same as a file and can contain multiple unique things.
Error. 

<br>

`to a file`

![Image](https://github.com/riasinghania/cse15l-lab-reports/blob/main/Screen%20Shot%202024-01-11%20at%2011.29.40%20AM.png?raw=true)

The working directory when the command was run was `messages`, which contained some files. By using ls `es-mx.txt`, the output was the contents within `es-mx.txt`.
So the command outputs the contents within a file when a file is provided as an argument. In this case it `Hola Mundo!`
No error.
