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
    
##### 2d vector user define size
      int n = 3; 
      int m = 4; 
      vector<vector<int> > vec( n , vector<int> (m, 0));  
      0 0 0 0 
      0 0 0 0
      0 0 0 0
      
 ##### singel vector user define size
    Create a vector of size n with 
       all values as 10. 
    vector<int> vect(n, 10); 
      

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
    
##### sorting a 2d vector by specific position:
      #include<bits/stdc++.h>
      using namespace std;
      static int cmp(vector<int>&a,vector<int>b)
      {
          return a[2]>b[2];

      }
      int main()
      {
          vector<vector<int>>v= {{1,2,3},{3,4,5},{1,1,6},{4,0,0}};
          sort(v.begin(),v.end(),cmp);
          for(auto i:v)
          {
              for(auto j:i)
                  cout<<j<<" ";
              cout<<endl;
          }
      }

    
  ##### pair in vector
     vector<pair<long,int>>du;
     vector<int>nums={1,2,3,4};
       for(int i=0; i<nums.size(); i++)
       {
           du.push_back(make_pair(nums[i],i));

       }
       
  ##### insert a value into speacific position:
     vector<int>v;
     v.insert(v.begin(),{10}); // for 1 element   v.insert(v.begin(),10)
     cout<<v[0];
     
 ##### remove a element from speacific position of vector
     vector<int> myvector{ 1, 2, 3, 4, 5, 6, 7, 8, 9 };
     myvector.erase(myvector.begin()+2);
     
##### max element in  vector light: 
  *max_element(light.begin(),light.end());
  
  

     
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
##### string to int :
      string a ="1234";
      int x = stoi(a);
      cout<<x;
      
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
            
            
       4. indirect recursion:
         include<bits/stdc++.h>
         using namespace std;
         void funB(int n);
         void funA(int n)
         {
             if( n>0 )
             {
                 cout<<n;
                 funB(n-1);
             }
         }
         void funB(int n)
         {
             if( n>1 )
             {
                 cout<<n;
                 funA(n/2);
             }
         }
         int main()
         {
             funA(20);
         }

OUTPUT : 20,19,9,8,4,3,1
     
      ### Nested recursion:
         #include<bits/stdc++.h>
         using namespace std;
         int fun(int n)
         {
             if(n>100)
                 return n-10;
             return fun(fun(n+11));
         }
         int main()
         {

             cout<<fun(30);
         }

      output:91
      
      ### 
