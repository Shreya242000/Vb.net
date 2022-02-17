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



****
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



