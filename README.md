
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

**13.INCREAMENT ICOMPARABLE INTERFACE**
using System;

namespace ex13
{
    class Fraction : IComparable<br>
    {<br>
        int z, n;<br>
        public Fraction(int z, int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator *(Fraction a, Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(object obj)<br>
        {<br>
            Fraction f = (Fraction)obj;<br>
            if ((float) z / n < (float)f.z / f.n)<br>
                    return -1;<br>
            else if ((float) z / n > (float)f.z / f.n )<br>
                    return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br>
    {<br>
        public static void Main()<br>
        {<br>
            Fraction[] a =<br>
            {<br>

                 new Fraction(5,2),<br>
                 new Fraction(29,6),<br>
                 new Fraction(4,5),<br>
                 new Fraction(10,8),<br>
                 new Fraction(34,7),<br>
            };<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the IComparable Interface in " + " Displaying Fraction:");<br>
            foreach(Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
        }<br>
    }<br>

        
    
}<br>
OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155658749-141fdd61-ab31-49c7-8513-344a66d01fb6.png)

14.CREATE PROGRAM TO CREATE THREAD POOLS

using System;<br>
using System.Threading;<br>


namespace ex14<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
       public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for( loop=0;loop<=4;loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>
            }<br>
        }<br>
        public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for(loop=0;loop<=4;loop++)<br>
            {<br>
                Console.WriteLine("Thread2 is executing");<br>
            }<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for(int i=0;i<2;i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br>

OUTPUT:
![image](https://user-images.githubusercontent.com/97940767/155659457-4bb5c9da-ec82-4ef6-aa57-f596d6a0e6de.png)

15.TO DEMOSTRATE ERROR HANDLING USING TRY,CATCH,FINALLY BLOACK
using System;

namespace ex15<br>
{<br>
    class ExceptionHandling<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            Age a = new Age();<br>
            try<br>
            {<br>
                a.displayAge();<br>
            }<br>
            catch (AgeIsNegativeException e)<br>
            {<br>
                Console.WriteLine("AgeIsNegativeException {0}", e.Message);<br>
            }<br>
             finally<br>
            {<br>
                Console.WriteLine("Execution of Finally block is done");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class  AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException ( string message):base(message)<br>
    {<br>

    }<br>
} <br>
    public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if(age<0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is :{0}", age);<br>
        }<br>
    }<br>


}<br>

OUTPUT:



![image](https://user-images.githubusercontent.com/97940767/155659824-ddd7a9bb-39ab-407d-9f65-991117b4fc57.png)

**16. FIBBONOCCI NUMBERS**

using System;<br>
public class FibonacciExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n1 = 0, n2 = 1, n3, i, number;<br>
        Console.Write("Enter the number of elements: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        Console.Write(n1 + " " + n2 + " "); //printing 0 and 1  <br>  
        for (i = 2; i < number; ++i) //loop starts from 2 because 0 and 1 are already printed    <br>
        {<br>
            n3 = n1 + n2;<br>
            Console.Write(n3 + " ");<br>
            n1 = n2;<br>
            n2 = n3;<br>
        }<br><br>
    }<br>
}<br>

OUTPUT:



![image](https://user-images.githubusercontent.com/97940767/155660585-c39f8d95-9e35-4393-9a09-4f2cc4619ece.png)

**17.PRIME NUMBER**
using System;<br>
public class PrimeNumberExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i, m = 0, flag = 0;<br>
        Console.Write("Enter the Number to check Prime: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        m = n / 2;<br>
        for (i = 2; i <= m; i++)<br>
        {<br>
            if (n % i == 0)<br>
            {<br>
                Console.Write("Number is not Prime.");<br>
                flag = 1;<br>
                break;<br>
            }<br>
        }<br>
        if (flag == 0)<br>
            Console.Write("Number is Prime.");<br>
    }<br>
}<br>

OUTPUT:


![image](https://user-images.githubusercontent.com/97940767/155662032-c3cd5196-ed11-45cb-9170-c0e4979fe4a6.png)



**18. PALINDROME OR NOT**
using System;<br>
public class PalindromeExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = (sum * 10) + r;<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Number is Palindrome.");<br>
        else<br>
            Console.Write("Number is not Palindrome");<br>
    }<br>
}<br>
OUTPUT:

![image](https://user-images.githubusercontent.com/97940767/155662884-598030bb-f4df-4270-9f3a-43e66f8302a2.png)



**19. To find factorial number**

using System;<br>
public class FactorialExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int i, fact = 1, number;<br>
        Console.Write("Enter any Number: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= number; i++)<br>
        {<br>
            fact = fact * i;<br>
        }<br>
        Console.Write("Factorial of " + number + " is: " + fact);<br>
    }<br>
}<br>

output:


![image](https://user-images.githubusercontent.com/97940767/155663864-28d58d00-2d0f-461d-84db-c8364ca49d68.png)



**20.To find some of digit**

using System;<br>
public class SumExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, sum = 0, m;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n > 0)<br>
        {<br>
            m = n % 10;<br>
            sum = sum + m;<br>
            n = n / 10;<br>
        }<br>
        Console.Write("Sum is= " + sum);<br>
    }<br>
}<br>

OUTPUT:



![image](https://user-images.githubusercontent.com/97940767/155664277-6a2e5a75-0656-4dd2-8e41-51add238c831.png)

**21. TO REVERSE A NUMBER**

using System;<br>
public class ReverseExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, reverse = 0, rem;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n != 0)<br>
        {<br>
            rem = n % 10;<br><br>
            reverse = reverse * 10 + rem;<br>
            n /= 10;<br>
        }<br>
        Console.Write("Reversed Number: " + reverse);<br>
    }<br>
}<br>

OUTPUT:


![image](https://user-images.githubusercontent.com/97940767/155664890-f968f1f6-95e3-4c0a-8ca9-f27118ea63e0.png)



**22. PROGRAM TO SWAP A NUMBER**

using System;<br>
public class SwapExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int a = 5, b = 10;<br>
        Console.WriteLine("Before swap a= " + a + " b= " + b);<br>
        a = a * b; //a=50 (5*10)   <br>   
        b = a / b; //b=5 (50/10)  <br>    
        a = a / b; //a=10 (50/5)   <br> 
        Console.Write("After swap a= " + a + " b= " + b);<br>
    }<br>
}<br>

OUTPUT:


![image](https://user-images.githubusercontent.com/97940767/155665793-d64307aa-dbd3-4f1d-a855-525576035294.png)

 
 **EXAMPLE:**
**23.TO PRINT NUMBER TRIANGLE
**

using System;

namespace ex26
{
    public class Printexample<br>
    {<br>
         public static void Main(string[] args)<br>
        {<br>
            int i, j, k, l, n;<br>

            Console.WriteLine("Enter the range=");<br>
            n = int.Parse(Console.ReadLine());<br>
            for(i=1;i<=n;i++)<br>
            {<br>
                for(j=1;j<=n-i;j++)<br>
                {<br>
                    Console.Write(" ");<br>
                }<br><br>
                for(k=1;k<=i;k++)<br>
                {<br>
                    Console.Write(k);<br>

                }<br><br>
                for(l=i-1;l>=1;l--)<br>
                {<br>
                    Console.Write(l);<br>

                }<br>
                  Console.Write("\n");<br>
            }<br>
        }<br>
    }<br>
}<br>

**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940767/156508900-d1b57b27-59b1-435e-a6f0-235aff780857.png)


**24. TO CONVERT DECIMAL TO BINARY**

using System;<br>
public class ConversionExample<br>
{<br>
    public static void Main(string[] args)<br>
    {
        int n, i;<br>
        int[] a = new int[10];<br>
        Console.Write("Enter the number to convert: ");<br><br>
        n = int.Parse(Console.ReadLine());<br>
        for (i = 0; n > 0; i++)<br>
        {<br>
            a[i] = n % 2;<br>
            n = n / 2;<br>
        }<br>
        Console.Write("Binary of the given number= ");<br>
        for (i = i - 1; i >= 0; i--)<br>
        {<br>
            Console.Write(a[i]);<br>
        }<br>
    }<br>
}<br>



**OUTPUT:**


![image](https://user-images.githubusercontent.com/97940767/156509333-9e210afc-43af-45fc-bd9d-8f13d8001f11.png)

**25. NUMBER IN CHARCTER**


using System;<br>
public class ConversionExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, sum = 0, r;<br>
        Console.Write("Enter the Number= ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = sum * 10 + r;<br>
            n = n / 10;<br>
        }<br>
        n = sum;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            switch (r)<br>
            {<br>
                case 1:<br>
                    Console.Write("one ");<br><br>
                    break;<br>
                case 2:<br>
                    Console.Write("two ");<br>
                    break;<br>
                case 3:<br>
                    Console.Write("three ");<br>
                    break;<br>
                case 4:<br>
                    Console.Write("four ");<br>
                    break;<br>
                case 5:<br>
                    Console.Write("five ");<br>
                    break;<br>
                case 6:<br>
                    Console.Write("six ");<br>
                    break;<br>
                case 7:<br>
                    Console.Write("seven ");<br>
                    break;<br>
                case 8:<br>
                    Console.Write("eight ");<br>
                    break;<br>
                case 9:<br>
                    Console.Write("nine ");<br><br>
                    break;<br>
                case 0:<br>
                    Console.Write("zero ");<br>
                    break;<br>
                default:<br>
                    Console.Write("tttt ");<br>
                    break;<br>
            }//end of switch  <br>    
            n = n / 10;<br>
        }//end of while loop     <br>  
    }<br>
}
<br>


**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940767/156509607-d4ebabd5-a948-4e24-8a36-dc2e98eb7c89.png)

**26.ALPHABET TRIANGLE**

using System;<br>
public class PrintExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        char ch = 'A';<br>
        int i, j, k, m;<br>
        for (i = 1; i <= 5; i++)<br>
        {<br>
            for (j = 5; j >= i; j--)<br>
                Console.Write(" ");<br>
            for (k = 1; k <= i; k++)<br>
                Console.Write(ch++);<br>
            ch--;<br>
            for (m = 1; m < i; m++)<br>
                Console.Write(--ch);<br>
            Console.Write("\n");<br>
            ch = 'A';<br>
        }<br>
    }<br>
}<br>


**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940767/156509929-d34a98cd-9e72-4447-8a5d-7ae16ec87d6b.png)


**27. FIBONOCCI TRIANGLE**

using System;<br>

namespace example;<br>
{
     public class Printexample;<br>;<br>
    {<br>
       public static void Main(string[] args)<br>
        {;<br>
            int a = 0,b=1,i,c,n,j ;;<br>
            Console.Write("Enter the limits");<br>
            n = int.Parse(Console.ReadLine());<br>;<br>
            for(i=1;i<=n;i++)<br>
            {<br>
                a = 0;<br>
                b = 1;<br>
                Console.Write(b + "\t");<br>
                for(j=1;j<i;j++)<br>
                {<br>
                    c = a + b;;<br>
                    Console.Write(c + "\t");<br>
                    a = b;<br>
                    b = c;<br>
                }<br>
                Console.Write("\n");<br>
            }<br>
           
        }<br>
    }<br>
}<br>

**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940767/156514845-89f6c83f-d3e4-4582-ae3b-68db42ea7df


WINDOWS APPLICATION

1. CONVERT DIGITS INTO WEORDS

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace ex2<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void button1_Click(object sender, EventArgs e)
        {
            lbl_words.Text = NumtoWord(long.Parse(txt_num.Text));
        }
        public string NumtoWord(long number)
        {
            string word = "";
            if (number == 0)
            {
                return "Zero";
            }
            if (number < 0)
            {
                return "Minus" + Math.Abs(number);
            }
            if (number / 10000000 > 0)
            {
                word += NumtoWord(number / 10000000) + "Corer"; number %= 10000000;
            }

        if (number / 100000 > 0)
            {
                word += NumtoWord(number / 100000) + "Lacs";
                number %= 100000;
            }
            if (number / 1000 > 0)
            {
                word += NumtoWord(number / 1000) + "Thousand";
                number %= 1000;
            }
            if (number / 100 > 0)
            {
                word += NumtoWord(number / 100) + "Hundred";
                number %= 100;
            }
            if (number > 0)
            {
                string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine","ten" ,"Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen", "Eighteen", "Nineteen" };
                string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety" };
                if (number < 20)
                {
                    word += units[number];
                }
                else
                {
                    word += Tens[number / 10];
                    if (number % 10 > 0)
                    {
                        word += units[number % 10];
                    }
                }
            }
            return word;
        }
    }
}

            

OUTPUT:


![image](https://user-images.githubusercontent.com/97940767/157811354-31ba1c0e-df5d-4955-9027-d3f228c69fa9.png)
![image](https://user-images.githubusercontent.com/97940767/157811446-b77dd21d-7724-4ed1-a02b-2f06beef44c1.png)


2. PROGRAM TO REVERSE ,TRIM, PADDING A NUMBER

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace ex4<br>
{
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {
            InitializeComponent();<br>
        }<br>

        private void button1_Click(object sender, EventArgs e)
        {
            string inputString, revstr = "";
            int Length;
            inputString = txtInput.Text;
            Length = inputString.Length - 1;
            while (Length >= 0)
            {
                revstr = revstr + inputString[Length];
                Length--;
            }
            MessageBox.Show("Reverse String Is : " + revstr, "Result");
        }

        private void button2_Click(object sender, EventArgs e)
        {
            string inputString;
            inputString = txtInput.Text;
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");

        }

        private void button3_Click(object sender, EventArgs e)
        {
            string inputString;
            inputString = txtInput.Text;
            inputString = inputString.PadLeft(10, '*');
            inputString = inputString.PadRight(15, '*');
            MessageBox.Show("String After Padding : " + inputString, "Result");

        }
    }
}

Output:


![image](https://user-images.githubusercontent.com/97940767/157821183-7a9d2661-9d90-4d8a-ba94-5edccbecb7ec.png)
![image](https://user-images.githubusercontent.com/97940767/157821287-fc76bb8e-97b0-49e1-b13d-c39e27fb892a.png)
![image](https://user-images.githubusercontent.com/97940767/157821364-207e1d86-4b80-4644-9911-12b1d125a0a0.png)
![image](https://user-images.githubusercontent.com/97940767/157821421-cd64dc22-9260-459f-a2f2-c4fe0384e571.png)

**3.TO CREATYE A PROGRESS BAR**

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading;<br>
using System.Windows.Forms;<br>

namespace ex5<br>
{<br>
    public partial class Form1 : Form<br>
    {
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)
        {
            for(int i=1;i<=100;i++)
            {
                Thread.Sleep(50);
                backgroundWorker1.ReportProgress(i);
            }
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            backgroundWorker1.WorkerReportsProgress = true;
            backgroundWorker1.RunWorkerAsync();
        }

        private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)
        {
            progressBar1.Value = e.ProgressPercentage;
            this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";
        }
    }
}
<br>

OUTPUT:

![image](https://user-images.githubusercontent.com/97940767/158746060-0c2ee69a-889e-42b0-81f5-99da9fac25e9.png)
![image](https://user-images.githubusercontent.com/97940767/158746145-abd080de-67ee-4908-b3c0-dcc5153e817e.png)


**4 DEVELOP A WINDOW APPLICATION TO CREATE FLAT CLOCK**
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace ex6<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            timer1.Start();<br>
        }<br>

        private void Form1_Load(object sender, EventArgs e)
        {
            System.Timers.Timer timer = new System.Timers.Timer();
            timer.Interval = 1000;//1s
            timer.Elapsed += Timer_Elapsed;
            timer.Start();
        }
        private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)
        {
            circularProgressBar1.Invoke((MethodInvoker)delegate
            {
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");
                circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM
                }); 
            }
        }

    }

OUTPUT:

![image](https://user-images.githubusercontent.com/97940767/158756050-6925eae5-858a-4dc3-a327-2ba90227d95d.png)
![image](https://user-images.githubusercontent.com/97940767/158756143-2a8a6ff3-3a30-468d-b79e-86a654d5d36b.png)





6.





using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace guess
{
    public partial class Form1 : Form
    {
        // Intialising component 
        static Random r = new Random();
        int value;
        int guessnum;
        int win = 10;
        int guess = 1;
        TextBox textBox1;
        RichTextBox richTextBox1;
        RichTextBox richTextBox2;
        Label label4;
        public Form1()
        {
            InitializeComponent();
            
                value = r.Next(10);
                this.Controls.Clear();
                this.BackColor = Color.SkyBlue;
                this.AutoSize = true;
                this.Padding = new Padding(16);

                Label label = new Label();
                label.Text = "Pick a number between 1 and 100";
                label.Bounds = new Rectangle(10, 20, 340, 40);
                label.Font = new Font("Arial", 16);
                textBox1 = new TextBox();
                textBox1.Bounds = new Rectangle(20, 50, 120, 80);
                textBox1.Font = new Font("Arial", 24);
                button1 = new Button();
                button1.Text = " Check Your Guess ";
                button1.Bounds = new Rectangle(160, 50, 120, 40);
                button1.BackColor = Color.LightGray;
                button1.Click += new EventHandler(button1_Click);
                Label label2 = new Label();
                label2.Text = "Low Guess";
                label2.Bounds = new Rectangle(20, 150, 160, 40);
                label2.Font = new Font("Arial", 18);
                richTextBox1 = new RichTextBox();
                richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);
                richTextBox1.Font = new Font("Arial", 16);
                Label label3 = new Label();
                label3.Text = "High Guess";
                label3.Bounds = new Rectangle(180, 150, 160, 40);
                label3.Font = new Font("Arial", 18);
                richTextBox2 = new RichTextBox();
                richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);
                richTextBox2.Font = new Font("Arial", 16);
                label4 = new Label();
                label4.Bounds = new Rectangle(20, 100, 340, 40);
                label4.Font = new Font("Arial", 16);
                this.Controls.Add(label);
                this.Controls.Add(textBox1);
                this.Controls.Add(button1);
                this.Controls.Add(label4);
                this.Controls.Add(label2);
                this.Controls.Add(label3);
                this.Controls.Add(richTextBox1);
                this.Controls.Add(richTextBox2);
          

        }
       

        private void button1_Click(object sender, EventArgs e)
        {
            // Coding of game 
            if (textBox1.Text == "")
            {
                return;
            }
            guessnum = Convert.ToInt32(textBox1.Text);
            textBox1.Text = String.Empty;
            if (win >= 0)
            {
                if (guessnum == value)
                {
                    MessageBox.Show("You have guessed the number! \n The number was " + value);
                    InitializeComponent();
                }
                else if (guessnum < value)
                {
                    richTextBox1.Text += guessnum + "\n";
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));
                    
                }
                else if (guessnum > value)
                {
                    richTextBox2.Text += guessnum + "\n";
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));
                    
                }
                guess++;
                win--;
            }
            if (guess == 11)
            {
                label4.Text = "You loose,Correct Guess is " + value;
            }
        }
    }
}







    
    

    

