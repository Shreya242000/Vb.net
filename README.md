**1.C# Program  a print a Binary Triangle.**

using System;<br>

namespace ex2<br>
{<br>
    class BinaryTriangle<br>

    {<br>
        static void Main(string[] args)<br>
        {<br>
            int number, digit = 1;<br>
            Console.WriteLine("\nEnter the number of lines");<br>
            number = Convert.ToInt32(Console.ReadLine());<br>

            for (int i = 1; i <= number; i++)<br>
            {<br>
                for (int space = number - i; space > 0; space--)<br>
                {<br>
                    Console.Write(" ");<br>
                }<br>

                for (int j = 0; j < i; j++)<br>
                {
                    Console.Write(digit + " ");<br>
                    digit = (digit == 1) ? 0 : 1;<br>
                }<br>
                Console.Write("\n");<br>
            }<br>
        }<br>
    }<br>
}<br>

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154425191-a0b6b8b6-7a87-46de-bda0-e18f575a4ad1.png)



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








