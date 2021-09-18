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
