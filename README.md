# Prize-Drawing-Program
A small prize drawing program which can be used with small group of people, enter the name and the number and the computer will randomly pick a winner

using System;
using System.Collections.Generic;

namespace ConsoleApp7
{
    class Program
    {
        class Person
        {
            string Name { get; set; }
            int Number { get; set; }

            public Person(string name, int number)
            {
                this.Name = name;
                this.Number = number;
            }

            public override string ToString()
            {
                return "The winner is " + Name +" and the number is "+Number.ToString();
            }
        }

        static void Main(string[] args)
        {
          
            
            Console.WriteLine("How many persons?");
            int numOfPersons = int.Parse(Console.ReadLine());

            List<Person> list = new List<Person>(numOfPersons);

            for (int i = 0; i < numOfPersons; i++)
            {
                Console.Write("Enter the name: ");
                string name = Console.ReadLine();

                Console.Write("Enter the number: ");
                int number = int.Parse(Console.ReadLine());

                var person1 = new Person(name, number);

                list.Add(person1);
            }


            Random rnd = new Random();
            int luckyNum = rnd.Next(0, numOfPersons);


            double winningRate = (double)1 / (double)numOfPersons;


            Console.WriteLine(list[luckyNum].ToString());

            Console.WriteLine("The winning rate is " + winningRate);

        }
    }
}
