# GFG-DAILY-PROBLEM


int minSteps(string str) {
    // Write your code here.
        int count=1;
    int n=str.size();
    int last=str[0];
    for(int i=1;i<n;i++){
        if(str[i]!=last){
            last=str[i];
            count++;
        }
    }
    return count/2 +1;
}



BY:Abhay Gupta
