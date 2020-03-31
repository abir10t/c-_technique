# Vector
    ## for unique element :
    include<bits/stdc++.h>
    using namespace std;
    int main()
    {
        vector<int>v{2,2,3,4,5,1,1};
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



