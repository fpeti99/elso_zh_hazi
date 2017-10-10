namespace HF_ZH_ra
{
    class Program
    {
        static Random rand = new Random();

        static void Main(string[] args)
        {
            int[] szamok;
            szamok = feltolt(10);

            kiir(szamok);

            Console.WriteLine();
            Console.WriteLine("A tömb legkisebb eleme:{0}", minimum(szamok));
            Console.WriteLine("A tömb legnagyobb eleme:{0}", maximum(szamok));

            Console.ReadLine();

        }

        static int[] feltolt(int meret)
        {
            int[] tomb = new int[meret];

            for(int i = 0; i < meret; i++)
            {
                tomb[i] = rand.Next(2,1000);
            }
            return tomb;
        }

        static int maximum (int[] szamok_tomb)
        {
            int max = szamok_tomb[0];

            for(int i = 1; i < szamok_tomb.Length; i++)
            {
                if(max < szamok_tomb[i])
                {
                    max = szamok_tomb[i];
                }
            }

            return max;
        }

        static int minimum (int[] szamok_tomb)
        {
            int min = szamok_tomb[0];

            for(int i = 1; i < szamok_tomb.Length; i++)
            {
                if(min > szamok_tomb[i])
                {
                    min = szamok_tomb[i];
                }
            }

            return min;
        }

        static bool prime (int szam)
        {
            bool prim = true;

            for (int i = 2; i < szam; i++)
            {
                if (szam % i == 0)
                {
                    prim = false;
                    break;
                }
                else
                {
                    if (i == (szam-1))
                    {
                        prim = true;
                    }
                }
            }



            return prim;
        }

        static void kiir (int[] szamok_tomb)
        {
            string prm;

            for (int i = 0; i < szamok_tomb.Length; i++)
            {
                if (prime(szamok_tomb[i]))
                {
                    prm = "prímszám";
                }
                else
                {
                    prm = "nem prímszám.";
                }
                Console.WriteLine("A tömb {0}. eleme: {1} és ez {2}", i + 1, szamok_tomb[i], prm);
            }
        }

    }
}
