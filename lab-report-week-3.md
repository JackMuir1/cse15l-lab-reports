# Lab Report Week 3

## Part 1: Simple Search Engine

Here is the code from last week's search engine:

'''
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


'''

add method

one query

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
