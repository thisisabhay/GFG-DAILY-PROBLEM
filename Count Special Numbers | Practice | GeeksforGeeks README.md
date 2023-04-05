# GFG-DAILY-PROBLEM



class Solution {
  public:
  vector<int>f(int x)
  {
      vector<int>v;
      v.push_back(1);
      for(int i=2;i<=sqrt(x);i++)
      {
          if(x%i==0)
          {
              if(x/i==i)
              v.push_back(i);
              else
              {
                  v.push_back(i);
                  v.push_back(x/i);
              }
          }
      }
      return v;
  }
    int countSpecialNumbers(int N, vector<int> arr) {
        // Code here
        int ans=0;
        map<int,int>mp;
        for(auto it:arr)
        {
            mp[it]++;
        }
        map<int,int>mp1;
        for(auto it:mp)
        {
            if(it.second>1)
            {
                ans+=it.second;
                mp[it.first]=1;
                mp1[it.first]=1;
            }
            else
            {
                mp1[it.first]=0;
            }
        }
        
        for(auto it:mp)
        {
            vector<int>curr=f(it.first);
            if(mp1[it.first]==0)
            {for(int i=0;i<curr.size();i++)
            {
                if(mp[curr[i]]>0&&curr[i]!=it.first)
                {
                    ans++;
                    break;
                }
            }}
        }
        
        return ans;
        
    }
};




BY:Abhay Gupta
