using System;
using System.Collections.Generic;
using System.Collections;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApplication31
{
    class Program
    {
        static void Main(string[] args)
        {
            Hashtable table = new Hashtable();
            DictionaryEntry[] arr = new DictionaryEntry[10];
            bool Menu = true;
            do
            {
                foreach (DictionaryEntry de in table)
                {
                    Console.WriteLine("Key = {0}, Value = {1}", de.Key, de.Value);
                }
                Console.WriteLine();
                Console.ForegroundColor = ConsoleColor.Green;
                Console.WriteLine("[1] - Add");
                Console.WriteLine();
                Console.WriteLine("[2] - Remove");
                Console.WriteLine();
                Console.WriteLine("[3] - Clone");
                Console.WriteLine();
                Console.WriteLine("[4] - Clear");
                Console.WriteLine();
                Console.WriteLine("[5] - CopyTo");
                Console.WriteLine();
                Console.WriteLine("[6] - Keys");
                Console.WriteLine();
                Console.WriteLine("[7] - Values");
                Console.WriteLine();
                Console.WriteLine("[8] - Count");
                Console.WriteLine();
                Console.WriteLine("[9] - IsFixedSize");
                Console.WriteLine();
                Console.WriteLine("[10] - IsReadOnly");
                Console.WriteLine();
                Console.WriteLine("[11] - ContainsKey");
                Console.WriteLine();
                Console.WriteLine("[0] - Выход из программы");
                Console.WriteLine();
                int d = Convert.ToInt32(Console.ReadLine());
                Console.Clear();
                switch (d)
                {
                    case 1:
                        Console.WriteLine("Введите ключ:");
                        string n = Console.ReadLine();
                        Console.WriteLine("Введите значение:");
                        string h = Console.ReadLine();
                        table.Add(n, h);

                        break;
                    case 2:
                        Console.WriteLine("Введите ключ который нужно удалить");
                        string j = Console.ReadLine();
                        table.Remove(j);
                        break;
                    case 3:
                        table.Clone();


                        Console.ReadKey();
                        break;
                    case 4:
                        table.Clear();
                        Console.ReadKey();
                        break;
                    case 5:
                        table.CopyTo(arr, 3);
                        for (int i = 0; i < 10; i++)
                        {
                            Console.WriteLine(arr[i]);
                        }
                        Console.ReadKey();
                        break;
                    case 6:
                        ICollection g = table.Keys;
                        foreach (string s in g)
                        {
                            Console.WriteLine(s);
                        }

                        Console.ReadKey();
                        break;
                    case 7:
                        ICollection b = table.Values;
                        foreach (string s in b)
                        {
                            Console.WriteLine(s);
                        }
                        Console.ReadKey();
                        break;
                    case 8:
                        Console.WriteLine("Количевство пар: " + table.Count);
                        Console.ReadKey();
                        break;
                    case 9:
                        Console.WriteLine(table.IsFixedSize);
                        Console.ReadKey();
                        break;
                    case 10:
                        Console.WriteLine(table.IsReadOnly);
                        Console.ReadKey();
                        break;
                    case 11:
                        Console.WriteLine("Введите ключ");
                        string k = Console.ReadLine();
                        Console.WriteLine(table.ContainsKey(k));
                        Console.ReadKey();
                        break;
                    case 0:
                        Menu = false;
                        break;
                }
                Console.Clear();
            }
            while (Menu);
        }
    }
}

