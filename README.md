/*Задание 1. Написать программу, которая считывает символы с клавиатуры, пока не 
будет введена точка. Программа должна сосчитать количество введенных 
пользователем пробелов.
 */
using System;

namespace Lesson
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter the characters:");
            char ch;
            int cnt=0;
            do
            {
                ch=Convert.ToChar(Console.Read());
                if (ch == ' ')  cnt++;
            } while (ch!='.');
            Console.WriteLine("You enter dot");
            Console.WriteLine($"Probils = {cnt}");
        }
    }
}
______________________________________________________________________________________
*Задание 2. Ввести с клавиатуры номер трамвайного билета (6-значное число) и
проверить является ли данный билет счастливым (если на билете напечатано 
шестизначное число, и сумма первых трёх цифр равна сумме последних трёх, то 
этот билет считается счастливым).
 */
using System;

namespace Lesson
{
    class Program
    {
        static void Main(string[] args)
        {
            int num,sum1=0,sum2=0,cnt=0;
            int[] arr = new int[6];
            Console.WriteLine("Enter the tram ticket number (6 digits)");
            try
            {
                string s = Console.ReadLine();
                num = Convert.ToInt32(s);
                for (int i = 0; i < 6; i++)
                {
                    arr[i] = num % 10;
                    num /= 10;
                    if (i < 3) sum1 += arr[i];
                    if (i >= 3) sum2 += arr[i];
                }
                if (s.Length != 6) { Console.WriteLine("You must enter 6 digits!!!"); }
                else if (sum1 == sum2) { Console.WriteLine("Congratulations! Your ticket is happy."); }
                else { Console.WriteLine("Your ticket is not happy."); }
            }
            catch (Exception)
            {
                Console.WriteLine("Error!!!You must enter digits!!!"); ;
            }           
        }
    }
}
______________________________________________________________________________________
/*Задание 3. Числовые значения символов нижнего регистра в коде ASCII
отличаются от значений символов верхнего регистра на величину 32. Используя эту 
информацию, написать программу, которая считывает с клавиатуры и конвертирует 
все символы нижнего регистра в символы верхнего регистра и наоборот.
 */
using System;

namespace Lesson
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter your string:");
            string str = Console.ReadLine();
            char[] ch = new char[str.Length];
            ch=str.ToCharArray();
            for (int i = 0; i < str.Length; i++)
            {
                for (int j = 65; j <= 90; j++)
                {
                    if (ch[i] == ((char)j)) ch[i] = ((char)(j + 32));
                    else if (ch[i] == ((char)(j+32))) ch[i] = (char)j;
                }
            }
            Console.WriteLine(ch);
            Console.WriteLine();
        }
    }
}
______________________________________________________________________________________
/*Задание 4. Даны целые положительные числа A и B (A < B). Вывести все целые
числа от A до B включительно; каждое число должно выводиться на новой строке;
при этом каждое число должно выводиться количество раз, равное его значению. 
Например: если А = 3, а В = 7, то программа должна сформировать в консоли 
следующий вывод:
       3 3 3
       4 4 4 4
       5 5 5 5 5
       6 6 6 6 6 6
       7 7 7 7 7 7 7
 */
using System;

namespace Lesson
{
    class Program
    {
        static void Main(string[] args)
        {
            int a, b;
            Console.WriteLine("Enter the value of A:");
            bool res1 = int.TryParse(Console.ReadLine(), out a);
            Console.WriteLine("Enter the value of B:");
            bool res2 = int.TryParse(Console.ReadLine(), out b);
            if (res1 && res2 )
            {
                int size = (b - a) + 1;
                int[][] arr = new int[size][];
                for (int i = 0; i < size; i++)
                {
                    arr[i] = new int[a];
                    for (int j = 0; j < a; j++)
                    {
                        arr[i][j] = a;
                    }
                    a++;
                }
                for (int i = 0; i < arr.Length; i++)
                {
                    for (int j = 0; j < arr[i].Length; j++)
                    {
                        Console.Write(" " + arr[i][j]);
                    }
                    Console.WriteLine();
                }
            }
            else { Console.WriteLine("ERROR!!! You need to enter value."); }
        }
    }
}
______________________________________________________________________________________
/*Задание 5. Дано целое число N (> 0), найти число, полученное при прочтении 
числа N справа налево. Например, если было введено число 345, то программа
должна вывести число 543.
 */
using System;

namespace Lesson
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter the value of N (>0):");
            int num;
            string str = Console.ReadLine();
            int size = str.Length;
            bool res = int.TryParse(str, out num);
            if(res==true && num > 0)
            {
                int[] arr = new int[size];
                int i = 0;
                while (i<size)
                {
                    arr[i++] = num % 10;
                    num /= 10;
                }
                foreach (var item in arr)
                {
                    Console.Write(item);
                }
                Console.WriteLine();
            }
            else { Console.WriteLine("ERROR!!! You need to enter the value and value need > 0."); }
        }
    }
}
______________________________________________________________________________________
