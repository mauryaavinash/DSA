## to find the majority element greater than n/2
``` cpp

/* find the element which is grater than all elements
  exampe arr[]={2 ,3, 5, 3, 3, 4};
*/

 int find_cand(int a[],int size){
        int maj_index=0,count=1;
        for(int i=1;i<size;i++){
            if(a[maj_index]==a[i])
                count++;
            else 
                count--;
            if(count==0){
                maj_index=i;
                count=1;
            }
        }
        return a[maj_index];
    }
    /* to chech whether the element is greater than n/2 or not*/
    bool ismajority(int a[], int size,  int cand){
        int count=0;
        for(int i=0;i<size;i++){
            if(cand==a[i])
                count++;
        }
        if(count>size/2)
            return 1;
        else
            return 0;
    }
    int majorityElement(int a[], int size)
    {
       
        // your code here
        int cand=find_cand(a,size);
        if(ismajority(a,size,cand))
            return cand;
        else
            return -1;
       
    }