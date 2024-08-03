### Chef and digits of a number
##### [https://www.codechef.com/problems/LONGSEQ]
### cpp
```cpp
#include <stdio.h>

int main(void) {
		int t;
	scanf("%d",&t);
	while(t--){
	    char num[100001];
	    scanf("%s",num);
	    int ones=0; int zeros=0;
	    int length=strlen(num);
	    for(int i=0;i<length;i++){
	       
	        if(num[i]=='1'){
	            ones++;
	        }
	        else if(num[i]=='0'){
	            zeros++;
	        }
	       
	    
	    }
	    
	    if(ones==1 || zeros==1){
	        printf("YES\n");
	        
	    }
	    else{
	        printf("NO\n");
	    }
	}

}
```
