# Vector
   ## for unique element :
    include<bits/stdc++.h>
    using namespace std;
    int main()
    {  vector<int>v{2,2,3,4,5,1,1};
        vector<int>::iterator p;
        p = unique(v.begin(), v.end(), [](int a, int b)
        {
            return a == b;
        });
        
        v.resize(distance(v.begin(), p));
        // resizing vector to make size equal to total different number
        
    for_each(v.begin(),v.end(),[](int i){
    cout<<i<<endl;
    });
    return 0;
    }
Link:https://www.geeksforgeeks.org/lambda-expression-in-c/

## Sorting a 2d vector
      
    vector<vector<int>>n{{6,8,2},{9,1,0},{2,4,1},{4,7,9}};
    sort(n.begin(),n.end());
    for(int i=0; i<n.size(); i++)
    {
        for(int j=0; j<n[i].size(); j++)
        {
        cout<<n[i][j]<<" ";
        }
        cout<<endl;
    }
# unordered_map:
      unordered_map<string, int> umap; 
        umap["GeeksforGeeks"] = 10; 
        umap["Practice"] = 20; 
        umap["Contribute"] = 30; 
      for (auto x : umap) 
      cout << x.first << " " << x.second << endl; 
      
### access from vector
      vector<int>nums{4,1,2,1,2};
      unordered_map<int,int>u;
         for(auto i:nums)
            u[i]++;
         
      for(auto i: u)
       cout<<i.second<<endl;
    
      link:https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/
