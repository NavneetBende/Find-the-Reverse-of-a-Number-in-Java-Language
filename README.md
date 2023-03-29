# Find-the-Reverse-of-a-Number-in-Java-Language

Given an integer input as number, the objective is Find the Reverse of a Number in Java Language. To do so we usually break down the number into its individual digits and then rearrange them in reverse order. Here are a few methods to solve the above-mentioned problem in Java Language,

Method 1: Using while loop
Method 2: Using for loop
Method 3: Using Recursion I
Method 4: Using Recursion II
Method 5: Taking care of negative numbers in case of method 4
Let’s implement the above-mentioned methods in the upcoming sections.

Method 1: Using while loop
In this method, we’ll use a while loop to break down the number input and rearrange the number in reverse order. We’ll use the modulo operator to extract the digits from the number and the divide operator to shorten the number.

Let’s implement the above-mentioned logic in Java Language.

Reverse a given number in Java
Java Code (Method 1)
Run
public class Main
{
    public static void main (String[]args)
    {

        //variables initialization
        int num = 1234, reverse = 0, rem;


        //loop to find reverse number
        while (num != 0)
        {
            rem = num % 10;
            reverse = reverse * 10 + rem;
            num /= 10;
        };

        //output
        System.out.println ("Reversed Number: " + reverse);
    }
}
Output
Reversed Number: 4321
Method 2: Using For loop
In this method, the approach followed is the same as the previous method but we will use a for loop instead of a while loop.

Initialization: Left Blank
Condition: num != 0 (Checking if number is reduced to zero or not)
Increment: num = num/10, we are reducing the digits in num here
Run
class Main
{
    public static void main (String[]args)
    {

        //variables initialization
        int num = 1234, reverse = 0, rem;


        //loop to find reverse number
        for( ;num != 0; num = num/10)
        {
            rem = num % 10;
            reverse = reverse * 10 + rem;
        };

        //output
        System.out.println ("Reversed Number: " + reverse);
    }
}
Output
Reversed Number: 4321
Related Pages
Program to print Prime Number in range

Program to find Sum of digits of number

Program to check palindrome or not

Program to check armstrong number

Armstrong number in a given range

Method 3: Using Recursion I
In this method we’ll use recursion to break down the input integer number and reassemble them in reverse order. We’ll use the modulo and divide operators to break down the number and rearrange them. 

Let’s implement the logic in Java Language.

Java Code
Run
public class Main
 {
   public static void main (String[]args)
   {

     //variables initialization
     int num = 1234, rev = 0;

     //output
       System.out.println ("Reversed Number: " + getReverse(num, rev));
   }

   static int getReverse (int num, int rev)
   {
     if (num == 0)
       return rev;

     int rem = num % 10;
     rev = rev * 10 + rem;

     return getReverse (num / 10, rev);
   }
 }
Output
Reversed Number: 4321
Method 4: Using Recursion II
This method is similar to that of the above-mentioned method, but instead of using two arguments, we’ll use only one in this method. We’ll directly print the last extracted digit with each recursive call, forming the whole number in reverse order.

Let’s implement the above mentioned logic in Java Language.

Java Code
Run
public class Main
{
  public static void main (String[]args)
  {

    //variables initialization
    int num = 1234;

      getReverse (num);
  }

  static void getReverse (int num)
  {
    if (num == 0)
      return;

    int rem = num % 10;
    System.out.print (rem);

    getReverse (num / 10);

  }
}
Output
Reversed Number: 4321
Taking care of negative Numbers
The above program will give wrong input if the number is negative, example for -1234 the output will be  -4-3-2-1.

We can take care of this in the following way –

Check if the number is positive
Do nothing
If the number is negative
Print ‘-‘ additionally and then
Multiply num with -1 and then send to the function
Run
class Main
{
    public static void main (String[]args)
    {

        //variables initialization
        int num = -1234;
        boolean isNegative = num < 0 ? true: false;

        if (isNegative) {
            System.out.print("-");
            num = num * -1;
        }

        getReverse(num);
    }

    static void getReverse(int num)
    {
        if (num == 0)
            return;

        int rem = num % 10;
        System.out.print(rem);

        getReverse(num / 10);

    }
}
Prime Course Trailer

Related Banners
Get PrepInsta Prime & get Access to all 200+ courses offered by PrepInsta in One Subscription

Get Prime
Output
Reversed Number: -4321
