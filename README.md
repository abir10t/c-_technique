# Vector
   ##### for unique element :
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
##### declearing a 2d vector 
    vector<vector<int>>m;
    int n;
    for(int i=1; i<=3; i++)
    {
        vector<int>temp;
        for(int j=0; j<=3; j++)
        {

            cin>>n;
            temp.push_back(n);
        }
        m.push_back(temp);
    }
    

##### Sorting a 2d vector
      
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
    
  ##### pair in vector
     vector<pair<long,int>>du;
     vector<int>nums={1,2,3,4};
       for(int i=0; i<nums.size(); i++)
       {
           du.push_back(make_pair(nums[i],i));

       }
  ##### ........................................... --------- ............................................................................................................................
# unordered_map:
      unordered_map<string, int> umap; 
        umap["GeeksforGeeks"] = 10; 
        umap["Practice"] = 20; 
        umap["Contribute"] = 30; 
      for (auto x : umap) 
      cout << x.first << " " << x.second << endl; 
      
##### access from vector
      vector<int>nums{4,1,2,1,2};
      unordered_map<int,int>u;
         for(auto i:nums)
            u[i]++;
         
      for(auto i: u)
       cout<<i.second<<endl;
    
      link:https://www.geeksforgeeks.org/unordered_map-in-cpp-stl/
      
 ##### Map of Vectors 
 
       https://www.geeksforgeeks.org/map-of-vectors-in-c-stl-with-examples/
       ##### initialize :
         unordered_map<int,vector<int>>mp;
         mp[0].push_back(0);
         
      ##### iteration :
     vector<int>v= {1,2,3};
    unordered_map<int,vector<int>>mp;
    
    for(auto i:v)
        mp[i].push_back(i);

    for(int i=0; i<mp.size(); i++)
      for(int j=0; j<mp[i].size(); j++)
              cout<<mp[i][j]<<" ";
     
    ##### sort ->
      sort(mp[i].begin(),mp[i].end());
         
 
 
 

 ##### ........................................... --------- ............................................................................................................................
  
 # map
 
      vector<string>strs{"eat", "tea", "tan", "ate", "nat", "bat"};
      map<string,vector<string>>mp;
      for(auto i: strs)
      {
        mp[i].push_back(i);
      }
   
      vector<vector<string>>s;
      vector<string>ab;
    
      for(auto i: mp)  //for(auto i: mp) s.push_back(i.second); only push_back can be use by this way.
      {
         for(auto j:i.second)
         {
            ab.push_back(j);
         }
        s.push_back(ab);
    }
    
##### ........................................... --------- ............................................................................................................................
# multimap

    multimap<int,int>mp;
       mp.insert(make_pair(1,0)); //we cant' use mp[1]=0;
       mp.insert(make_pair(1,1));







    
  ##### ........................................... --------- ............................................................................................................................
  # set 
  
  ##### a value in set or not
    set<int>s{1,2,3,4}
    if(s.count(4) ==1)
      print("found")     
 ##### ........................................... --------- ............................................................................................................................
    
# string 
##### erase a particular char from string
      string s="abcd";
      s.erase(s.begin()+2); //abd
      print("found")
      
 ##### ........................................... --------- ............................................................................................................................
 
 
 # recursion
   ### variable bs static variable:
   
      #include<bits/stdc++.h>
      using namespace std;
      int fun(int n)
      {

          if(n>0)
              return fun(n-1)+n;
      }
      int main()
      {
          int a=5;
          cout<<fun(a);
      }
      
### static variable:
      #include<bits/stdc++.h>
      using namespace std;
      int fun(int n)
      {
          static int x=0;
          if(n>0)
          {
                x++;
              return fun(n-1)+x;
          }
      }
      int main()
      {

          int a=5;
          cout<<fun(a);
      }
here, static int x=0, creadted once,it's created loding time.and +x works returning time.so result of the function is 25.if x is global, than it also work same.

### Types of recursion
    1. Tail recursion :
       void fun(int n)
       {
         if(n>0)
         {
           cout<<n;
           fun(n-1)
         }
       }
  recursive call and the call is the last statement.
  
      2. Head recursion:
      void fun(int n)
       {
         if(n>0)
         {
           
           fun(n-1)
           cout<<n;
         }
       }
     all things are below in recursive call.nothing can be avobe.
     
     3. Tree recursion:
      #include<bits/stdc++.h>
      using namespace std;
      void fun(int n)
      {
          if(n>0)
          {
              cout<<n;
              fun(n-1);
              fun(n-1);
          }
      }
      int main()
      {
          fun(3);
      }
      output : 3211211
