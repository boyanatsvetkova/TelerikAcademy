1. What is the expected running time of the following C# code?


        long Compute(int[] arr)
        {
            long count = 0;
            for (int i = 0; i < arr.Length; i++)
            {
                int start = 0, end = arr.Length - 1;
                while (start < end)
                    if (arr[start] < arr[end])
                    { start++; count++; }
                    else
                        end--;
            }
            return count;
        }

The expected running time of the following code is **O(n^2)** because the first for loop interates over all of the elements of the array, i.e. the size of the array - 'n'. At the same time the inner while loop once again iterates over the elements of the array as the start variable starts always from 0 and end variable starts always from the size of the array minus one and they increase or decrease with every iteration.

***

2. What is the expected running time of the following C# code?
Assume the input matrix has size of n * m.

        long CalcCount(int[,] matrix)
        {
            long count = 0;
            for (int row = 0; row < matrix.GetLength(0); row++)
            {
                if (matrix[row, 0] % 2 == 0)
                {
                    for (int col = 0; col < matrix.GetLength(1); col++)
                    {
                        if (matrix[row, col] > 0)
                        {
                            count++;
                        }
                    }
                }
            }

            return count;
        }

The expected running time of the following code is **O(n * m)** - the for for loop will lways iterates through the whole row elements of the matrix whereas in the worst case if all first elements in every row are even the second for loop will be executed and will iterate over the columns of the matrix.

***

3. (*) What is the expected running time of the following C# code?

Assume the input matrix has size of n * m.

        long CalcSum(int[,] matrix, int row)
        {
            long sum = 0;
            for (int col = 0; col < matrix.GetLength(0); col++)
                sum += matrix[row, col];
            if (row + 1 < matrix.GetLength(1))
                sum += CalcSum(matrix, row + 1);
            return sum;
        }

Console.WriteLine(CalcSum(matrix, 0));

The expecting running time of the code in the worst case is **O(n * m)**. The outer loop will always iterate over the size of the matrix n and at the same time the if condition will always be true as long as row + 1 < matrix.GetLength(1) (size of the matrix m)
