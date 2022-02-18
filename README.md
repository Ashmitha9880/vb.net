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



2.   c# program to amicable numbers
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


1. PRINT A BINARY TRIANGLE

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

4. CREATE A GRAY CODE

using System;

namespace ex4<br>
{
    class Graycode<br>
    {
        static int getGray(int n)<br>
        {
            return n ^ (n >> 1);<br>
        }
        static void Main(string[] args)<br>
        {
            int InputNum, GrayNum;<br>
            Console.WriteLine(" ENTER THE DECIMAL NUMBER");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\n Binary equivalent of {0}:{1}", InputNum, Convert.ToString(InputNum, 2));<br>
            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\n Graycode equivalent of {0}:{1}", InputNum, Convert.ToString(GrayNum, 2));<br>
        }
    }
}

![image](https://user-images.githubusercontent.com/97940767/154624040-0c7e13ef-9c19-45d3-b4e2-1a0ec4509a23.png)


5.C# PROGRAM TO CALCULATE VOLUME OF 2 BOXES AND FIND THE RESULTANT VOLUME AFTER ADDITION OF TWO BOXES BY IMPLIMENTING OPERATING OPERLOADING


  using System;

namespace ex5<br>
{
    class Box<br>
    {
        float width;<br>
        float height;<br>
        float length;<br>
        public float volume<br>
        {
            get { return width * height * length; }<br>
        }
        public Box(float width, float height, float length)<br>
        {
            this.width = width;<br>
            this.height = height;<br>
            this.length = height;<br>
        }
        public static float operator+(Box box1, Box box2)<br>
        {
            return box1.volume + box2.volume;<br>
        }
        public override string ToString()<br>
        {
            return "box with width" + width + ",height" + height + "and length" + length;<br>
        }
    }
    class OperatingOverloading<br>
    {
    
       public static void Main()<br>
        {
            Box box1 = new Box(10, 20, 30);<br>
            Box box2 = new Box(25, 32, 15); <br>
            Console.WriteLine("volume of {0}is:{1}",box1,box1.volume);<br>
            Console.WriteLine("volume of {0}is:{1}",box2,box2.volume);<br>
            Console.WriteLine("volume after adding boxes:{0}", box1 + box2);<br>
        }<br>
    }<br>
}  <br>

![image](https://user-images.githubusercontent.com/97940767/154625531-6c4ec6db-eff8-48f2-b9be-0e17a431e302.png)

