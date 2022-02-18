c# program to print a statement hello
using System;

namespace ex1<br>
{<br>
    class Program<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Console.WriteLine("Hello World!");<br>
        }<br>
    }<br>
}<br>



3.   c# program to amicable numbers
using System;

namespace ex2<br>
{
    class AmicableNumber<br>
    {
        static void Main(string[] args)<br>
        {
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n....AMICABLE NUMBERS...\n");<br>
            Console.Write("\n Enter the first number");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\n Enter the second number");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for(int i=1;i<num1;i++)<br>
            {
                if(num1%i==0)<br>
                {
                    sum1 += i;<br>
                }
            }
            for(int i=1;i<num2;i++)<br>
            {
                if(num2%i==0)<br>
                {
                    sum2 += i;<br>
                }
            }
            if(sum1==num2&&sum2==num1)<br>
            {
                Console.WriteLine("\n the number {0} and {1} are amicable", num1, num2);<br>
            }
            else<br>
            {
                Console.WriteLine("\n the number{0} and {1} are not amicable", num1, num2);<br>
            }
        }

    }
}
![image](https://user-images.githubusercontent.com/97940767/154622485-f1a8265b-c1d0-4b3e-abe3-ff0a9a422ec3.png)


2. PRINT A BINARY TRIANGLE

using System;

namespace example1<br>
{
    class BinaryTriangle<br>
    {
        static void Main(string[] args)<br>
        {
        int number, digit = 1;<br>
         Console.WriteLine("Enter the number of lines");<br>
        number = Convert.ToInt32(Console.ReadLine());<br>
        for (int i = 1; i <= number; i++)<br>
        {
            for (int space = number - i; space > 0; space--)<br>
            {
                Console.Write("");<br>

            }
            for (int j = 0; j < i; j++)<br>
            {
                Console.Write(digit + "");<br>
                digit = (digit == 1) ? 0 : 1;<br>
            }
            Console.Write("\n");<br>
        }

        }
    }
}

![image](https://user-images.githubusercontent.com/97940767/154623042-af715743-a4fa-4463-9c3a-a9bc680697dc.png)


