---
toc: true
layout: post
description: Data Structures Tri 3
categories: [markdown]
title: Data Types
---

## int
```
int[] intArray = new int[]{1, 2, 3, 4, 5};
int randomInt = intArray[(int) (Math.random() * intArray.length)];
```

## Wrapper Class Integer
```
Integer[] integerArray = new Integer[]{1, 2, 3, 4, 5};
Integer randomInteger = integerArray[(int) (Math.random() * integerArray.length)];
```

<br>

## double
```
double[] doubleArray = new double[]{4.76, 9.87, 31.1, 16.8, 132.0};
double randomDouble = doubleArray[(int) (Math.random() * doubleArray.length)];
```
## Wrapper Class Double
```
Double[] doubleArray = new Double[]{1.2, 2.4, 3.6, 4.8, 5.0};
Double randomDouble = doubleArray[(int) (Math.random() * doubleArray.length)];
```

<br>

## boolean
```
boolean[] booleanArray = new boolean[]{true, false, true, false, true};
boolean randomBoolean = booleanArray[(int) (Math.random() * booleanArray.length)];
```

## Wrapper Class Boolean
```
Boolean[] booleanArray = new Boolean[]{true, false, true, false, true};
Boolean randomBoolean = booleanArray[(int) (Math.random() * booleanArray.length)];
```

<br>

## char
```
String charString = "hello";
char[] charArray = charString.toCharArray();
String randomCharString = charString.substring((int) (Math.random() * charString.length()), (int) (Math.random() * charString.length() + 1));
char randomChar = randomCharString.charAt(0);
```

## Wrapper Class Character
```
String charString = "hello";
Character[] charArray = ArrayUtils.toObject(charString.toCharArray());
String randomCharString = charString.substring((int) (Math.random() * charString.length()), (int) (Math.random() * charString.length() + 1));
Character randomChar = randomCharString.charAt(0);
```
# Exploring Teacher Code
[Menu.java](https://github.com/nighthawkcoders/spring_portfolio/blob/master/src/main/java/com/nighthawk/hacks/methodsDataTypes/Menu.java)
```
class Driver {
    /**
     *  Menu Control Example
     */
    public static void main(String[] args) {
        // Row initialize
        MenuRow[] rows = new MenuRow[]{
            // lambda style, () -> to point to Class.Method
            new MenuRow("Exit", () -> main(null)),
            new MenuRow("Do Nothing", () -> DoNothingByValue.main(null)),
            new MenuRow("Swap if Hi-Low", () -> IntByReference.main(null)),
            new MenuRow("Matrix Reverse", () -> Matrix.main(null)),
            new MenuRow("Diverse Array", () -> Matrix.main(null)),
            new MenuRow("Random Squirrels", () -> Number.main(null))
        };

        // Menu construction
        Menu menu = new Menu(rows);

        // Run menu forever, exit condition contained in loop
        while (true) {
            System.out.println("Hacks Menu:");
            // print rows
            menu.print();

            // Scan for input
            try {
                Scanner scan = new Scanner(System.in);
                int selection = scan.nextInt();

                // menu action
                try {
                    MenuRow row = menu.get(selection);
                    // stop menu
                    if (row.getTitle().equals("Exit")) {
                        if (scan != null) 
                            scan.close();  // scanner resource requires release
                        return;
                    }
                    // run option
                    row.run();
                } catch (Exception e) {
                    System.out.printf("Invalid selection %d\n", selection);
                }

            } catch (Exception e) {
                System.out.println("Not a number");
            }
        }
    }
}
```
The code above uses try-catch blocks to handle exceptions and Runnable to control program execution.

The "DiverseArrays" and "Matrix" classes demonstrate the application of control structures and data types in programming. These classes use arrays, loops, and conditionals to perform various tasks, such as finding the sum and average of elements in an array or matrix.

The "DoNothingByValue" and "IntByReference" classes demonstrate the concepts of pass-by-value and pass-by-reference, respectively. These are important concepts in Java, and understanding them is crucial for writing efficient and effective code.

## Methods
Methods are reusable code blocks that perform a specific task. They help in reducing code duplication, improving code readability, and making the code modular. In Java, a method is defined using the keyword 'void' (if it doesn't return anything) or the data type it returns, followed by the method name, and the parameters it takes (if any).

## Control Structures
Control structures are programming constructs that determine the order in which statements are executed in a program. They control the flow of the program, based on certain conditions or criteria. Java has several types of control structures, including if-else, switch, while, do-while, and for loops.

## Math.random
```
function getRandomInt(max) {
  return Math.floor(Math.random() * max);
}

console.log(getRandomInt(3));
// Expected output: 0, 1 or 2

console.log(getRandomInt(1));
// Expected output: 0

console.log(Math.random());
// Expected output: a number from 0 to <1
```

## AP FRQ 2019
Part a
```
public ArrayList<String> getDelimitersList(String[] tokens) 
{     
  ArrayList<String> d = new ArrayList<String>();    
  for (String str : tokens)    
  {       
    if (str.equals(openDel) || str.equals(closeDel))       
    {          d.add(str);       
    }    
}    
return d; 
} 
```

The above code is a Java method that takes an array of strings called "tokens" as input and returns an ArrayList of strings containing only the strings that are equal to either "openDel" or "closeDel".

The method first initializes an empty ArrayList of strings called "d". It then iterates through each string "str" in the "tokens" array using a for-each loop. For each "str" string, it checks whether it is equal to "openDel" or "closeDel" using the equals() method. If "str" is equal to either of these strings, it adds it to the "d" ArrayList using the add() method.

Finally, after iterating through all the strings in the "tokens" array, the method returns the "d" ArrayList containing only the strings that are equal to either "openDel" or "closeDel".

Note that the values of "openDel" and "closeDel" are not defined in the code snippet provided, so their values are unknown.

Part b
```
public boolean isBalanced(ArrayList < String > delimiters) {
  int openCount = 0;
  int closeCount = 0;
  for (String str: delimiters) {
    if (str.equals(openDel)) {
      openCount++;
    } else {
      closeCount++;
    }
    if (closeCount > openCount) {
      return false;
    }
  }
  if (openCount == closeCount) {
    return true;
  } else {
    return false;
  }
}
```

The code above is a Java method that takes an ArrayList of strings called "delimiters" as input and checks whether the input contains balanced delimiters.

The method first initializes two integer variables, "openCount" and "closeCount", to 0. It then iterates through each string "str" in the "delimiters" ArrayList using a for-each loop. For each "str" string, it checks whether it is equal to "openDel" using the equals() method. If "str" is equal to "openDel", it increments the "openCount" variable. Otherwise, it increments the "closeCount" variable.

At each iteration, the method checks whether the number of closing delimiters is greater than the number of opening delimiters. If this is the case, it means that the input is unbalanced, and the method immediately returns false.

After iterating through all the strings in the "delimiters" ArrayList, the method checks whether the "openCount" variable is equal to the "closeCount" variable. If they are equal, it means that the input contains balanced delimiters, and the method returns true. Otherwise, it means that the input is unbalanced, and the method returns false.

Note that the value of "openDel" is not defined in the code snippet provided, so its value is unknown. Additionally, this implementation assumes that all other strings in the "delimiters" ArrayList are closing delimiters, which may not always be the case.
