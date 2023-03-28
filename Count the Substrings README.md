class Solution
{
    public:
    int countSubstring(string S)
    {
        int n=S.size();
        int cnt=0;
        int cap[n],low[n];
        cap[0]=(S[0]>='A'&&S[0]<='Z');
        low[0]=(S[0]>='a'&&S[0]<='z');
        for(int i=1;i<n;i++){
            cap[i]=cap[i-1]+(S[i]>='A'&&S[i]<='Z');
            low[i]=low[i-1]+(S[i]>='a'&&S[i]<='z');
        }
        for(int i=0;i<S.size()-1;i++){
            for(int j=i+1;j<S.size();j++){
                if(i==0){
                    if(cap[j]==low[j]){
                        cnt++;
                    }
                }
                if(i>0){
                    if(cap[j]-cap[i-1]==low[j]-low[i-1]){
                        cnt++;
                    }
                }
            }
        }
        return cnt;
    }
};


BY:Abhay Gupta
