# helloworld
计算器重构
using System;

namespace 字符串的加减
{
    class Program
    {
        static void Main(string[] args)
        {
            Caculate c = new Caculate();
            string str = "";
            string result = "";
            Console.WriteLine("请输入第一个参数");
            c.x = Console.ReadLine();
            str = c.x;
            result = System.Text.RegularExpressions.Regex.Replace(str, @"[0-9]+", "");
            if (string.IsNullOrEmpty(result))
            {
                c.a = Convert.ToInt32(str);
                Console.WriteLine("请输入符号");
                c.c = char.Parse(Console.ReadLine());
                Console.WriteLine("请输入第二个参数");
                c.z = Console.ReadLine();
                str = c.z;
                for (int i = 0; i < str.Length; i++)
                {
                    result = System.Text.RegularExpressions.Regex.Replace(str, @"[0-9]", " ");

                }
                if (!string.IsNullOrEmpty(result))
                {

                    c.b = Convert.ToInt32(str);
                    Console.WriteLine("计算结果是{0}", c.Cac(c.a, c.b));
                }
                else
                {
                    Console.WriteLine("计算结果是{0}", c.Cac(ref c.x, ref c.z));
                }

            }
            else
            {
                Console.WriteLine("请输入符号");
                c.c = char.Parse(Console.ReadLine());
                Console.WriteLine("请输入第二个参数");
                c.z = Console.ReadLine();
                Console.WriteLine("计算结果是{0}", c.Cac(ref c.x, ref c.z));
            }
        }
      
        class Caculate
        {
            public int a, b;
            public string x, z;

            public char c;
            public int Cac(int d, int e)
            {
                if (c == '+')
                {
                    return a + b;
                }
                else
                {
                    return a - b;
                }
            }
            public  string Cac(ref string d,ref string e)
            {
                if (c == '+')
                {
                    return x + z;
                }
                else
                    return x.Replace(z, " ");
            }                       
        }
    }
}
