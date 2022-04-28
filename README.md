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

**2 C# program to check whether the entered number is an AMICABLE NUMBER or not**<br>
using System;<br>

namespace ex4<br>
{<br>
    class AmicableNumber<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n........AMICABLE NUMBERS........");<br>
            Console.Write("\n Enter the first number: ");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.Write("\n Enter the second number: ");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for (int i = 1; i < num1; i++)<br>
            {<br>
                if (num1 % i == 0)<br>
                {<br>
                    sum1 += i;<br>
                }<br>
            }<br>
            for (int i = 1; i < num2; i++)<br>
            {<br>
                if (num2 % i == 0)<br>
                {<br>
                    sum2 += i;<br>
                }<br>
            }<br>
            if (sum1 == num2 && sum2 == num1)<br>
            {<br>
                Console.WriteLine("\n The number {0} and {1} are amicable.", num1, num2);<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("\n The number {0} and {1} are not amicable.", num1, num2);<br>
            }<br>

   }<br>
   }<br>
}<br>

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154425457-4d3bc1d3-a81d-4081-9b7d-4f8957e5ea39.png)



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

using System;using System;<br>
using System.Diagnostics;<br>

namespace ex9<br>
{<br>
    class BenchmarkAllocation<br>

    {<br>
        const int _max = 10000;<br>
        static void Main(string[] args)<br>
        {<br>
         var Arr2D = new int[100, 100];<br>
         var ArrJagged = new int[100][];<br>
<br>
          for (int i = 0; i < 100; i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>
            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        Arr2D[j, k] = k;<br>
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>

            var StopwatchJagged = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        ArrJagged[j][k] = k;<br><br>
                    }<br>
                }<br>
            }<br>

            StopwatchJagged.Stop();<br>
            Console.Write("\n Time taken for allocation in case of 2D array:");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "miliseconds");<br>
            Console.Write("\n Time taken for allocation in cse Jagged array:");<br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds+ "miliseconds");<br>
         }<br>
    }<br>
}<br>

using System.Diagnostics;<br>
<br>
namespace ex9<br>
{<br>
    class BenchmarkAllocation<br>

    {<br>
        const int _max = 10000<br>;<br>
        static void Main(string[] args)<br>
        {<br>
            var Arr2D = new int[100, 100];<br>
            var ArrJagged = new int[100][];<br>

            for (int i = 0; i < 100; i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>
            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        Arr2D[j, k] = k;<br>
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>

            var StopwatchJagged = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        ArrJagged[j][k] = k;<br>
                    }<br>
                }<br>
            }<br>

            StopwatchJagged.Stop();<br>
            Console.Write("\n Time taken for allocation in case of 2D array:");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "miliseconds");<br>
            Console.Write("\n Time taken for allocation in cse Jagged array:");
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds+ "miliseconds");<br>


        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154628508-a298606d-23f2-46dc-b74f-3d7f8ef65710.png)


**10.C# program to find the sum of the valuve on diagnal of the matrix**

using System;<br>

namespace ex10<br>
{<br><br>
    class SumOfDiagnonals<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int MaxRow, MaxCol, Sum = 0;<br>
            int[,] Matrix;<br>

            Console.WriteLine("\n----SUM OF DIAGNOL OF MATRIX-----\n");<br>
            Console.WriteLine("\n Enter the number of rows:");<br>
            MaxRow = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\n Enter the number of columns:");<br>
            MaxCol = Convert.ToInt32(Console.ReadLine());<br>

            if (MaxRow != MaxCol)<br>
            {<br>
                Console.WriteLine("\n The Dimension entered are not of squre Matrix:");<br>
                Console.WriteLine("\nExiting the program..");<br>
                return;<br>
            }<br>
            Matrix = new int[MaxRow, MaxCol];<br>

            for (int i=0; i<MaxRow; i++)<br>
            {<br>
                for(int j=0;j<MaxCol;j++)<br>
                {<br>
                    Console.Write("\nEnter the {0},{1}th element of the matrix:", (i + 1), (j + 1));<br>
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
                }<br>
            }<br>
            Console.WriteLine("\n The enterd Matrix is:");<br>
            for (int i = 0; i < MaxRow; i++)<br>
            {
                for (int j = 0; j < MaxCol; j++)<br>
                {
                    Console.Write(" " + Matrix[i, j]);<br>
<br>
                    if (i == j)<br>
                    {<br>
                        Sum += Matrix[i, j];<br>
                    }<br>
                }<br>
                Con<br>sole.WriteLine();<br>
            }<br>
            Console.WriteLine("\n The Sum Of Diagonal is" + Sum);<br>
            }<br>


        }<br>
    }<br>
   
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


**16.Fibonocie number**

using System;<br>  
  public class ex16<br>  
   {<br>
     public static void Main(string[] args)<br>  
      {<br> 
         int n1=0,n2=1,n3,i,number;<br>    
         Console.Write("Enter the number of elements: ");<br>    
         number = int.Parse(Console.ReadLine());<br>  
         Console.Write(n1+" "+n2+" ");<br>    
         for(i=2;i<number;++i)<br>    
         {<br>    
          n3=n1+n2;<br>    
          Console.Write(n3+" ");<br>    
          n1=n2;<br>    
          n2=n3;<br>    
         }<br>    
      }<br>  
   }<br>  
   
   **OUTPUT**
   
   ![image](https://user-images.githubusercontent.com/97940851/155657439-d6233097-7af8-40c8-80e2-e6626e63b4bb.png)
   
   **17.Prime number**
   
   using System;<br>
public class ex17<br>
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
   
   
  **OUTPUT**
   
   ![image](https://user-images.githubusercontent.com/97940851/155658678-723793ca-a5fb-4016-9cb3-43807086b603.png)

   ![image](https://user-images.githubusercontent.com/97940851/155659122-5a6cc4e0-1df1-411f-9cb5-5030b10b2636.png)
   
   
  **18.Palindrome**
  
  using System;<br>
public class ex18<br>
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
  
  
  
  **OUTPUT**
  
   ![image](https://user-images.githubusercontent.com/97940851/155659836-f569f940-e582-4937-8f88-8c853c395e9f.png)
   
   ![image](https://user-images.githubusercontent.com/97940851/155660513-4705ad29-438e-4403-a849-928cc0b71b2b.png)
   
   
   **19.Factorial**
   
   using System;<br>
public class ex19<br>
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
    }
}
   
   
   
   **OUTPUT**
   
   ![image](https://user-images.githubusercontent.com/97940851/155661737-0581f2c7-24b5-4fed-baa9-c56a50cb45dc.png)
   
   
   **20.Sum of Digits**
   
   using System;<br>
public class ex20<br>
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

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/155662355-9354679a-3b77-481a-87aa-4f8206f5e12a.png)

![image](https://user-images.githubusercontent.com/97940851/155662476-12b49ca4-bd40-4ffa-b5ea-01d2e33d6bae.png)

**21.Reversed number**

using System;<br>
public class ex21<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, reverse = 0, rem;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n != 0)<br>
        {<br>
            rem = n % 10;<br>
            reverse = reverse * 10 + rem;<br>
            n /= 10;<br>
        }<br>
        Console.Write("Reversed Number: " + reverse);<br>
    }<br>
}<br>


**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/155663443-8244bc9d-2343-4143-b440-53a201d095dd.png)


**22.Swap two numbers without using third variable**

using System;<br>
public class ex22<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int a = 5, b = 10;<br>
        Console.WriteLine("Before swap a= " + a + " b= " + b);<br>
        a = a * b; //a=50 (5*10)<br>      
        b = a / b; //b=5 (50/10)<br>      
        a = a / b; //a=10 (50/5)<br>    
        Console.Write("After swap a= " + a + " b= " + b);<br>
    }<br>
}<br>


**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/155663752-afc58582-b2d7-49b1-8288-df44844a818a.png)



**23.Decimal to Binary**

using System;<br>
public class ConversionExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i;<br>
        int[] a = new int[10];<br>
        Console.Write("Enter the number to convert: ");<br>
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

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/156501240-5134a011-5171-4f27-bbdd-81f87aeefed1.png)


**24.Convert number in character**

using System;<br>  
  public class ConversionExample<br>  
   {  <br>
     public static void Main(string[] args)<br>  
      {  <br>
       int n,sum=0,r;<br>     
       Console.Write("Enter the Number= ");<br>    
       n= int.Parse(Console.ReadLine());<br>     
       while(n>0)<br>      
       {<br>      
        r=n%10;<br>      
        sum=sum*10+r;<br>      
        n=n/10;<br>      
       }<br>      
       n=sum;<br>      
       while(n>0)<br>      
       {<br>      
        r=n%10;<br>      
        switch(r)<br>      
        {<br>      
         case 1:<br>      
         Console.Write("one ");<br>  
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
         Console.Write("nine ");<br>    
         break;<br>      
         case 0:<br>      
         Console.Write("zero ");<br>    
         break;<br>      
         default:<br>      
         Console.Write("tttt ");<br>      
         break;<br>      
        }<br>   
        n=n/10;<br>      
       }<br>
   } <br> 
  }<br>  

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/156502100-b190c5d7-c6b5-43b9-9140-706f6d6eedf6.png)


**25.Alphabet Triangle**

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

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/156504836-17142930-2242-4d9b-8740-83af5d2025e2.png)


**26.Number Triangle**

using System;<br>  
  public class PrintExample<br>    
   { <br>  
     public static void Main(string[] args) <br>   
      { <br>   
       int  i,j,k,l,n;<br>             
       Console.Write("Enter the Range=");<br>      
       n= int.Parse(Console.ReadLine());<br>       
       for(i=1; i<=n; i++)<br>        
       {<br>            
        for(j=1; j<=n-i; j++)<br>        
        {<br>        
         Console.Write(" ");<br>        
        }<br>        
        for(k=1;k<=i;k++)<br>        
        {<br>        
         Console.Write(k);<br>        
        }<br>        
        for(l=i-1;l>=1;l--)<br>        
        {<br>        
        Console.Write(l);<br>        
        }<br>        
        Console.Write("\n");<br>        
       }<br>         
   }<br>    
  }<br>    
  
  **OUTPUT**
  
  ![image](https://user-images.githubusercontent.com/97940851/156506392-4c395ae0-4f21-494c-987c-d51ae6876b52.png)
  
  
  **27.Fibonacci Triangle**
  sing System;<br>
public class PrintExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int a = 0, b = 1, i, c, n, j;<br>
        Console.Write("Enter the limit: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= n; i++)<br>
        {<br>
            a = 0;<br>
            b = 1;<br>
            Console.Write(b + "\t");<br>
            for (j = 1; j < i; j++)<br>
            {<br>
                c = a + b;<br>
                Console.Write(c + "\t");<br>
                a = b;<br>
                b = c;<br>
            }<br>
            Console.Write("\n");<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/156515360-3951956a-1c10-4535-b87b-49d3267f2e00.png)







**16. C# Program to Convert Digits to Words**

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace lab16<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        <br>}<br>

        private void button1_Click(object sender, EventArgs e)<br>
        
            {<br>
                lbl_words.Text = NumtoWord(long.Parse(txt_num.Text));<br>
            }<br>
            public string NumtoWord(long number)<br>
            {<br>
                string word = "";<br>
                if (number == 0)<br>
                {<br>
                    return "Zero";<br>
                }<br>
                if (number < 0)<br>
                {<br>
                    return "Minus" + Math.Abs(number);<br>
                }<br>
                if (number / 10000000 > 0)<br>
                {<br>
                    word += NumtoWord(number / 10000000) + "Corer";<br>
                    number %= 10000000;<br>
                }<br>

            if (number / 100000 > 0)<br>
                {<br>
                    word += NumtoWord(number / 100000) + "Lacs";<br>
                    number %= 100000;<br>
                }<br>
                if (number / 1000 > 0)<br>
                {<br>
                    word += NumtoWord(number / 1000) + "Thousand";<br>
                    number %= 1000;<br>
                }<br>
                if (number / 100 > 0)<br>
                {<br>
                    word += NumtoWord(number / 100) + "Hundred";<br>
                    number %= 100;<br>
                }<br><br>
                if (number > 0)<br>
                {<br>
                    string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six",<br>
"Seven", "Eight", "Nine","Ten", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen",<br>
"Seventeen", "Eighteen", "Nineteen" };<br>
                    string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty",<br>
"Sixty", "Seventy", "Eighty", "Ninety" };<br>
                    if (number < 20)<br>
                    {<br>
                        word += units[number];<br>
                    }<br>
                    else<br>
                    {<br>
                        word += Tens[number / 10];<br>
                        if (number % 10 > 0)<br>
                        {<br>
                            word += units[number % 10];<br>
                        }<br>
                    }<br>
                }<br>
                return word;<br>
            }<br>

        private void lbl_words_Click(object sender, EventArgs e)<br>
        {<br>

        }<br>
    }<br>
    }<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/158942155-ca652b7e-e539-40a3-83ef-d457182b8c44.png)

**18. C# Program to Perform Reversal, Padding and Trimming Operations on string.**

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace lab18<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void btnrev_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString, revstr = "";<br>
            int Length;<br>
            inputString = txtInput.Text;<br>
            Length = inputString.Length - 1;<br>
            while (Length >= 0)<br>
            {<br>
                revstr = revstr + inputString[Length];<br>
                Length--;<br>
            }<br>
            MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>
        }<br>

        private void btntrim_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
        }<br>

        private void btnpad_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            inputString = inputString.PadLeft(10, '*');<br>
            inputString = inputString.PadRight(15, '*');
            MessageBox.Show("String After Padding : " + inputString, "Result");
        }
    }
}
    
    
    
**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/158943063-04a43ac7-f0ef-4aca-b3f7-5ebda8595ea5.png)

![image](https://user-images.githubusercontent.com/97940851/158943198-9a1616b3-0704-4ec3-b785-c20f60c42f7c.png)

![image](https://user-images.githubusercontent.com/97940851/158943264-45d3e50a-f904-45e9-8f0e-2f8b5e9e0c96.png)


**19. C# Program to Create a Progress Bar Control.**

using System;<br>
using System.ComponentModel; <br>
using System.Threading; <br>
using System.Windows.Forms<br> <br>
namespace WindowsFormsApplication1 <br>
{ <br>
 public partial class Form1: Form <br>
 { <br>
 public Form1() <br>
 { <br>
 InitializeComponent(); <br>
 }<br>
}<br>
private void Form1_Load(object sender, System.EventArgs e) <br>
 { <br>
backgroundWorker1.WorkerReportsProgress = true;<br>
 backgroundWorker1.RunWorkerAsync(); <br>
 }<br>
private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e) <br>
 { <br>
 for (int i = 1; i <= 100; i++) <br>
 { <br>
 Thread.Sleep(50); <br>
 backgroundWorker1.ReportProgress(i); <br>
 } <br>
 }<br> 
 private void backgroundWorker1_ProgressChanged(object sender, <br>
 ProgressChangedEventArgs e)<br> 
 { <br><br>
 progressBar1.Value = e.ProgressPercentage; <br>
 this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";<br>
 } <br>
 } <br>
}<br><br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/158939841-71ce2448-dbbc-4964-b0a0-952f158d8834.png)

![image](https://user-images.githubusercontent.com/97940851/158939912-1825c96d-9e04-4f7c-8926-e0b11b9e0b44.png)


**20. Develop a winform application to create flat clock**

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace lab20<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            timer1.Start();<br>
        }<br>

        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            System.Timers.Timer timer = new System.Timers.Timer();<br>
            timer.Interval = 1000;//1s<br>
            timer.Elapsed += Timer_Elapsed;<br>
            timer.Start();<br>
        }<br><br>
        private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
        {<br>
            circularProgressBar1.Invoke((MethodInvoker)delegate<br>
            {<br>
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");<br>
                circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM<br>
            });<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/158940615-f1c694fa-c7e4-4f0c-84fd-1095c4e802dd.png)


**21. C# Program to perform a number guessing game**

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br><br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
<br>
namespace lab21<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        // Intialising component <br>
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        Button button1;<br>
        TextBox textBox1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            {<br>
                value = r.Next(10);<br>
                this.Controls.Clear();<br>
                this.BackColor = Color.SkyBlue;<br>
                this.AutoSize = true;<br>
                this.Padding = new Padding(16);<br>
                Label label = new Label();<br>
                label.Text = "Pick a number between 1 and 100";<br>
                label.Bounds = new Rectangle(10, 20, 340, 40);<br>
                label.Font = new Font("Arial", 16);<br>
                textBox1 = new TextBox();<br>
                textBox1.Bounds = new Rectangle(20, 50, 120, 80);<br>
                textBox1.Font = new Font("Arial", 24);<br>
<br>
                button1 = new Button();<br>
                button1.Text = " Check Your Guess ";<br>
                button1.Bounds = new Rectangle(160, 50, 120, 40);<br>

                button1.BackColor = Color.LightGray;<br>
                button1.Click += new EventHandler(button1_Click);<br>
                Label label2 = new Label();<br>
                label2.Text = "Low Guess";<br>
                label2.Bounds = new Rectangle(20, 150, 160, 40);<br>
                label2.Font = new Font("Arial", 18);<br>
                richTextBox1 = new RichTextBox();<br><br>
                richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);<br>
                richTextBox1.Font = new Font("Arial", 16);<br>

                Label label3 = new Label();<br>
                label3.Text = "High Guess";<br>
                label3.Bounds = new Rectangle(180, 150, 160, 40);<br>
                label3.Font = new Font("Arial", 18);<br>
                richTextBox2 = new RichTextBox();<br>
                richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);<br>
                richTextBox2.Font = new Font("Arial", 16);<br>
                label4 = new Label();<br>
                label4.Bounds = new Rectangle(20, 100, 340, 40);<br>
                label4.Font = new Font("Arial", 16);<br>
                this.Controls.Add(label);<br>
                this.Controls.Add(textBox1);<br><br>
                this.Controls.Add(button1);<br>
                this.Controls.Add(label4);<br>
                this.Controls.Add(label2);<br>
                this.Controls.Add(label3);<br>
                this.Controls.Add(richTextBox1);<br>
                this.Controls.Add(richTextBox2);<br>
            }<br>
        }<br>
        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            // Coding of game <br>
            if (textBox1.Text == "")<br>
            {<br>
                return;<br>
            }<br>
            guessnum = Convert.ToInt32(textBox1.Text);<br>
            textBox1.Text = String.Empty;<br>
            if (win >= 0)<br>
            {<br>

                if (guessnum == value)<br>
                {<br>
                    MessageBox.Show("You have guessed the number! \n The number was " + value);<br>
                    InitializeComponent();<br>
                }<br>
                else if (guessnum < value)<br>
                {<br>
                    richTextBox1.Text += guessnum + "\n";<br>
                    label4.Text = "wrong Guess and number of guesses left are " + (10 - guess);<br>
                }<br>
                else if (guessnum > value)<br>
                {<br>
                    richTextBox2.Text += guessnum + "\n";<br>
                    label4.Text = "wrong Guess and number of guesses left are " + (10 - guess);<br>
                }<br>
                guess++;<br>
                win--;<br>
            }<br>
            if (guess == 11)<br>
            {<br><br>
                label4.Text = "You loose,Correct Guess is " + value;<br>
            }<br>
        }<br>

        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>

        }<br>
    }<br><br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/158955496-f439228b-fa8f-4bee-bb4c-ac9d391e795f.png)

**Develop an application to create a notepad**

using System;<br>
using System.IO;<br>
using System.Drawing;<br>
using System.Windows.Forms;<br>

namespace lab22<br>
{<br>

    public partial class NotepadForm : Form<br>
    {<br>

        private string fileName;<br>
        private RichTextBox txtCo<br>ntent;<br>
        private ToolBar toolBar;<br>
        internal NotepadForm()<br>
        {<br>
            fileName = null;<br>
            initializeComponents();<br>
        }<br>
        void initializeComponents()<br>
        {<br>
            this.Text = "My notepad";<br>
            this.MinimumSize = new Size(600, 450);<br>
            this.FormClosing += new FormClosingEventHandler(NotepadClosing);<br>
            this.MaximizeBox = true;<br>
            toolBar = new ToolBar();<br>
            toolBar.Font = new Font("Arial", 16);<br>
            toolBar.Padding = new Padding(4);<br>
            toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
            ToolBarButton toolBarButton1 = new ToolBarButton();<br>
            ToolBarButton toolBarButton2 = new ToolBarButton();<br>
            ToolBarButton toolBarButton3 = new ToolBarButton();<br>
            toolBarButton1.Text = "New";<br>
            toolBarButton2.Text = "Open";<br>
            toolBarButton3.Text = "Save";<br>
            toolBar.Buttons.Add(toolBarButton1);<br>
            toolBar.Buttons.Add(toolBarButton2);<br>
            toolBar.Buttons.Add(toolBarButton3);<br>
            txtContent = new RichTextBox();<br>
            txtContent.Size = this.ClientSize;<br>
            txtContent.Height -= toolBar.Height;<br>
            txtContent.Top = toolBar.Height;<br>
            txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right | AnchorStyles.Top | AnchorStyles.Bottom;<br>
            txtContent.Font = new Font("Arial", 16);<br>
            txtContent.AcceptsTab = true;<br>
            txtContent.Padding = new Padding(8);<br>

            this.Controls.Add(toolBar);<br>
            this.Controls.Add(txtContent);<br><br>
        }<br>
        private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br>
        {<br>
            saveFile();<br>
            switch (toolBar.Buttons.IndexOf(e.Button))<br>
            {<br>
                case 0:<br>
                    this.Text += "My notepad";<br>
                    txtContent.Text = string.Empty;<br>
                    fileName = null;<br>
                    break;<br>
                case 1:<br>
                    OpenFileDialog openDlg = new OpenFileDialog();<br><br>
                    if (DialogResult.OK == openDlg.ShowDialog()) ;<br>
                    {<br>
                        fileName = openDlg.FileName;<br>
                        txtContent.LoadFile(fileName);<br>
                        this.Text = "My notepad " + fileName;<br>
                    }<br>
                    break;<br>
            }<br>
        }<br>

        void saveFile()<br>
        {<br>
            if (fileName == null)<br>
            {<br>
                SaveFileDialog saveDlg = new SaveFileDialog();<br>
                if (DialogResult.OK == saveDlg.ShowDialog())<br>
                {<br>
                    fileName = saveDlg.FileName;<br>
                    this.Text += " " + fileName;<br>
                }<br>
            }<br>
            else<br>
            {<br>
                txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br>
            }<br>
        }<br>
        private void NotepadClosing(Object sender, FormClosingEventArgs e)<br>
        {<br>
            saveFile();<br>
        }<br>
        private void NotepadForm_Load(object sender, EventArgs e)<br>
        {<br>

        }<br>
    }<br>
}<br>
          
   

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/160997137-21d39783-db5a-47a1-bc97-40c2df57d6f9.png)

**C# Program to Perform Reversal, Padding and Trimming Operations on string.**
using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>
using System.Drawing.Drawing2D;<br>

namespace binarytree<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private Node root;<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            this.root = null;<br>
            test();<br>
        }<br>
        
    <br>
        void test()<br>
        {<br>
            textBox1.Text = "5";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "3";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "2";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "1";<br>
            btnAdd_Click(btnAdd, null);<br><br>
            textBox1.Text = "4";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "7";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "6";<br>
            btnAdd_Click(btnAdd, null);<br>
            textBox1.Text = "8";<br>
            btnAdd_Click(btnAdd, null);<br>
        }<br>

        private void btnCreate_Click(object sender, EventArgs e)<br>
        {<br>
            root = null;<br>
            pictureBox1.Image = null;<br>
        }<br>

        private void btnAdd_Click(object sender, EventArgs e)<br>
        {<br>

            int value = int.Parse(textBox1.Text);<br>
            if (root == null)<br>
                root = new Node(value);<br>
            else<br>
<br>
            {<br>
                if (root.Add(value) == false)<br>
                    MessageBox.Show("The value already exists!");<br>

            }<br>
            drawTree();<br>

        }<br>

        private void btnRemove_Click(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text);<br>
            if (root != null)<br>

            {<br>
                bool status = root.Remove(value, root,<br>ref root);<br>
                if (status == false)<br>

                {<br>
                    MessageBox.Show("the value does not exists");<br>

                }<br>

            }<br>
            drawTree();<br>
        }<br>

        private void btnSearch_Click(object sender, EventArgs e)<br>
        {<br>
            string msg;<br>
            int value = int.Parse(textBox1.Text);<br>
            if (root == null)<br>

            {<br>
                msg = "Tree is empty";<br>
            }<br>
            else<br>
<br>
            {<br>
                if (root.Exists(value))<br>

                {<br>
                    msg = "Value found";<br>
                }<br>
                else<br>

                {<br>
                    msg = "Value not found";<br>

                }<br>

            }<br><br>
            MessageBox.Show(msg);<br>

        }<br>
        void drawTree()<br>
        {<br>
            if (root != null)<br>
                pictureBox1.Image = root.Draw();<br>
            else<br>
                pictureBox1.Image = null;<br>
            this.Update();<br>
        }<br>
       /* static void Main()<br>
        {<br>
            Application.Run(new BinTreeForm());<br>
        }*/<br>
    }<br>
    class Node<br>
    {<br>
        internal Node left { get; set; }<br>
        internal Node right { get; set; }<br>
        internal int value;<br>
        internal int center = 12;<br>
        private static Bitmap nodeBg = new Bitmap(30, 25);<br>
        private static Font font = new Font("Arial", 14);<br>
        internal Node(int value)<br>
        {<br>
            this.value = value;<br>
        }<br>
        internal bool Add(int value)<br>
        {<br>
            Node node = new Node(value);<br>
            if (value < this.value)<br>
            {<br>
                if (this.left == null)<br>
                {<br>
                    this.left = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.left.Add(value);<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (this.right == null)<br>

             {<br>
                    this.right = node;<br>
                    return true;<br>
                }<br>
 else<br>
                    return this.right.Add(value);<br>
            }<br>
            return false;<br>
        }<br>
        internal bool Remove(int value, Node parent, ref Node root)<br>
        {<br>
            if (value < this.value)<br><br>
            {<br>
                if (left != null)<br>
                {<br>
                    return left.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (right != null)<br><br><br>
                {<br>
                    return right.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value == this.value)<br>
            {<br>
                bool isLeft = (this == parent.left);<br>
                if (left == null && right == null)<br>
                {<br>
                    if (root == this)<br>
                        root = null;<br>
                    else<br>
                    if (isLeft) parent.left = null; else parent.right = null;<br>
                }<br>
                else if (right == null)<br>
                {<br>
                    if (isLeft) parent.left = left; else parent.right = left;<br>
                    if (root == this)<br><br>
                        root = left;<br><br>
                }<br><br>
                else<br><br>
                {<br><br>
                    if (right.left == null)<br><br>
                    {<br><br>
                        right.left = left;<br><br>
                        if (isLeft) parent.left = right;<br><br>
                        else<br><br>

                    parent.right = right;<br><br>
                        if (root == this)<br><br>
                            root = right;<br><br>
                    }<br><br>
                    else<br><br>
                    {<br><br>
                        Node node = right;<br><br>
                        while (node.left.left != null)<br><br>
                            node = node.left;<br><br>
                        Console.WriteLine("Node: " + node.value);<br><br>
                        this.value = node.left.value;<br><br>
                        Console.WriteLine("here");<br><br>
                        node.left = null;<br><br>
                    }<br><br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
        {<br>
            Size lSize = new Size(nodeBg.Width / 2, 0);<br>
            Size rSize = new Size(nodeBg.Width / 2, 0);<br>
            Image lNodeImg = null;<br>
            Image rNodeImg = null;<br>
            int lCenter = 0, rCenter = 0;<br>

            if (this.left != null)<br>
            {<br>
                lNodeImg = left.Draw();<br>
                lSize = lNodeImg.Size;<br>
                this.center = lSize.Width;<br>
                lCenter = left.center;<br>
            }<br>
            if (this.right != null)<br>
            {<br>
                rNodeImg = right.Draw();<br><br>
                rSize = rNodeImg.Size;<br>
                rCenter = right.center;<br>
            }<br>
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height;<br><br>
            if (maxHeight > 0) maxHeight += 35;<br>

        Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height +maxHeight);<br>
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);<br>

            Graphics g = Graphics.FromImage(result);<br>
            g.SmoothingMode = SmoothingMode.HighQuality;<br>
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize));<br>
            g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);<br>

            string str = "" + value;<br>
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7,<br>
           nodeBg.Height / 2f - 12);<br>
            Pen pen = new Pen(Brushes.Black, 1.2f);<br>
            float x1 = center;<br>
            float y1 = nodeBg.Height;<br>
            float y2 = nodeBg.Height + 35;<br>
            float x2 = lCenter;<br>
            var h = Math.Abs(y2 - y1);<br>
            var w = Math.Abs(x2 - x1);<br>
            if (lNodeImg != null)<br>
            {<br>
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35);<br>
                var points1 = new List<PointF><br>
 {<br>
 new PointF(x1, y1),<br>
 new PointF(x1 - w/6, y1 + h/3.5f),<br>
 new PointF(x2 + w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2),<br>
 };<br>
                g.DrawCurve(pen, points1.ToArray(), 0.5f);<br>
            }<br>
            if (rNodeImg != null)<br>
            {<br>
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35);<br>
                x2 = rCenter + lSize.Width;<br>
                w = Math.Abs(x2 - x1);<br>
                var points = new List<PointF><br>
 {<br>
 new PointF(x1, y1),<br>
 new PointF(x1 + w/6, y1 + h/3.5f),<br>
 new PointF(x2 - w/6, y2 - h/3.5f),<br>
 new PointF(x2, y2)<br>
 };<br>

            g.DrawCurve(pen, points.ToArray(), 0.5f);<br>
            }<br>
            return result;<br><br>
        }<br>
        public bool Exists(int value)<br>
        {<br>
            bool res = value == this.value;<br>
            if (!res && left != null)<br>
                res = left.Exists(value);<br>
            if (!res && right != null)<br>
                res = right.Exists(value);<br>
            return res;<br>
        }<br>
    }<br>
}<br>

 
**OUTPUT**
    
 ![image](https://user-images.githubusercontent.com/97940851/161209478-d1350af6-e9f1-4a21-b478-1045dcc50d77.png)
    
    
**Write a program to perform money conversion.**
    
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
namespace moneyconvertion
{
 public partial class Form1 : Form
 {
 public Form1()
 {
 InitializeComponent();
 }
 private void button1_Click(object sender, EventArgs e)
 {
 {
 label4.Visible = true;
 if (textBox1.Text == "")
 {
 label4.Text = "Enter the amount";
 }
 else
 {
 Double convertedamt = Convert.ToDouble(textBox1.Text);
if (comboBox1.SelectedItem== "INR" && comboBox2.SelectedItem == 
"USD")
 {
 Double a = convertedamt / 74;
 label4.Text = a + "$";
 }
else if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == 
"SAR")
 {
 Double a = convertedamt / 17;
label4.Text = a + "SAR";
 }
else if (comboBox1.SelectedItem== "INR" && comboBox2.SelectedItem == 
"EUR")
 {
 Double a = convertedamt / 11;
 label4.Text = a + "EUR";
 }
else
{
 label4.Text = "Please Enter the conversion code";
 }
 }
 }
 }
 private void button2_Click(object sender, EventArgs e)
 {
 textBox1.Text = "";
 label4.Text = "";
 
 }
 }
}
    
**OUTPUT**
    
   ![image](https://user-images.githubusercontent.com/97940851/165695273-1b1f4b94-fdd2-4df6-a35b-db11a2edd0dc.png)













    








   
   






   














