**1.C# Program  a print a Binary Triangle.**

using System;<br>

namespace exersices<br>
{<br>
class Binarytriangle<br>
{<br>
static void Main(string[]args)<br>
{<br>
int number, digit = 1;<br>
Console.Write("\nEnter the number of lines:");<br>
number = Convert.ToInt32(Console.ReadLine());<br>
for (int i=1;i<=number;i++)<br>
{<br>
for (int space = number - i; space > 0; space--) <br>
{ <br>
Console.Write(" ");<br>
}<br>
for (int j=0;j<i;j++)<br>
{<br>
Console.Write(digit+" ");<br>
digit=(digit==1)?0:1;<br>
}<br>
}<br>
}<br>
}<br>



**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154425191-a0b6b8b6-7a87-46de-bda0-e18f575a4ad1.png)




**3.C# program to illustrate multilevel Inheritance with virtual methods**
using System;<br>

namespace ex3<br>
{<br>
class PersonalDetails<br>
{<br>
string name;<br>
int age;<br>
string gender;<br>

public PersonalDetails(string name, int age, string gender)<br>
{<br>
this.name = name;<br>
this.age = age;<br>
this.gender = gender;<br>
}<br>
public virtual void Display()<br>
{<br>
Console.WriteLine("\n------Personal Details----");<br>
Console.WriteLine("Name    :" + name);<br>
Console.WriteLine("Age     :" + age);<br>
Console.WriteLine("Gender  :" + gender);<br>
}<br>
}<br>
class CourseDetails : PersonalDetails<br>
{<br>
int regNo;
string course<br>;
int semester;<br>

public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)<br>
{<br>
this.regNo = regNo;<br>
this.course = course;<br>
this.semester = semester;<br>
}<br>

public override void Display()<br>
{<br>
base.Display();<br>
Console.WriteLine("\n------Course Details------\n");<br>
Console.WriteLine("Register Number :" + regNo);<br>
Console.WriteLine("Course          :" + course);<br>
Console.WriteLine("Semester        :" + semester);<br>
}<br>
}<br>

class MarksDetails : CourseDetails<br>
{<br>
int[] marks = new int[5];<br>
int total;<br>
float average;<br>
string grade;<br>
int flagFail;<br>

public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age,gender, regNo, course, semester)<br>
{<br>
total = 0;<br>
for (int i = 0; i < 5; i++)<br>
{<br>
this.marks[i] = marks[i];<br>
total += marks[i];<br>

if (marks[i] < 35)<br>
{<br>
flagFail = 1;<br>
}<br>
}<br>
Calculate();<br>
}<br>
private void Calculate()<br>
{<br>
            average = total / 5;<br>

            if (flagFail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "First Class";<br>
            else if (average >= 50<br>)
                grade = "second Class";<br>
            else<br>
                grade = "Pass Class";<br>
        }<br>
        public override void Display()<br>
        {<br>
            base.Display();<br>
            Console.WriteLine("\n----Mark Details----");<br>
            Console.Write("marks in 5 subjects: ");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.Write(marks[i] + " ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total   :" + total);<br>
            Console.WriteLine("Average :" + average);<br>
            Console.WriteLine("Grade   :" + grade);<br>
        }<br>
    }<br>
    class MultiLevel<br>
    {<br>
        public static void Main(string[] agrs)<br>
        {<br>
            MarksDetails Student1 = new MarksDetails("Shreya", 22, "Female", 202090001, "Msc", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            Student1.Display();<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154623000-35a144e4-2645-49f7-9978-c2a6fd88d76f.png)






**4.C# program to create a Gray code**
using System;<br>

namespace Ex4<br>
{<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
        }<br>

        static void Main(string[] args)<br>
        {<br>
            int InputNum, GrayNum;<br>
            Console.Write("\nEnter the decimal number:");<br>
            InputNum = Convert.ToInt32(Console.ReadLine());<br>

            Console.WriteLine("\nbinary equivalent of {0}:  {1} ", InputNum, Convert.ToString(InputNum, 2));<br>

            GrayNum = getGray(InputNum);<br>
            Console.WriteLine("\n Gray code equivalent of {0}:  {1} ", InputNum, Convert.ToString(InputNum, 2));<br>
        }<br>

    }<br>
}<br>


**OUTPUT**








**5.C# program to calculate volumate of 2 boxes and find the recultant volume after addition of 2 boxes by implementing operator overloading**
using System;<br>

namespace ex5<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>

        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width, float height, float length)<br>
        {<br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = height;<br>
        }<br>
        public static float operator +(Box box1, Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return base.ToString();<br>
            {<br>
                return "box with width" + width + ",height" + height + "and length" + length;<br>
            }<br>
        }<br>
        class OperatorOverloading<br>
        {<br>
            public static void Main()<br>
            {<br>
                Box box1 = new Box(10, 20, 30);<br>
                Box box2 = new Box(25, 32, 15);<br>

                Console.WriteLine("Volume of {0} is:{1}", box1, box1.Volume);<br>
                Console.WriteLine("Volume of {0} is:{1}", box2, box2.Volume);<br>
                Console.WriteLine("Volume after adding boxes:{0}", box1 + box2);<br>
            }<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154622907-6f7e5bc1-4872-4fac-a10b-95353d48f475.png)



**6.C# program to implement principle of delegate converting input string to uppercase first last and entire string**
using System;<br>

namespace ex6<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            Char[] buffer = input.ToCharArray();<br>
            buffer[0] = char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        { <br>
          Char[] buffer = input.ToCharArray();<br>
          buffer[buffer.Length-1] = char.ToUpper(buffer[buffer.Length-1]);<br>
          return new string (buffer);<br>
        }<br>
        static string UppercaseAll(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input,UppercaseDelegate del)<br>
            {<br>
            Console.WriteLine("Input String:{0}", input);<br>
            Console.WriteLine("Output String:{0}",del( input));<br>
        }<br>
        static void Main()<br>
        {<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseAll));<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
    }<br>
    
**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154623846-5ee21756-ccd2-416d-882d-df8cbb87332b.png)

**7.C# program to generate register number automatically for 100 students using static constructs**

using System;

namespace ex7
{
    class RegisterNum<br>
    {
        int regNo;<br>
        static int startNum;<br>

        static RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
            regNo = ++startNum;<br>
        }<br>
        public static void Main(string[] args)<br>
        {<br>
            for (int i = 0; i < 100; i++)<br>
            {<br>
                RegisterNum Student = new RegisterNum();<br>
                Console.WriteLine("Student{0}:{1}", i + 1, Student.regNo);<br>
            }<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154624217-5ae8cf9c-d4e9-4e1b-a7a1-effb692edb4d.png)


**8.C# program to find the frequency of the word "is" in a given sentance**
using System;

namespace ex8
{
    class FrequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count = 0;<br>
            string inputString;<br>
            Console.WriteLine("\n-----Frequency of Word 'is'-------");<br>
            Console.Write("\n Enter the input String");<br>
            inputString = Console.ReadLine();<br>
            char[] separator = { ',', ' ', '.', '!', '\n' };<br>
            string testString = inputString.ToLower();<br>
            string[] outcomes = testString.Split(separator);<br>
            
            foreach(String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\n Number of 'is'in'"+inputString+"'is" + count);<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154624761-edc9a8a6-eb98-4935-934d-6009a8e4497c.png)

**9.C# program that beanchmark 2D,jagged array allocation**

using System;using System;
using System.Diagnostics;

namespace ex9
{
    class BenchmarkAllocation

    {
        const int _max = 10000;
        static void Main(string[] args)
        {
            var Arr2D = new int[100, 100];
            var ArrJagged = new int[100][];

            for (int i = 0; i < 100; i++)
            {
                ArrJagged[i] = new int[100];
            }
            var Stopwatch2D = Stopwatch.StartNew();
            for (int i = 0; i < _max; i++)
            {
                for (int j = 0; j < 100; j++)
                {
                    for (int k = 0; k < 100; k++)
                    {
                        Arr2D[j, k] = k;
                    }
                }
            }
            Stopwatch2D.Stop();

            var StopwatchJagged = Stopwatch.StartNew();
            for (int i = 0; i < _max; i++)
            {
                for (int j = 0; j < 100; j++)
                {
                    for (int k = 0; k < 100; k++)
                    {
                        ArrJagged[j][k] = k;
                    }
                }
            }

            StopwatchJagged.Stop();
            Console.Write("\n Time taken for allocation in case of 2D array:");
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "miliseconds");
            Console.Write("\n Time taken for allocation in cse Jagged array:");
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds+ "miliseconds");


        }
    }
}

using System.Diagnostics;

namespace ex9
{
    class BenchmarkAllocation

    {
        const int _max = 10000;
        static void Main(string[] args)
        {
            var Arr2D = new int[100, 100];
            var ArrJagged = new int[100][];

            for (int i = 0; i < 100; i++)
            {
                ArrJagged[i] = new int[100];
            }
            var Stopwatch2D = Stopwatch.StartNew();
            for (int i = 0; i < _max; i++)
            {
                for (int j = 0; j < 100; j++)
                {
                    for (int k = 0; k < 100; k++)
                    {
                        Arr2D[j, k] = k;
                    }
                }
            }
            Stopwatch2D.Stop();

            var StopwatchJagged = Stopwatch.StartNew();
            for (int i = 0; i < _max; i++)
            {
                for (int j = 0; j < 100; j++)
                {
                    for (int k = 0; k < 100; k++)
                    {
                        ArrJagged[j][k] = k;
                    }
                }
            }

            StopwatchJagged.Stop();
            Console.Write("\n Time taken for allocation in case of 2D array:");
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "miliseconds");
            Console.Write("\n Time taken for allocation in cse Jagged array:");
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds+ "miliseconds");


        }
    }
}

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154628508-a298606d-23f2-46dc-b74f-3d7f8ef65710.png)


**10.C# program to find the sum of the valuve on diagnal of the matrix**

using System;

namespace ex10
{
    class SumOfDiagnonals
    {
        static void Main(string[] args)
        {
            int MaxRow, MaxCol, Sum = 0;
            int[,] Matrix;

            Console.WriteLine("\n----SUM OF DIAGNOL OF MATRIX-----\n");
            Console.WriteLine("\n Enter the number of rows:");
            MaxRow = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("\n Enter the number of columns:");
            MaxCol = Convert.ToInt32(Console.ReadLine());

            if (MaxRow != MaxCol)
            {
                Console.WriteLine("\n The Dimension entered are not of squre Matrix:");
                Console.WriteLine("\nExiting the program..");
                return;
            }
            Matrix = new int[MaxRow, MaxCol];

            for (int i=0; i<MaxRow; i++)
            {
                for(int j=0;j<MaxCol;j++)
                {
                    Console.Write("\nEnter the {0},{1}th element of the matrix:", (i + 1), (j + 1));
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());
                }
            }
            Console.WriteLine("\n The enterd Matrix is:");
            for (int i = 0; i < MaxRow; i++)
            {
                for (int j = 0; j < MaxCol; j++)
                {
                    Console.Write(" " + Matrix[i, j]);

                    if (i == j)
                    {
                        Sum += Matrix[i, j];
                    }
                }
                Console.WriteLine();
            }
            Console.WriteLine("\n The Sum Of Diagonal is" + Sum);
            }


        }
    }
   
**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154628852-f360f892-652c-489b-ac06-26817fd1ade7.png)


**11.C# program to create a file,check the existance of a file and Read the contents of the file **

using System;<br>
using System.IO;<br>

namespace ex11<br>
{<br>
    class FileRead<br>
    {<br>
        static void Main()<br>
        {<br>
            String fileName;<br>
            while (true)<br>
            {<br>
                Console.WriteLine("\n--------MENU-------");<br>
                Console.WriteLine("\n1.Create a File");<br>
                Console.WriteLine("\n 2.Existence of the file");<br>
                Console.WriteLine("\n 3.Read the Contents of the file");<br>
                Console.WriteLine("\n 4.Exit");<br>
                Console.Write("\n Enter your choice:");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>

                {<br>
                    case 1:<br>
                        Console.Write("\n Enter the file name to create:");<br>
                        fileName = Console.ReadLine();<br><br>
                        Console.WriteLine("\n Write the Contents to the File:\n");
                         string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(fileName))<br>
                        {<br>
                            fileStr.WriteLine(r);<br>
                        }<br>
                        Console.WriteLine("File is Created...");<br>
                        break;<br>

                    case 2:<br>
                        Console.Write("\n Enter the file name:");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File Exists..");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exist in the current dirctory!");<br>
                        }<br>
                        break;<br>

                    case 3:<br>
                        Console.Write("Enter the file name to read the contents:\n");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = "";<br>
                                Console.WriteLine("Here is the content of the file:");<br>
                                while ((s = sr.ReadLine()) != null)<br>
                                {<br>
                                    Console.WriteLine(s);<br>
                                }<br>
                                Console.WriteLine("");<br>
                            }<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exists");<br>
                        }<br>
                        break;<br>

                    case 4:<br>
                        Console.WriteLine("\n Existing...");<br>
                        return;<br>

                    default:<br>
                        Console.WriteLine("\n Invalid choice");<br>
                        break;<br>
                }<br>
            }<br>
        }<br>

    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154629978-3e793434-c1cb-4e14-b2d8-37029da6339a.png)


**12.C# program to perform file comparision**

using System;<br>
using System.IO;<br>

namespace ex12<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string file1;<br>
            string file2;<br>
           
            Console.Write("Enter the first file path:");<br>
            file1 = Console.ReadLine();<br>

            Console.Write("Enter the second file path:");<br>
            file2 = Console.ReadLine();<br>

            if (!File.Exists(file1))<br>
            {<br>
                Console.WriteLine("Second file does not exist!");<br>
            }<br>
            else if (!File.Exists(file2))<br>
            {<br>
                Console.WriteLine("Second file Does not exit!");<br>
            }<br>
            else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
            {<br>
                Console.WriteLine("Both files contain in the same content"); ;<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("Contents of files are not same");<br>
            }<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154630682-9f5f20bf-aa30-4675-aee5-3f5ae6f84fd0.png)

**13.C# program to implement Icomparable Interface using system**

using System;<br>
namespace ex13<br>
{<br>
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
            if ((float)z / n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
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
            Fraction[] a = {<br>
 new Fraction(5,2),<br>
 new Fraction(29,6),<br>
 new Fraction(4,5),<br>
 new Fraction(10,8),<br>
 new Fraction(34,7)<br>
 };<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying Fractions: ");<br>
            foreach (Fraction f in a)<br>
            {<br>
                Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154631353-6dfb9d26-e6f7-43bc-a216-5a0e8c34560c.png)


**14.C# program to create Thread pools**

using System;<br>
using System.Threading;<br>
namespace ex14<br>
{<br>
    class ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread1 is executing");<br>
            }<br>
        }<br>
        public void ThreadFun2(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread2 is executing");<br>
            }<br>
        }<br>
        public static void Main()<br>
        {<br>
            ThreadPoolProg TP = new ThreadPoolProg();<br>
            for (int i = 0; i < 2; i++)<br>
            {<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>
            }<br>
            Console.ReadKey();<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154631704-4b540ead-c04d-41aa-ad7c-acde3a22270e.png)

**15.C# program to demonstrate error handling using try,catch and finally block**

using System;<br>
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
                Console.WriteLine("AgeIsNegativeException: {0}", e.Message);<br>
            }<br>
            finally<br>
            {<br>
                Console.WriteLine("Execution of Finally block is done.");<br>
            }<br>
        }<br>
    }<br>
}<br>
public class AgeIsNegativeException : Exception<br>
{<br>
    public AgeIsNegativeException(string message) : base(message)<br>
    {<br>
    }<br>
}<br>
public class Age<br>
{<br>
    int age = -5;<br>
    public void displayAge()<br>
    {<br>
        if (age < 0)<br>
        {<br>
            throw (new AgeIsNegativeException("Age cannot be negative"));<br>
        }<br>
        else<br>
        {<br>
            Console.WriteLine("Age is: {0}", age);<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154632142-377b1db9-f89a-44b7-9ed5-f3b96272f7e9.png)


**Fibonocie number**

using System;  
  public class FibonacciExample  
   {  
     public static void Main(string[] args)  
      {  
         int n1=0,n2=1,n3,i,number;    
         Console.Write("Enter the number of elements: ");    
         number = int.Parse(Console.ReadLine());  
         Console.Write(n1+" "+n2+" "); //printing 0 and 1    
         for(i=2;i<number;++i) //loop starts from 2 because 0 and 1 are already printed    
         {    
          n3=n1+n2;    
          Console.Write(n3+" ");    
          n1=n2;    
          n2=n3;    
         }    
      }  
   }  
   
   **OUTPUT**
   
   ![image](https://user-images.githubusercontent.com/97940851/155657439-d6233097-7af8-40c8-80e2-e6626e63b4bb.png)
   
   **Prime number**
   
   using System;
public class ex16
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
   
   
  **OUTPUT**
   
   ![image](https://user-images.githubusercontent.com/97940851/155658678-723793ca-a5fb-4016-9cb3-43807086b603.png)

   ![image](https://user-images.githubusercontent.com/97940851/155659122-5a6cc4e0-1df1-411f-9cb5-5030b10b2636.png)
   
   
  **Palindrome**
  
  using System;
public class ex18
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
  
  
  
  **OUTPUT**
  
   ![image](https://user-images.githubusercontent.com/97940851/155659836-f569f940-e582-4937-8f88-8c853c395e9f.png)
   
   ![image](https://user-images.githubusercontent.com/97940851/155660513-4705ad29-438e-4403-a849-928cc0b71b2b.png)
   
   
   **Factorial**
   
   using System;
public class ex19
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
   
   
   
   **OUTPUT**
   
   ![image](https://user-images.githubusercontent.com/97940851/155661737-0581f2c7-24b5-4fed-baa9-c56a50cb45dc.png)
   
   
   **Sum of Digits**
   
   using System;
public class ex20
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

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/155662355-9354679a-3b77-481a-87aa-4f8206f5e12a.png)

![image](https://user-images.githubusercontent.com/97940851/155662476-12b49ca4-bd40-4ffa-b5ea-01d2e33d6bae.png)

**Reversed number**

using System;
public class ex21
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


**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/155663443-8244bc9d-2343-4143-b440-53a201d095dd.png)


**Swap two numbers without using third variable**

using System;
public class ex22
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


**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/155663752-afc58582-b2d7-49b1-8288-df44844a818a.png)







   
   






   














