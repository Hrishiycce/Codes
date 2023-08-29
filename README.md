#include <bits/stdc++.h>
using namespace std;

//Max sum sub-array of size k
int main(){
    int n;
    cin>>n;
    int a[n];
    for(int i=0; i<n; i++) {
        cin>>a[i];
    }
    int k;
    cin>>k;// size of window
    int ma=INT_MIN,sum=0;
    int i=0,j=0;
    while(j<n){
        sum+=a[j];
        if(j-i+1<k)
            j++;
        else if (j-i+1==k)
        {
            ma=max(ma,sum);
            sum-=a[i];
            i++;
            j++;
        }
    }
    cout<<ma<<endl;

    return 0;
}
