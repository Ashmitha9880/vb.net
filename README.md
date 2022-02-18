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


3. C# PROGRAMTO ILLIUSTRATE MULTILEVEL INHERITANCE WITH VIRTUAL METHOD

using System;

namespace exam3<br>
{
   
        class PersonalDetails<br>
        {
            string name;<br>
            int age;<br>
            string gender;<br>
            public PersonalDetails(string name, int age, string gender)<br>
            {
                this.name = name;<br>
                this.age = age;<br>
                this.gender = gender;<br>
            }
            public virtual void Display()<br>
            {
                Console.WriteLine("\n-------- PERSONAL DETAILS --------\n");<br>
                Console.WriteLine("Name : " + name);<br>
                Console.WriteLine("Age : " + age);<br>
                Console.WriteLine("Gender : " + gender);<br>
            }
        }
        class CourseDetails : PersonalDetails<br>
        {
            int regNo;<br>
            string course;<br>
            int semester;<br>
            public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)<br>
            {
                this.regNo = regNo;<br>
                this.course = course;<br>
                this.semester = semester;<br>
            }
            public override void Display()<br>
            {
                base.Display();<br>
                Console.WriteLine("\n-------- COURSE DETAILS --------\n");<br>

                Console.WriteLine("Register Number : " + regNo);<br>
                Console.WriteLine("Course : " + course);<br>
                Console.WriteLine("Semester : " + semester);<br>
            }
        }
        class MarksDetails : CourseDetails<br>
        {
            int[] marks = new int[5];<br>
            int total;<br>
            float average;<br>
            string grade;<br>
            int flagFail;<br>
            public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age, gender, regNo, course, semester)<br>
            {
                total = 0;<br>
                for (int i = 0; i < 5; i++)<br>
                {
                    this.marks[i] = marks[i];<br>
                    total += marks[i];<br>
                    if (marks[i] < 35)<br>
                    {
                        flagFail = 1;<br>
                    }
                }
                Calculate();<br>
            }
            private void Calculate()<br>
            {
                average = total / 5;<br>
                if (flagFail == 1 || average < 40)<br>
                    grade = "Fail";<br>
                else if (average >= 70)<br>
                    grade = "Distinction";<br>
                else if (average >= 60)<br>
                    grade = "First Class";<br>
                else if (average >= 50)<br>
                    grade = "Second Class";<br>


                else<br>
                    grade = "Pass Class";<br>
            }
            public override void Display()<br>
            {
                base.Display();
                Console.WriteLine("\n-------- MARKS DETAILS --------\n");<br>
                Console.Write("Marks in 5 subjects: ");<br>
                for (int i = 0; i < 5; i++)<br>
                    Console.Write(marks[i] + " ");<br>
                Console.WriteLine();<br>
                Console.WriteLine("Total : " + total);<br>
                Console.WriteLine("Average : " + average);<br>
                Console.WriteLine("Grade : " + grade);<br>
            }
        }
        class MultiLevel<br>
        {
            public static void Main(string[] args)<br>
            {
                MarksDetails Student1 = new MarksDetails("Abhijith", 22, "Male", 20190001, "MCA", 5, new int[] { 77, 80, 98, 95, 90 });<br>
                Student1.Display();<br>
            }
        }
   }
    
    
![image](https://user-images.githubusercontent.com/97940767/154630114-7a9a1632-5e41-478f-960b-6b0b5e49de55.png)
    
    
    
    
    
  6. C# PROGRAM TO IMPLEMENT OF DELEGATES
   
   using System;

namespace ex6<br>
{<br>
    class Delegates<br>

    {
        delegate string UppercaseDelegates(string input);<br>
        static string UppercaseFirst(string input)<br>
        {
        char[] buffer = input.ToCharArray();<br>
        buffer[0]=char.ToUpper(buffer[0]);<br>
        return new string (buffer);<br>
        }
    static string UppercaseLast(string input)<br>
    {
        char[] buffer = input.ToCharArray();<br>
        buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);<br>
        return new string(buffer);<br>
    }<br>
    static string UppercaseAll(string input)<br>
    {
        return input.ToUpper();<br>
    }
    static void WriteOutput(string input,UppercaseDelegates del)<br>
    {
        Console.WriteLine("Input string:{0}", input);<br>
        Console.WriteLine("Onput string:{0}",del (input));<br>

    }
    static void Main()<br>
        {
        WriteOutput("tom", new UppercaseDelegates(UppercaseFirst));<br>
        WriteOutput("tom", new UppercaseDelegates(UppercaseLast));<br>
        WriteOutput("tom", new UppercaseDelegates(UppercaseAll));<br>
        Console.ReadLine();<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940767/154630924-250ca30c-4583-4106-a4be-28babe6304e0.png)


    
    
    
  7. C# PROGRAM TO GENERATE REGISTER NUMBER AUTOMATICALLY FOR 100 STUDENTS USING STATIC CONSTRUCTOR

     
     using System;

namespace ex7
{
    class RigisterNum<br>
    {
        int regno;<br>
        static int StartNum;<br>
        
        static RigisterNum()<br>
        {
            StartNum = 20210000;<br>
        }
        RigisterNum()<br>
        {
            regno = ++StartNum;<br>

        }
        public static void Main(string[] args)<br>
        {
            for(int i=0;i<100;i++)<br>
            {
                RigisterNum student = new RigisterNum();<br>
                Console.WriteLine("student{0}:{1}", i + 1, student.regno);<br>
            }
           
        }
    }
}


![image](https://user-images.githubusercontent.com/97940767/154632035-c37bf9af-d0ac-48e1-b2fe-5864bee2e40c.png)
![image](https://user-images.githubusercontent.com/97940767/154632110-fc6fa501-5cdf-4456-ac7d-dd1690c0a87d.png)


8.. C# PROGRAM TO FIND THE FREQUENCY OF THE WORD "IS" IN A GIVEN SENTENCE


using System;

namespace ex8<br>
{
    class FrequencyIS<br>
    {
        static void Main(string[] args)<br>
        {
            int count = 0;<br>
            string inputstring;<br>

            Console.WriteLine("\n......Frequency of word 'is'.......");<br>
            Console.Write("\n enter the input string");<br>
            inputstring = Console.ReadLine();<br>
            char[] separator = { ',', '.', '!', ' ', '\n' };<br>
            string teststring = inputstring.ToLower();<br>
            string[] outcomes = teststring.Split(separator);<br>
            foreach (string s in outcomes)<br>
            {
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
            }
                Console.WriteLine("\n number of 'is' in " + inputstring + "is:" + count);<br>
            
        }
    }
}

![image](https://user-images.githubusercontent.com/97940767/154633180-e03f0005-ad5b-4442-b448-fec44f0bc887.png)




9.PROGRAM TO BENCHMARK 2D JAGGED ARRAY ALLOCATION USING SYSTEM

using System;
using System.Diagnostics;<br>
namespace ex9<br>
{
    class BenchmarkAllocation<br>
    {
        const int max = 100000;<br>

        static void Main(string[] args)<br>
        {
            var Arr2D = new int[100, 100];<br>
             var ArrJagged = new int[100][];<br>
            for (int i = 0; i < 100; i++)<br>
            {
                ArrJagged[i] = new int[100];<br>
            }
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i < max; i++)<br>
            {
                for (int k = 0; k < 100; k++)<br>
                {
                    for (int j = 0; j < 100; j++)<br>
                        Arr2D[j, k] = k;<br>


                }
            }

        

            Stopwatch2D.Stop();<br>
            var StopwatchJagged = Stopwatch.StartNew();<br>
            for (int i = 0; i < max; i++)<br>
            {
                for (int j = 0; j < 100; j++)<br>
                {
                    for (int k = 0; k < 100; k++)<br>
                    {
                        ArrJagged[j][k] = k;<br>
                    }
                }
            }
            StopwatchJagged.Stop();<br>
            Console.Write("\n Time taken for allocation in case of 2D array");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "miliseconds");<br>
            Console.WriteLine("\n time taken for aalocation in case of jagged array:");<br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "miliseconds");<br>
        }
    }
}


![image](https://user-images.githubusercontent.com/97940767/154634014-476b1b3f-34e9-45c6-8532-966811cd18a8.png)




























    
    

    

