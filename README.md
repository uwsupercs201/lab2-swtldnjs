# CSCI 201 FALL 2022
Week 3 Lab Starter Code:

None!

Welcome to GitHub and your second CS201 Lab!

### Learning Goals:
- use numeric datatypes
- use `Math` Class to perform complex computations
- use variable names appropriately (if you don't you're gonna have a bad time!)


### Creating an IntelliJ Project [same as last time]

First we need to create an IntelliJ project in a well-named, easy to locate folder.

1) If you're using a Lab Workstation, navigate to the H:\ Drive and create a folder called `cs201`.  If you're using your own device, place a folder called `cs201` wherever you can reliably find it. I recommend `Documents\classes`
2) Open IntelliJ. On Lab Workstations, this can be done by navigating to the Start Menu and finding IntelliJ in the JetBrain folder. If you are using a Windows machine of your own, the process is the same. If you are using a Mac, you'll need to find IntelliJ in the Apps location.
3) IntelliJ will open a dialog box the first time you open it. Select "Create a New Project" and click Next. 
4) You can select the Project SDK, you should choose JDK Version 16.0.2.
5) Ensure both Groovy and Kotlin/JVM are NOT selected.
6) Ensure "Create Project from Template" is NOT selected.
7) Set the Project Name to `Lab2`. Set the Project location to `H:\cs201\Lab2` or `[Location on your device]\cs201\Lab2` and click Finish. It will give you a "Directory does not exist" Dialogue. Click Ok to create directory.

## Lab 2 Part 1

### Creating a .java file

Program are written in .java files and compiled into .class files.
1) Click the arrow next to the Lab1 folder in the Project Viewer Pane. This will expand the project folder.
2) Right click on the `src` folder and navigate to `New`. Click `Java Class`. When prompted for a name, name the class `Lab2_1`.

The Text Editor Pane will now contain a page with the following:

```
public class Lab2{
}
```

Inside of that class is where you will place the `main` method of your program. That program, when compiled, should print the following:

The program should do the following:
- Prompt the user for 6 numbers (decimals are acceptable). The first three entries will correspond to the coordinates of 3-dimensional point $P_1=(x_1,y_1,z_1)$ and the second 3 entries will correspond the the coordinates of a second 3-dimensional point $P_2=(x_2,y_2,z_2)$. 
   * You can prompt for each individual coordinate or all 6 at once, but I think one of these options is better practice.
- The program should could compute the distance between these two points. The formula for distance between $P_1=(x_1,y_1,z_1)$ and $P_2=(x_2,y_2,z_2)$ in 3d is $d=\sqrt{(x_1-x_2)^2+(y_1-y_2)^2+(z_1-z_2)^2}$. 
- The program should print the distance with a brief explanation. Here is an example:

```
Enter the x-coordinate of point 1: 1.2 
Enter the y-coordinate of point 1: 2.6 
Enter the z-coordinate of point 1: -3.4 
Enter the x-coordinate of point 2: 0.9 
Enter the y-coordinate of point 2: 1.1 
Enter the z-coordinate of point 2: 8.4 
The distance between point 1 and point 2 is: 11.898739429031968 
```

Note: you can compute square roots by using the `Math.sqrt().`

### Bonus: Also print the "integer part" of the distance and "fractional part" of the distance:

```
The integer part of the distance between point 1 and 2 is: 11
The fractional part of the distance between point 1 and 2 is: 0.8987394290319681  
```

You can compile and run your program in IntelliJ by selecting `Run > Run` from the header, pressing the green "Play Button" next to the `main` method, or pressing `Shift+F10`.


## Lab 2 Part 2 SUPER CHALLENGE BONUS (This is not required, but is fun if you finish part 1)

1) Right click on the `src` folder and navigate to `New`. Click `Java Class`. When prompted for a name, name the class `Lab2_2`.

Your program should:
- prompt the user for a number of seconds.
- pass the entered number of seconds to a method called `secondsAnalyzer` which performs the following task: convert that number of seconds to the amount of weeks, days, hours, minutes, and leftover seconds that is. It does NOT convert the entire amount to each, but the total quantity. For example 3600 seconds is 1 hour so your program would display:
- the secondsAnalyzer method should return the String generated to the main method where it can be printed. 

Below are some examples:

```
Enter a number of seconds: 3600
3600 seconds is 0 weeks, 0 days, 1 hours, 0 minutes, and 0 seconds
```

OR

```
Enter a number of seconds: 137
137 seconds is 0 weeks, 0 days, 0 hours, 2 minutes, and 17 seconds
```

Note: you should never have more than 59 seconds since that would just give you another minute. 

**Implementation Tips:**

***The `main` method:***

The main method should only do 3 things:

1) prompt the use for a  number of seconds, allow them to respond, and store the value as `enteredSeconds.`
2) pass this value to the `secondsAnalyzer` method which will return a string.
3) print the string that is returned from `secondsAnalyzer.`

***The `secondsAnalyzer` method:***

In the secondsAnalyzer method you'll pass a single integer parameter, call it `x`. 

You can create 5 integer variables `weeks, days, hours, minutes, seconds`

You can process the number of minutes using the division operator. Since the number of seconds will be known as `x` by the method, the number of minutes is the result of 

```minutes = x / 60;```

Since both are integers, this will return an integer value.

To find the leftover number of seconds after accounting for minutes, you can compute 

```seconds = x - (minutes * 60);```

Fun question: can you explain why this works?

Now, you can repeat this process with the number of minutes you have, converting it to `hours`, converting `hours` to `days` and converting `days` to weeks. 

Finally, you'll create a string which represents the data as desired: 

```java
x seconds is [weeks] weeks, [days] days, [hours] hours, [0] minutes, and [1] seconds
```

The `secondsAnalyzer` method should return that string to the `main` method where it can be printed.

Hint: If you're struggling with the math portion of this, just try converting to minutes and left over seconds first. Once that works reliably, shoot for hours. Once that works, work on days, etc. One step at a time making sure everything works as desired. 


### Submitting the project

When you're done, you can upload your files to this Repo and commit the changes. 

1) Click `Add files ` at the top right of the Repo page.

There are two options:

A) Click "Add Files" to create new Java files in the repo manually. Create new files with name `Lab2_1.java` (and `Lab2_2.java` if you got there)You can re-type or copy paste your code into that file.

B) Click "Upload Files" to just upload the .java files you already created. Navigate to the `src` folder on your computer and upload `Lab2_1.java` (and maybe `Lab2_2.java`). 

2) Once you've created the file you want, or uploaded them, navigate to the bottom of the Page and hit "Commit changes". Ensure "Commit directly to the `main` branch." is selected. You'll need to "Commit changes" once for each file you "Create" in GitHub, but can upload multiple files before a single Commit. 


