# chudnovsky-csharp
Chudnovsky's algorithm to calculate Pi using C#

public static int Factorial(int f)
        {
            if (f == 0)
                return 1;
            else
                return f * Factorial(f - 1);
        }//need to improve this factorial function a lot

        public static void Chudnovsky()
        {
            double S = 0;

            int iter = 100; // greater iteration produce better approximation of Pi
            int k; // iteration k

            // constant value
            const double k1 = 545140134, k2 = 13591409, k3 = -640320;
            const double k4 = 426880, k5 = 10005;

            Console.WriteLine("\nPi Approximation : \n\n");

            for (k = 0; k <= iter - 1; k++)
            {
                double numerator = Factorial(6 * k) * (k1 * k + k2);
                double denominator = Factorial(3 * k) * Math.Pow(Factorial(k), 3) * Math.Pow(k3, 3 * k);

                S += numerator / denominator;

                double Pi = (k4 * Math.Sqrt(k5)) / S;
                Console.WriteLine("k = {0} : {1}\n", k + 1, Pi);
            }
        }
