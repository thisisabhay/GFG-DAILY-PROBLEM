# GFG-DAILY-PROBLEM


class Solution {
  public:
    long long int minOperations(int N) {
        long long x=(N*1LL)/2;
        if(N&1){
            return x*(x+1);
        }
        else{
            return x*x;
        }
        return 0;
    }
};
