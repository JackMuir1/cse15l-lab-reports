# Lab Report Week 3

## Part 1: Simple Search Engine

Here is the code from last week's search engine, in which you can add strings to the server and search for the contents of the strings:

```
import java.util.ArrayList;
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    
    ArrayList<String> strings = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "Welcome to String Search Engine! Add a String in the queries of the url";
        } else if (url.getPath().equals("/search")) {
            String[] parameters = url.getQuery().split("=");
            
                String toSearch = parameters[1];
                ArrayList<String> matches = new ArrayList<String>();
                
                for(String s : strings)
                {
                    System.out.println(toSearch);
                    System.out.println(s);
                    for(int i = 0; i < s.length() - toSearch.length() + 1; i++)
                    {
                        System.out.println(s.substring(i, i + toSearch.length()));
                        
                        if(s.substring(i, i + toSearch.length()).equals(toSearch))
                        {
                            matches.add(s);
                        }
                    }
                }
                return matches.toString();
                }
         else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                String added = "";
                for (int i = 1; i < parameters.length; i++) {
                    added += " " + parameters[i];
                    strings.add(parameters[i]);
                }
                return "You have added " + (parameters.length - 1) + " new Strings:" + added;
            }
            return "404 Not Found!";
         }
    }
}
class SearchEngine {
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
When /add is added to the address, the follwoing code block is run:
```
String[] parameters = url.getQuery().split("=");
                String added = "";
                for (int i = 1; i < parameters.length; i++) {
                    added += " " + parameters[i];
                    strings.add(parameters[i]);
                }
                return "You have added " + (parameters.length - 1) + " new Strings:" + added;
```
The program splits the queries between = and puts them into a list, then adds all the items from the list into the strings dataset. It also concatinates them into a string to be outputted by the program.

This means that you can add as many strings you want to the data set in one address line. Below is an example of adding one string and three strings as queries
![adding jack](![Lab2SSJack](https://user-images.githubusercontent.com/70072541/195721331-d8546b09-b49d-437e-a7d1-98a031cdd646.png)
![adding_2names](!![Lab2SS3Names](https://user-images.githubusercontent.com/70072541/195721403-a2ae7048-e419-4a35-927c-078f05ae6137.png)

Now that there are strings in the data set, you can search through them. When /search is added to the address, the following code is run:
```
String[] parameters = url.getQuery().split("=");
            
                String toSearch = parameters[1];
                ArrayList<String> matches = new ArrayList<String>();
                
                for(String s : strings)
                {
                    System.out.println(toSearch);
                    System.out.println(s);
                    for(int i = 0; i < s.length() - toSearch.length() + 1; i++)
                    {
                        System.out.println(s.substring(i, i + toSearch.length()));
                        
                        if(s.substring(i, i + toSearch.length()).equals(toSearch))
                        {
                            matches.add(s);
                        }
                    }
                }
                return matches.toString();
                }
```
The code takes the first querry after the = , then loops through all the strings in the data set and checks to see if the querry is a substring of any of the elements in the dataset. If the querry is a substring, then the string is added to the output of the program.

From the 4 strings added in the previous code, when searching for "jack" you get two results, seen below:
![searching_jack](https://user-images.githubusercontent.com/70072541/195722142-5062b603-850a-4615-94f6-0b240317336e.png)


## Part 2: Testing for Bugs

First Bug- Arrays

Failure Inducing Input: 

Symptom:

Bug:

Connection:

Second Bug- Lists

Failure Inducing Input: 

Symptom:

Bug:

Connection:
