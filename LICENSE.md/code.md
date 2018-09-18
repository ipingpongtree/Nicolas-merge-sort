using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace algorithm
{
    class Program
    {
        static void Main(string[] args)
        { MergeSort(); }
        static void SelectiveSort()
        {
            int[] x = { 8, 5, 4, 7, 6, 1, 10, 2, 9, 3 };

            int min;
            int minTemIndex = 0;
            bool swap = false;
            min = x[0];
            for (int i = 0; i < x.Length; i++) {
                min = x[i];
                swap = false;
                for (int j = i + 1; j < x.Length; j++)
                {
                    if (min > x[j]) {
                        min = x[j];
                        minTemIndex = j;
                        swap = true;
                    }

                }
                if (swap == true)
                {
                    x[minTemIndex] = x[i];
                    x[i] = min;
                }
            }
            for (int z = 0; z < x.Length; z++)
            {
                Console.WriteLine(x[z]);
            }
            Console.ReadLine();
        }
        static void MergeSort()
        {
            int[] leftArray = new int[] { 1, 3, 5, 6 };
            int[] rightArray = new int[] { 2, 4, 7, 8 };
            int[] sortedArray = new int[] { leftArray.Length, rightArray.Length };
            int li = 0;
            int ri = 0;
            for (int i = 0; i < 9; i++) {
                if (leftArray[li] > rightArray[ri])
                {
                    sortedArray[i] = rightArray[ri];
                    ri++;
                }
                if (rightArray[ri] > leftArray[li])
                {
                    sortedArray[i] = leftArray[li];
                    li++;
                }
            }
            for(int i=0; i<9; i++)
            {
                Console.WriteLine(sortedArray[i]);
                Console.ReadLine();
            }
        }
    }
}
