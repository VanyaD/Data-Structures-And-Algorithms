## Data Structures, Algorithms and Complexity Homework

1. **What is the expected running time of the following C# code?**
  - Explain why using Markdown.
  - Assume the array's size is `n`.

  ```cs
  long Compute(int[] arr)
  {
      long count = 0;
      for (int i=0; i<arr.Length; i++)
      {
          int start = 0, end = arr.Length-1;
          while (start < end)
              if (arr[start] < arr[end])
                  { start++; count++; }
              else 
                  end--;
      }
      return count;
  }
  
  Expected running time: The expected running time of the C# code above is O(n^2)
  Explanation: The outer loop will be traversed n times and for each of its iterations, 
  the inner loop will be traversed another n times. The other operations (such as incrementing 
  and decrementing variables have constant level of complexity, thus, can be omitted)
  
2. **What is the expected running time of the following C# code?**
  - Explain why using Markdown.
  - Assume the input matrix has size of `n * m`.

  ```cs
  long CalcCount(int[,] matrix)
  {
      long count = 0;
      for (int row=0; row<matrix.GetLength(0); row++)
          if (matrix[row, 0] % 2 == 0)
              for (int col=0; col<matrix.GetLength(1); col++)
                  if (matrix[row,col] > 0)
                      count++;
      return count;
  }
  
  Expected running time: The expected running time of the C# code above is O(n*m).
  Explanation: The outer loop will be traversed n times and for some of its iterations 
  the inner loop will be traversed m times. Since the exact number of times of the inner 
  loop will be invoked is constant, it can be ignored when calculating the final running time.

3. **(*) What is the expected running time of the following C# code?**
  - Explain why using Markdown.
  - Assume the input matrix has size of `n * m`.

  ```cs
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

  Expected running time: The expected running time of the C# code above is O(n*m).
  Explanation: The for-loop will be executed n times while the method itself -> m times. 
  The resulting running time is O(n*m).
