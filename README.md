# Finding-occurences-in-array
To find the first and last occorence in the array

#include<iostream>
using namespace std;
int first_occ(int arr[],int size, int var)
{
    int ans=-1;
    int e=size-1,s=0;

    int m=(s+e)/2;
    while(s<=e)
    {
    if( arr[m] ==var)
    {
        ans=m;
        e=m-1;
    }
    else if(var<arr[m])
    {
        e=m-1;
    }
    else if(var>arr[m])
    {
        s=m+1;
    }
    m=s+(e-s)/2;
    }
    return ans;
}
int main()
{
    int array1[4]={1,1,2,3};
    int arr[7]={1,2,3,4,5,5,6};
    int arr1[6]={1,2,3,4,4,5};
    cout<<"First occourence of 1 is at index "<<first_occ(array1,4,2)<<endl;
    cout<<"First occourence of 2 is at index "<<first_occ(arr,7,5)<<endl;
    cout<<"First occourence of 4 is at index "<<first_occ(arr1,6,5)<<endl;

return 0;
}
