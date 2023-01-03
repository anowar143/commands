## Python, C, C++, Java, PHP, Javascript

### User Input
##### Python
```
username = input("Enter a user Name")
print("User name is: " + username)

```
##### C
```
#include <stdio.h>
int main() {
    char firstName[20];
    printf("Enter Yor First Name: \n");
    scanf("%s", firstName);
    printf("Hello %s.", firstName);
    return 0;
}
```
##### C++
```
#include <iostream>
#include <string>
using namespace std;
int main() {
    string firstName;
    cout << "Enter your fisrt Name: ";
    cin >> firstName; // for fullname with space    getline(cin, fullName)
    cout << "Hello " << firstName <<".";
    return 0;
}
```
##### Java
```

import java.util.Scanner;
class Main{
    public static void main(String[] args) {

        Scanner myObj = new Scanner(System.in);
        String userName;
        System.out.println("Enter username");
        userName = myObj.nextLine();
        System.out.println("User name is: " + userName);
    }
}
```
##### PHP
```
<?php
$var = readline("Enter a user name: ");
echo "User name is: " .$var;
?>
```
##### Javascript
```
<script>
var name = prompt("Enter a user name");
alert("User name is: " + name);
</script>
```
###### or

```
<!DOCTYPE html>
<html>
<body>

<button onclick="myFunction()">Try it</button>

<p id="demo"></p>

<script>
function myFunction() {
  let person = prompt("Please enter your name", "Harry Potter");
  if (person != null) {
    document.getElementById("demo").innerHTML =
    "Hello " + person + "! How are you today?";
  }
}
</script>

</body>
</html>
```
