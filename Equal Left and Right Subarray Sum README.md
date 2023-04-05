# GFG-DAILY-PROBLEM



class Solution {
  public:
    int equalSum(int N, vector<int> &A) {
        // code here
        int sum = 0;
        int total = 0;
        for(int i=0;i<A.size();i++){
            total += A[i];
        }
        for(int i=0;i<A.size();i++){
            total -= A[i];
            if(sum==total){
                return i+1;
            }
            sum += A[i];
        }
        return -1;
    }
};



BY:Abhay Gupta
