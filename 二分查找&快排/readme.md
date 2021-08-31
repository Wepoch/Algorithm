```python
def partition(arr,left,right):
    x=arr[right]
    i=left-1
    for j in range(left,right):
        if arr[j]<=x:
            i+=1
            arr[i],arr[j]=arr[j],arr[i]
    i+=1
    arr[i],arr[right]=arr[right],arr[i]
    return i

def quickSort(arr,left,right):
    if(left<right):
        mid=partition(arr,left,right)
        quickSort(arr,left,mid-1)
        quickSort(arr,mid+1,right)

def binFind(arr,target):
    left,right=0,len(arr)-1
    while left<=right:
        mid=left+(right-left+1)//2
        if arr[mid]==target:
            return mid
        else:
            if arr[mid]<target:
                left=mid+1
            else:
                right=mid-1
    return -1
```





```c++
class Solution
{

public:

  void exchange(int &a,int &b);

  void quickSort(vector<int>&arr,int left,int right);

  int partition(vector<int> &arr,int left,int right);

  int binFind(vector<int>&arr,int target);

};



void Solution::exchange(int &a,int &b)

{

  int temp=a;

  a=b;

  b=temp;

}



void Solution::quickSort(vector<int> &arr,int left, int right)

{

  if (left<right)

  {

​    int mid = partition(arr,left,right);

​    quickSort(arr,left,mid-1);

​    quickSort(arr,mid+1,right);

  }

}



int Solution::partition(vector<int> &arr,int left,int right)

{

  int x = arr[right];

  int i = left-1;

  for (int j = left; j < right; j++)

  {

​    if (arr[j]<=x)

​    {

​      exchange(arr[j],arr[++i]);

​    }

  }

  exchange(arr[++i],arr[right]);

  return i;

}



int Solution::binFind(vector<int> &arr,int target)

{

  int left=0;

  int right=arr.size();

  while (left<=right)

  {

​    int mid=left+(right-left+1)*0.5;

​    if (arr[mid]==target)

​    {

​      return mid;

​    }

​    else

​    {

​      if (arr[mid]<target) left=mid+1;

​      else right=mid-1;

​    }

  }

  return -1;

}
```

