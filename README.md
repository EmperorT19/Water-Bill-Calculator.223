# Water-Bill-Calculator.223
using System;

namespace waterbillcalculator
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(@"-----------------------------------------------
 Welcome to the Monthly Water Bill Calculator!
-----------------------------------------------");
            bool isRunning = true;
            while (isRunning)
            {
                try
                {
                    Console.WriteLine();
                    // Input water consumption
                    Console.Write("Please enter the water consumption in m^3: ");
                    double waterConsumption = double.Parse(Console.ReadLine());

                    // Input usage type
                    Console.WriteLine("Please enter the usage type(i.e 1, 2 or 3):");
                    Console.WriteLine("1. Residential.");
                    Console.WriteLine("2. Commercial.");
                    Console.WriteLine("3. Industrial.");

                    Console.Write("Select choice: ");
                    int usageType = int.Parse(Console.ReadLine());
                    string usage = "residential";
                    double Rate = 0;

                    // Determine rate based on usage type
                    if (usageType == 1)
                    {
                        Rate = 25.00;
                        usage = "residential";
                    }
                    else if (usageType == 2)
                    {
                        Rate = 30.50;
                        usage = "commercial";
                    }
                    else if (usageType == 3)
                    {
                        Rate = 35.75;
                        usage = "industrial";
                    }

                    // Calculate total bill and display breakdown
                    double totalBill = waterConsumption * Rate;
                    Console.WriteLine($"Breakdown for {usage} usage:");
                    Console.WriteLine($"Water Consumption: {waterConsumption} m^3");
                    Console.WriteLine($"Rate: {Rate} KES/m^3");
                    Console.WriteLine($"Total Bill: {totalBill} KES");
                    Console.WriteLine("Press enter to exit.");
                }
                catch
                {
                    Console.WriteLine("Wrong input. Try again");
                    continue;
                }
                Console.ReadKey();
                isRunning = false;
            }
        }
    }
}
