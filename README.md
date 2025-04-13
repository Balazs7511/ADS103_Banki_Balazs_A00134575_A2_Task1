using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace ADS103_Banki_Balazs_A00134575_A2_Task1
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Stopwatch stopwatch = new Stopwatch();                               // instantiating stopwatch from stopwatch class
            string currentDirectory1 = Directory.GetCurrentDirectory();          // assigning GetCurrentDirectory method to currentDirectory string variable
            string filePath1 = Path.Combine(Directory.GetCurrentDirectory(), "a2_task1_input1.txt"); // combining the current directory with the file name
            string fileContent1 = File.ReadAllText(filePath1);                      // loading file content to string variable
            string[] numbers1 = fileContent1.Split(new char[] { ' ', '\n' },      // assigning filecontent variable to string array 
                StringSplitOptions.RemoveEmptyEntries); 
            int[] array1 = new int[numbers1.Length];                           // creating integer array to hold the value of string numbers array
            for (int i = 0; i < numbers1.Length; i++)                          // using for loop to iterate through integer array and parse string variables into integers
            {
                array1[i] = int.Parse(numbers1[i]); // parsing the string variable to integer
            }
            stopwatch.Start();                                                  // calling start stopwatch method
            Thread.Sleep(10000);                                                // setting the thread to delay by 1000 milliseconds
            insertionSort(array1);                                              // calling insertion sort method on array1
            stopwatch.Stop();                                                   // calling stopwatch stop method
            TimeSpan ts1 = stopwatch.Elapsed;                                   // assigning the elapsed time as variable to hold data 
            string elapsedTime1 = String.Format("{0:00}:{1:00}:{2:00}.{3:00}",   // formating the elapsed time to a string variable
                ts1.Hours, ts1.Minutes, ts1.Seconds, ts1.Milliseconds / 10);
            stopwatch.Reset();                                                  // resetting the stopwatch

            string currentDirectory2 = Directory.GetCurrentDirectory();      // assigning GetCurrentDirectory method to currentDirectory string variable                        
            string filePath2 = Path.Combine(Directory.GetCurrentDirectory(), "a2_task1_input1.txt");
            string fileContent2 = File.ReadAllText(filePath2);                      // loading file content to string variable
            string[] numbers2 = fileContent2.Split(new char[] { ' ', '\n' },              // assigning filecontent variable to string array
                StringSplitOptions.RemoveEmptyEntries);
            int[] array2 = new int[numbers2.Length];                                    // creating integer array to hold the value of string numbers array
            for (int i = 0; i < numbers2.Length; i++)                   // using for loop to iterate through integer array and parse string variables into integers
            {
                array2[i] = int.Parse(numbers2[i]);

            }
            stopwatch.Start();                                                                // calling start stopwatch method
            Thread.Sleep(10000);                                                               // setting the thread to delay by 1000 milliseconds
            mergesort(array2);                                                        // calling merge sort method on array2
            stopwatch.Stop();                                                                 // calling stopwatch stop method
            TimeSpan ts2 = stopwatch.Elapsed;                                         // assigning the elapsed time as variable to hold data 
            string elapsedTime2 = String.Format("{0:00}:{1:00}:{2:00}.{3:00}",              // formating the elapsed time to a string variable
                ts2.Hours, ts2.Minutes, ts2.Seconds, ts2.Milliseconds / 10);
            stopwatch.Reset();                                                                      // resetting the stopwatch
            if (ts1 < ts2)  // if statement to determine the time taken for insertion and merge sort algorithms
            {
                Console.WriteLine($"Insertion sort algorithm took {elapsedTime1} " +        // displaying the time taken 
                    $"time which is less than merge sort {elapsedTime2} for a2_task1_input1.txt");
            }
            else 
            {
                Console.WriteLine($"Merge sort algorithm took {elapsedTime2} " +            // displaying the time taken
                    $"time which is less than insertion sort algorithm {elapsedTime1} for a2_task1_input1.txt");

            }
            string currentDirectory3 = Directory.GetCurrentDirectory();              // assigning GetCurrentDirectory method to currentDirectory string variable
            string filePath3 = Path.Combine(Directory.GetCurrentDirectory(), "a2_task1_input2.txt"); // combining the current directory with the file name
            string fileContent3 = File.ReadAllText(filePath3);                                          // loading file content to string variable
            string[] numbers3 = fileContent3.Split(new char[] { ' ', '\n' },                // assigning filecontent variable to string array
                StringSplitOptions.RemoveEmptyEntries);
            int[] array3 = new int[numbers3.Length];                                // creating integer array to hold the value of string numbers array
            for (int i = 0; i < numbers3.Length; i++)// using for loop to iterate through integer array and parse string variables into integers
            {
                array3[i] = int.Parse(numbers3[i]); // parsing the string variable to integer
            }
            stopwatch.Start();                                                  // calling start stopwatch method
            Thread.Sleep(10000);                                               // setting the thread to delay by 1000 milliseconds                                      
            insertionSort(array3);                                          // calling insertion sort method on array3
            stopwatch.Stop();                                                               // calling stopwatch stop method
            TimeSpan ts3 = stopwatch.Elapsed;
            string elapsedTime3 = String.Format("{0:00}:{1:00}:{2:00}.{3:00}", // formating the elapsed time to a string variable
                ts3.Hours, ts3.Minutes, ts3.Seconds, ts3.Milliseconds / 10);
            stopwatch.Reset();                                                              // resetting the stopwatch
            string currentDirectory4 = Directory.GetCurrentDirectory();      //  assigning GetCurrentDirectory method to currentDirectory string variable
            string filePath4 = Path.Combine(Directory.GetCurrentDirectory(), "a2_task1_input2.txt"); // combining the current directory with the file name
            string fileContent4 = File.ReadAllText(filePath4);                                          // loading file content to string variable
            string[] numbers4 = fileContent4.Split(new char[] { ' ', '\n' },                // assigning filecontent variable to string array
                StringSplitOptions.RemoveEmptyEntries);
            int[] array4 = new int[numbers4.Length];                                    // creating integer array to hold the value of string numbers array
            for (int i = 0; i < numbers4.Length; i++)                 // using for loop to iterate through integer array and parse string variables into integers
            {
                array4[i] = int.Parse(numbers4[i]);                  // parsing the string variable to integer
            }
            stopwatch.Start();                                          // calling start stopwatch method
            Thread.Sleep(10000);                                        // setting the thread to delay by 1000 milliseconds
            mergesort(array4);                                          // calling merge sort method on array4
            stopwatch.Stop();                                           // calling stopwatch stop method
            TimeSpan ts4 = stopwatch.Elapsed;                               // assigning the elapsed time as variable to hold data
            string elapsedTime4 = String.Format("{0:00}:{1:00}:{2:00}.{3:00}",      // formating the elapsed time to a string variable
                ts4.Hours, ts4.Minutes, ts4.Seconds, ts4.Milliseconds / 10);
            stopwatch.Reset();                                                      // resetting the stopwatch
            if (ts3 < ts4)  // if statement to determine the time taken for insertion and merge sort algorithms
            {
                Console.WriteLine($"Insertion sort algorithm took {elapsedTime3} time which is less than merge sort {elapsedTime4} for a2_task1_input2.txt");
            }
            else 
            {
                Console.WriteLine($"Merge sort algorithm took {elapsedTime4} time which is less than insertion sort algorithm {elapsedTime3} for a2_task1_input2.txt");

            }

        }

        static void insertionSort(int[] array)          // method to perform insertion sort
        {
            for (int i = 1; i < array.Length; i++)      // for loop to iterate through the array
            {
                int temp = array[i];                    // assigning the value of the array to a temporary variable
                int j = i - 1;                          // index of the previous element
                while (j >= 0 && array[j] > temp)       // check if the previous element is greater than the current element
                {
                    array[j + 1] = array[j];            // shifting the elements to the right
                    j--;                                // decrementing the index
                }
                array[ j + 1 ] = temp;                  // inserting the current element in the correct position
            }
        }
        static void mergesort(int[] array)              // method to perform merge sort, dividing the array into two halves and sorting them recursively
        { 
            int length = array.Length;                  // assigning the length of the array to a variable
            if (length <= 1) return;                    // if the length of the array is less than or equal to 1, return, base case        

            int middle = length / 2;                        // finding the middle index of the array
            int[] leftarray = new int[middle];              // creating a left array of the first half of the array
            int[] rightarray = new int[length - middle];    // creating a right array of the second half of the array

            int i = 0;                                      // left array
            int j = 0;                                      // right array

            for (; i < length; i++)
            {                                               // for loop to iterate through the array
                if (i < middle)                             // if the index is less than the middle index
                {
                    leftarray[i] = array[i];                // assigning the value of the array to the left array

                }
                else
                {
                    rightarray[j] = array[i];                // assigning the value of the array to the right array
                    j++;
                }
            }
            mergesort(leftarray);                           // recursive call to the left array
            mergesort(rightarray);                          // recursive call to the right array
            merge(leftarray, rightarray, array);            // merging the two arrays
        }
        static void merge(int[] leftarray, int[] rightarray, int[] array)       // method to merge the two arrays
        {
            int leftsize = array.Length / 2;                                    // assigning the left size of the array
            int rightsize = array.Length - leftsize;                            // assigning the right size of the array
            int i = 0, l = 0, r = 0;                                            // assigning the index of the left and right arrays
            // check the condition for merging
            while (l < leftsize && r < rightsize)                               // loop to iterate through the left and right arrays
            {
                if (leftarray[l] < rightarray[r])                               // if the left array is less than the right array
                {
                    array[i] = leftarray[l];                                    // assigning the value of the left array to the merged array
                    i++;                                                        // incrementing the index
                    l++;                                                        // incrementing the left index
                }
                else                                                            // if the right array is less than the left array
                {
                    array[i] = rightarray[r];                                   // assigning the value of the right array to the merged array
                    i++;                                                        // incrementing the index
                    r++;                                                        // incrementing the right index
                }

            }
            while (l < leftsize)                                                // loop to iterate through the left array
            {
                array[i] = leftarray[l];                                        // assigning the value of the left array to the merged array
                i++;                                                            // incrementing the index
                l++;                                                            // incrementing the left index
            }
            while (r < rightsize)                                               // loop to iterate through the right array
            {
                array[i] = rightarray[r];                                       // assigning the value of the right array to the merged array
                i++;                                                            // incrementing the index
                r++;                                                            // incrementing the right index
            }
        }
    }
}
      
