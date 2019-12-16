### iebis_swdev_exam_debugging
# SOLUTION

The first bug was fixed in class by replacing "." with "\\."

## Second bug

Using a breakpoint I realized that the word variable remains null after declaring it an filling it up with strings. This happens because:

**Single quotes('')** are used for literal characters, like: char c = 'myChar'

**Double quotes("")** are used for for literal strings, like: string t = “myTotal”

This is why the String wasn't assimilating the inputs as the strings required.

[Source](https://www.quora.com/What-is-the-difference-between-single-quoted-and-double-quoted-in-Java)

## Third bug
The boundary of the random function was set to 2

The random fuction should be stated in the following manner:
>>java.util.Random.nextInt

>>new Random().nextInt((max-min+1))+min

The max is 2

The min is 0

2-0+1=3

The upper boundary needs to be incremented to 3.

[Source](http://bytepadding.com/java/java-core/java-generate-random-number-in-a-range/)
## Fourth bug
Applying a switch statement has rules, which this code isn't following

  * When a break statement is reached, the switch terminates, and the flow of control jumps to the next line following the switch statement.
  * Not every case needs to contain a break. If no break appears, the flow of control will fall through to subsequent cases until a break is reached.
  
  switch (random.nextInt(3))
        {
            case 0:
                word = new StringBuffer("Y");
            case 1:
                word = new StringBuffer("F");
            case 2:
                word = new StringBuffer("T");
        }

 As there are no breaks in this switch part, the flow keeps going until the function gets to the end. It should be like this:
 
  switch (random.nextInt(3))
        {
            case 0:
                word = new StringBuffer("Y");
                break;
            case 1:
                word = new StringBuffer("F");
                break;
            case 2:
                word = new StringBuffer("T");
                break;
        }
[Source](https://www.tutorialspoint.com/java/switch_statement_in_java.htm)

