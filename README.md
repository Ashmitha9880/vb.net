
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



**2.   c# program to amicable numbers**
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


**1. PRINT A BINARY TRIANGLE
**
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

**4. CREATE A GRAY CODE**

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


**5.C# PROGRAM TO CALCULATE VOLUME OF 2 BOXES AND FIND THE RESULTANT VOLUME AFTER ADDITION OF TWO BOXES BY IMPLIMENTING OPERATING OPERLOADING
**

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
    
    
    
    
    
 ** 6. C# PROGRAM TO IMPLEMENT OF DELEGATES**
   
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


    
    
    
  **7. C# PROGRAM TO GENERATE REGISTER NUMBER AUTOMATICALLY FOR 100 STUDENTS USING STATIC CONSTRUCTOR**

     
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


**8.. C# PROGRAM TO FIND THE FREQUENCY OF THE WORD "IS" IN A GIVEN SENTENCE

**
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




**9.PROGRAM TO BENCHMARK 2D JAGGED ARRAY ALLOCATION USING SYSTEM**

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




10. PROGRAM TO FIND THE SUM OF VALUE ON DIAGONAL OF A MATRIX


using System;

namespace ex10<br>
{
    class SumOfDiagonals<br>
    {
        static void Main(string[] args)<br>
        {
            int maxRow, maxCol, sum = 0;<br>
            int[,] matrix;<br>
            Console.WriteLine("\n SUM OF DIAGONAL OF A MATRIX.....\n");<br>
            Console.WriteLine("\n enter the number of rows:");<br>
            maxRow = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\n enter the number of coloumns:");<br>
            maxCol = Convert.ToInt32(Console.ReadLine());<br>
            if(maxRow!=maxCol)<br>
            {
                Console.WriteLine("\n the Dimensional entered are not of square matrix");<br>
                Console.WriteLine("\n  Exiting the program");<br>
                return;<br>
            }
            matrix = new int[maxRow, maxCol];<br>
            for(int i=0; i<maxRow; i++)<br>
            {
                for (int j = 0; j< maxCol; j++)<br>
                {
                    Console.Write("\n enter the ({0},{1}) th element of the matrix", (i + 1), (j + 1));<br>
                    matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>

                }
            }
            Console.WriteLine("\n the entered matrix is:");<br>
            for(int i=0;i<maxRow;i++)<br>
            {
                for (int j = 0; j < maxCol; j++)<br>
                {
                    Console.Write(" " + matrix[i, j]);<br>
                    if(i==j)<br>
                    {
                        sum += matrix[i, j];<br>
                    }
                }
                Console.WriteLine();<br>
            }
            Console.WriteLine("\n the sum of Diagonal is " + sum);<br>
             
        }
    }
}

![image](https://user-images.githubusercontent.com/97940767/154634589-86b2e181-8d7f-4ef6-8b1b-7cd50795c6d8.png)
![image](https://user-images.githubusercontent.com/97940767/154634665-0b898312-1783-4273-a87d-80d1f761639b.png)



**11. CREATE A FILE CHECK THE EXISTANCE OF A FILE AND READ THE CONTENT OF THE FILE **


using System;
using System.IO;<br>

namespace ex11<br>
{
    class FileRead<br>
    {
        public static void Main()<br>
        {
            string filename;<br>
            while(true)<br>
            {
                Console.WriteLine("\n ............MENU...................\n");<br>
                Console.WriteLine("\n 1. Create a file");<br>
                Console.WriteLine("\n 2. Existence of the File");<br>
                Console.WriteLine("\n 3. Read the content of the file");<br>
                Console.WriteLine("\n 4. Exit");<br>
                Console.WriteLine("\n enter your choice");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {
                    case 1 :<br>
                        Console.Write("\n Enter the file name to creater");<br>
                        filename = Console.ReadLine();<br>
                        Console.WriteLine("\n Write the content of the file: \n");<br>
                        string r = Console.ReadLine();<br>
                        using(StreamWriter fileStr=File.CreateText(filename))<br>
                        {
                    fileStr.WriteLine(r);<br>

                }
                Console.WriteLine("File is created..");<br>
                break;<br>
                case 2:
                        Console.Write("\n Enter the file name");<br>
                        filename = Console.ReadLine();<br>
                        if(File.Exists(filename))<br>
                        {
                            Console.WriteLine("File exists");<br>
                        }
                        else<br>
                        {
                            Console.WriteLine("File does not exit in the current directort");<br>
                        }
                        break;<br>
                    case 3:
                        Console.Write("Enter the file name to read the content:\n");<br>
                        filename = Console.ReadLine();<br>
                        if (File.Exists(filename))<br>
                        {
                            using(StreamReader sr = File.OpenText(filename))<br>
                            {
                                string s = " ";<br>
                                Console.WriteLine("Here is the content of the file:");<br>
                                while((s=sr.ReadLine())!=null)<br>
                                {
                                    Console.WriteLine(s);<br>
                                }
                                Console.WriteLine(" ");<br>
                            }
                        }
                        else<br>
                        {
                            Console.WriteLine("File does not exists");<br>
                        }
                        break;<br>
                    case 4:<br>
                        Console.WriteLine("\n Existing....");<br>
                        return;<br><br>
                    default :<br>
                        Console.WriteLine("\n invalid choice");<br>
                        break;<br>
                }


            }

        }
    }
}

![image](https://user-images.githubusercontent.com/97940767/154636145-2ee10dc5-73cc-4ce8-8af0-c9f4e3651172.png)
![image](https://user-images.githubusercontent.com/97940767/154636334-472de71d-b5ac-4c5a-9abb-f218e4f30eac.png)
![image](https://user-images.githubusercontent.com/97940767/154636424-4f2cedc5-bec4-436c-a68b-50ec4b9cc9c4.png)


**12. C# PROGRAM TO COMPARE THE TWO FILES**


using System;
using System.IO;<br>
namespace ex12<br>
{
    class FileRead<br>
    {
         public static void Main()<br>
        {
            string file1;<br>
            string file2;<br>
            Console.Write("enter the first file path");<br>
            file1 = Console.ReadLine();<br>
            Console.Write("Enter the second file path");<br>
            file2 = Console.ReadLine();<br>
            if(!File.Exists(file1))<br>
            {
                Console.WriteLine("first file does not exist!");<br>
            }
            else if(!File.Exists(file2))<br>
            {
                Console.WriteLine("second file does not exist!");<br>
            }
            else if(File.ReadAllText(file1)==File.ReadAllText(file2))<br>
            {
                Console.WriteLine("Both the files contain the same content");<br>
            }
            else<br>
            {
                Console.WriteLine("Contents of files are not same");<br>
            }
        }
    }
}

![image](https://user-images.githubusercontent.com/97940767/154637493-20aa1b32-b387-4c13-86bf-c998bdf3b492.png)
![image](https://user-images.githubusercontent.com/97940767/154637546-e390a333-2cfb-430f-89f9-5ef839e7570f.png)
![image](https://user-images.githubusercontent.com/97940767/154637612-6be5f45c-15dd-4c0c-a28f-3165edb8b652.png)
![image](https://user-images.githubusercontent.com/97940767/154637838-20eb6345-511e-4169-86ab-f0f030d3ee36.png)
![image](https://user-images.githubusercontent.com/97940767/154637902-a7528741-ce03-4ae4-86fc-f33c2709cfb1.png)
![image](https://user-images.githubusercontent.com/97940767/154637983-8507a495-0559-4e38-94ef-24958184f8cf.png)

13.INCREAMENT ICOMPARABLE INTERFACE
using System;

namespace ex13
{
    class Fraction : IComparable
    {
        int z, n;
        public Fraction(int z, int n)
        {
            this.z = z;
            this.n = n;
        }
        public static Fraction operator +(Fraction a, Fraction b)
        {
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);
        }
        public static Fraction operator *(Fraction a, Fraction b)
        {
            return new Fraction(a.z * b.z, a.n * b.n);
        }
        public int CompareTo(object obj)
        {
            Fraction f = (Fraction)obj;
            if ((float) z / n < (float)f.z / f.n)
                    return -1;
            else if ((float) z / n > (float)f.z / f.n )
                    return 1;
            else
                return 0;
        }
        public override string ToString()
        {
            return z + "/" + n;
        }
    }
    class ICompInterface
    {
        public static void Main()
        {
            Fraction[] a =
            {

                 new Fraction(5,2),
                 new Fraction(29,6),
                 new Fraction(4,5),
                 new Fraction(10,8),
                 new Fraction(34,7),
            };
            Array.Sort(a);
            Console.WriteLine("Implementing the IComparable Interface in " + " Displaying Fraction:");
            foreach(Fraction f in a)
            {
                Console.WriteLine(f + " ");
            }
            Console.WriteLine();
            Console.ReadLine();
        }
    }

        
    
}
OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155658749-141fdd61-ab31-49c7-8513-344a66d01fb6.png)

14.CREATE PROGRAM TO CREATE THREAD POOLS

using System;
using System.Threading;


namespace ex14
{
    class ThreadPoolProg
    {
       public void ThreadFun1(object obj)
        {
            int loop = 0;
            for( loop=0;loop<=4;loop++)
            {
                Console.WriteLine("Thread1 is executing");
            }
        }
        public void ThreadFun2(object obj)
        {
            int loop = 0;
            for(loop=0;loop<=4;loop++)
            {
                Console.WriteLine("Thread2 is executing");
            }
        }
        public static void Main()
        {
            ThreadPoolProg TP = new ThreadPoolProg();
            for(int i=0;i<2;i++)
            {
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));
            }
            Console.ReadKey();
        }
    }
}

OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155659457-4bb5c9da-ec82-4ef6-aa57-f596d6a0e6de.png)

15.TO DEMOSTRATE ERROR HANDLING USING TRY,CATCH,FINALLY BLOACK
using System;

namespace ex15
{
    class ExceptionHandling
    {
        static void Main(string[] args)
        {
            Age a = new Age();
            try
            {
                a.displayAge();
            }
            catch (AgeIsNegativeException e)
            {
                Console.WriteLine("AgeIsNegativeException {0}", e.Message);
            }
             finally
            {
                Console.WriteLine("Execution of Finally block is done");
            }
        }
    }
}
public class  AgeIsNegativeException : Exception
{
    public AgeIsNegativeException ( string message):base(message)
    {

    }
} 
    public class Age
{
    int age = -5;
    public void displayAge()
    {
        if(age<0)
        {
            throw (new AgeIsNegativeException("Age cannot be negative"));
        }
        else
        {
            Console.WriteLine("Age is :{0}", age);
        }
    }


}

OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155659824-ddd7a9bb-39ab-407d-9f65-991117b4fc57.png)

16. FIBBONOCCI NUMBERS

using System;
public class FibonacciExample
{
    public static void Main(string[] args)
    {
        int n1 = 0, n2 = 1, n3, i, number;
        Console.Write("Enter the number of elements: ");
        number = int.Parse(Console.ReadLine());
        Console.Write(n1 + " " + n2 + " "); //printing 0 and 1    
        for (i = 2; i < number; ++i) //loop starts from 2 because 0 and 1 are already printed    
        {
            n3 = n1 + n2;
            Console.Write(n3 + " ");
            n1 = n2;
            n2 = n3;
        }
    }
}

OUTPUT:

![image](https://user-images.githubusercontent.com/97940767/155660585-c39f8d95-9e35-4393-9a09-4f2cc4619ece.png)

17.PRIME NUMBER
using System;
public class PrimeNumberExample
{
    public static void Main(string[] args)
    {
        int n, i, m = 0, flag = 0;
        Console.Write("Enter the Number to check Prime: ");
        n = int.Parse(Console.ReadLine());
        m = n / 2;
        for (i = 2; i <= m; i++)
        {
            if (n % i == 0)
            {
                Console.Write("Number is not Prime.");
                flag = 1;
                break;
            }
        }
        if (flag == 0)
            Console.Write("Number is Prime.");
    }
}

OUTPUT:

![image](https://user-images.githubusercontent.com/97940767/155662032-c3cd5196-ed11-45cb-9170-c0e4979fe4a6.png)


18. PALINDROME OR NOT

using System;
public class PalindromeExample
{
    public static void Main(string[] args)
    {
        int n, r, sum = 0, temp;
        Console.Write("Enter the Number: ");
        n = int.Parse(Console.ReadLine());
        temp = n;
        while (n > 0)
        {
            r = n % 10;
            sum = (sum * 10) + r;
            n = n / 10;
        }
        if (temp == sum)
            Console.Write("Number is Palindrome.");
        else
            Console.Write("Number is not Palindrome");
    }
}
OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155662884-598030bb-f4df-4270-9f3a-43e66f8302a2.png)


19. To find factorial number

using System;
public class FactorialExample
{
    public static void Main(string[] args)
    {
        int i, fact = 1, number;
        Console.Write("Enter any Number: ");
        number = int.Parse(Console.ReadLine());
        for (i = 1; i <= number; i++)
        {
            fact = fact * i;
        }
        Console.Write("Factorial of " + number + " is: " + fact);
    }
}

output:
![image](https://user-images.githubusercontent.com/97940767/155663864-28d58d00-2d0f-461d-84db-c8364ca49d68.png)

20.To find some of digit

using System;
public class SumExample
{
    public static void Main(string[] args)
    {
        int n, sum = 0, m;
        Console.Write("Enter a number: ");
        n = int.Parse(Console.ReadLine());
        while (n > 0)
        {
            m = n % 10;
            sum = sum + m;
            n = n / 10;
        }
        Console.Write("Sum is= " + sum);
    }
}

OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155664277-6a2e5a75-0656-4dd2-8e41-51add238c831.png)

21. TO REVERSE A NUMBER

using System;
public class ReverseExample
{
    public static void Main(string[] args)
    {
        int n, reverse = 0, rem;
        Console.Write("Enter a number: ");
        n = int.Parse(Console.ReadLine());
        while (n != 0)
        {
            rem = n % 10;
            reverse = reverse * 10 + rem;
            n /= 10;
        }
        Console.Write("Reversed Number: " + reverse);
    }
}

OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155664890-f968f1f6-95e3-4c0a-8ca9-f27118ea63e0.png)

22. PROGRAM TO SWAP A NUMBER

using System;
public class SwapExample
{
    public static void Main(string[] args)
    {
        int a = 5, b = 10;
        Console.WriteLine("Before swap a= " + a + " b= " + b);
        a = a * b; //a=50 (5*10)      
        b = a / b; //b=5 (50/10)      
        a = a / b; //a=10 (50/5)    
        Console.Write("After swap a= " + a + " b= " + b);
    }
}

OUTPUT:



    
    

    

