### Recursion

In Recursion, the solution to a larger problem is defined in terms of smaller instances of itself.
* Recursion will always have a terminating condition. Else it'll be an infinite recursion.
* Recursive function performs some part of the task and delegates rest to the recursive call.

        E.g Compute sum of first N Positive numbers. (Java)
        
        public static int firstNSum(int n){
            if(n <= 0 ){
                // throw exception..
            }
            if(n == 1){
                return 1;
            }
            return n + firstNSum(n-1);
        }
        
         
         