 BÁO CÁO TEST WHITEBOX ROD CUTTING 
 
+) Link Github: https://github.com/TheAlgorithms/Java/blob/master/Dynamic%20Programming/RodCutting.java

+) Source code   
    
    private static int cutRod(int[] price, int n) {
        int val[] = new int[n + 1];
        val[0] = 0;

        for (int i = 1; i <= n; i++) {
            int max_val = Integer.MIN_VALUE;
            for (int j = 0; j < i; j++)
                max_val = Math.max(max_val, price[j] + val[i - j - 1]);

            val[i] = max_val;
        }

        return val[n];
    }
    
Liệt kê đường đi:
  + Path 1: 1 - 2 - 3 - 8
  + Path 2: 1 - 2 - 3 - 4 - 5 - 7 - 3 - 8
  + Path 3: 1 - 2 - 3 - 4 - 5 - 6 - 5 - 7 - 3 - 8
  + Path 4: 1 - 2 - 3 - 4 - 5 - 7 - 3 - 4 - 5 - 7 - 3 - 8
  + Path 5: 1 - 2 - 3 - 4 - 5 - 6 - 5 - 7 - 3 - 4 - 5 - 7 - 3 - 8
  + Path 6: 1 - 2 - 3 - 4 - 5 - 6 - 5 - 7 - 3 - 4 - 5 - 6 - 5 - 7 - 3 - 8
  
Phương trình đường đi
  + Path 1: 1 - 2 - 3=FALSE - 8
  + Path 2: 1 - 2 - 3=TRUE - 4 - 5=FALSE - 7 - 3=FALSE - 8
  + Path 3: 1 - 2 - 3=TRUE - 4 - 5=TRUE - 6 - 5=FALSE - 7 - 3=FALSE - 8
  + Path 4: 1 - 2 - 3=TRUE - 4 - 5=FALSE - 7 - 3=TRUE - 4 - 5=FALSE - 7 - 3=FALSE - 8
  + Path 5: 1 - 2 - 3=TRUE - 4 - 5=TRUE - 6 - 5=FALSE - 7 - 3=TRUE - 4 - 5=FALSE - 7 - 3=FALSE - 8
  + Path 6: 1 - 2 - 3=TRUE - 4 - 5=TRUE - 6 - 5=FALSE - 7 - 3=TRUE - 4 - 5=TRUE - 6 - 5=FALSE - 7 - 3=FALSE - 8
