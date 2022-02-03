# codes
int Solution::threeSumClosest(vector<int> &A, int B) {
    int sum=0;
    int min_diff=INT_MAX;
    int p;
    sort(A.begin(),A.end());
    for(int i=0;i<A.size()-2;i++){
        int l=i+1;
        int r=A.size()-1;
        while(l<r){
            sum=(A[i]+A[l]+A[r]);
            if((sum-B)==0)
             return sum;
            else if(sum>B){
                r--;
            }
            else{
                l++;
            }
            if((sum-B)<min_diff) {
                min_diff=abs(sum-B);
                p=sum;
            }
        }
    }
    return p;
}
                                 
  // Anagrams code
                                 
ector<vector<int> > Solution::anagrams(const vector<string> &A) {
    vector<vector<int>> v;
    int n=A.size();
    vector<string> p=A;
   unordered_map<string,vector<int>> mp;
    for(int i=0;i<n;i++){
         sort(p[i].begin(),p[i].end());
         mp[p[i]].push_back(i+1);
    }
    for(auto x:mp){
        v.push_back(x.second);
    }
    return v;
    
}
