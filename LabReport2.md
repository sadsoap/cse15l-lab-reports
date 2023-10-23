# Lab Report 2 - Servers and SSH Keys

## Part 1

### StringServer.java code:
![Image](scLR2/StringServerCode.png)

no text about the code

### Adding "Hello!": 
![Image](scLR2/StringServerHello.png)

What methods are called? What are the relevant arguments,
and the values of any relevant fields of the class? How 
do the values of any relevant fields of the class change
from this specific request?

* The primary method being called in terminal is `StringServer`,
but there are many methods nested inside that allow for the
results to show. Inside the definition of `StringServer`, there
is a call for `new Handler()` which has most of our working
methods inside it. The primary method in the Handler class
is `handleRequest`, which processes the url input and returns
the display results.
* Relevant arguments/values
For `StringServer`: a single argument, a string array that
contains the desired port number. Has one local variable, integer
`port` which holds the user's input as an integer.
For `Handler`: no arguments, but has two local variables, string
`sCurrent` and integer `iNum` which hold the string to be displayed
and the integer counting the lines added respectively.
For `handleRequest`: a single argument, a URI variable `url` that
contains the current url to the server site. Has three relevant
values, the variables `sCurrent` and `iNum` local to `Handler`,
and a string array `parameters` that holds strings deliminated by
an "=" after the query mark in the url.
* For this specific request, the only values that are affected
differently from any other request are `url` and `sCurrent`, since
they are evaluating a string that does or will contain "Hello!"
specifically.

### Adding "How are you today?":
![Image](scLR2/StringServerHowAreYouToday.png)

same as above
