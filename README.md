**1.C# Program  a print a Binary Triangle.**

using System;

namespace ex2
{
    class BinaryTriangle

    {
        static void Main(string[] args)
        {
            int number, digit = 1;
            Console.WriteLine("\nEnter the number of lines");
            number = Convert.ToInt32(Console.ReadLine());

            for (int i = 1; i <= number; i++)
            {
                for (int space = number - i; space > 0; space--)
                {
                    Console.Write(" ");
                }

                for (int j = 0; j < i; j++)
                {
                    Console.Write(digit + " ");
                    digit = (digit == 1) ? 0 : 1;
                }
                Console.Write("\n");
            }
        }
    }
}

**OUTPUT**

![image](https://user-images.githubusercontent.com/97940851/154425191-a0b6b8b6-7a87-46de-bda0-e18f575a4ad1.png)



**C# program to create a Gray code**
using System;

namespace Ex4
{
    class GrayCode
    {
        static int getGray(int n)
        {
            return n ^ (n >> 1);
        }

        static void Main(string[] args)
        {
            int InputNum, GrayNum;
            Console.Write("\nEnter the decimal number:");
            InputNum = Convert.ToInt32(Console.ReadLine());

            Console.WriteLine("\nbinary equivalent of {0}:  {1} ", InputNum, Convert.ToString(InputNum, 2));

            GrayNum = getGray(InputNum);
            Console.WriteLine("\n Gray code equivalent of {0}:  {1} ", InputNum, Convert.ToString(InputNum, 2));
        }

    }
}


**OUTPUT**












**3.C# program to illustrate multilevel Inheritance with virtual methods**
using System;

namespace ex3
{
    class PersonalDetails
    {
         string name;
         int age;
        string gender;

        public PersonalDetails(string name, int age, string gender)
        {
            this.name = name;
            this.age = age;
            this.gender = gender;
        }
        public virtual void Display()
        {
            Console.WriteLine("\n------Personal Details----");
            Console.WriteLine("Name    :" + name);
            Console.WriteLine("Age     :" + age);
            Console.WriteLine("Gender  :" + gender);
        }
    }
    class CourseDetails : PersonalDetails
    {
         int regNo;
        string course;
        int semester;

        public CourseDetails(string name, int age, string gender, int regNo, string course, int semester) : base(name, age, gender)
        {
            this.regNo = regNo;
            this.course = course;
            this.semester = semester;
        }

        public override void Display()
        {
            base.Display();
            Console.WriteLine("\n------Course Details------\n");
            Console.WriteLine("Register Number :" + regNo);
            Console.WriteLine("Course          :" + course);
            Console.WriteLine("Semester        :" + semester);
        }
    }

    class MarksDetails : CourseDetails
    {
        int[] marks = new int[5];
        int total;
        float average;
        string grade;
        int flagFail;

        public MarksDetails(string name, int age, string gender, int regNo, string course, int semester, int[] marks) : base(name, age,gender, regNo, course, semester)
        {
            total = 0;
            for (int i = 0; i < 5; i++)
            {
                this.marks[i] = marks[i];
                total += marks[i];

                if (marks[i] < 35)
                {
                    flagFail = 1;
                }
            }
            Calculate();
        }
        private void Calculate()
        {
            average = total / 5;

            if (flagFail == 1 || average < 40)
                grade = "Fail";
            else if (average >= 70)
                grade = "Distinction";
            else if (average >= 60)
                grade = "First Class";
            else if (average >= 50)
                grade = "second Class";
            else
                grade = "Pass Class";
        }
        public override void Display()
        {
            base.Display();
            Console.WriteLine("\n----Mark Details----");
            Console.Write("marks in 5 subjects: ");
            for (int i = 0; i < 5; i++)
                Console.Write(marks[i] + " ");
            Console.WriteLine();
            Console.WriteLine("Total   :" + total);
            Console.WriteLine("Average :" + average);
            Console.WriteLine("Grade   :" + grade);
        }
    }
    class MultiLevel
    {
        public static void Main(string[] agrs)
        {
            MarksDetails Student1 = new MarksDetails("Shreya", 22, "Female", 202090001, "Msc", 5, new int[] { 77, 80, 98, 95, 90 });
            Student1.Display();
        }
    }
}

**OUTPUT**
![image](https://user-images.githubusercontent.com/97940851/154623000-35a144e4-2645-49f7-9978-c2a6fd88d76f.png)





**5.C# program to calculate volumate of 2 boxes and find the recultant volume after addition of 2 boxes by implementing operator overloading**
using System;

namespace ex5
{
    class Box
    {
        float width;
        float height;
        float length;

        public float Volume
        {
            get { return width * height * length; }
        }
        public Box(float width, float height, float length)
        {
            this.width = width;
            this.height = height;
            this.length = height;
        }
        public static float operator +(Box box1, Box box2)
        {
            return box1.Volume + box2.Volume;
        }
        public override string ToString()
        {
            return base.ToString();
            {
                return "box with width" + width + ",height" + height + "and length" + length;
            }
        }
        class OperatorOverloading
        {
            public static void Main()
            {
                Box box1 = new Box(10, 20, 30);
                Box box2 = new Box(25, 32, 15);

                Console.WriteLine("Volume of {0} is:{1}", box1, box1.Volume);
                Console.WriteLine("Volume of {0} is:{1}", box2, box2.Volume);
                Console.WriteLine("Volume after adding boxes:{0}", box1 + box2);
            }
        }
    }
}

**OUTPUT**
![image](https://user-images.githubusercontent.com/97940851/154622907-6f7e5bc1-4872-4fac-a10b-95353d48f475.png)




