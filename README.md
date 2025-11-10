# Search-in-Database

#include <stdio.h>
#include<stdlib.h>
#include<string.h>
struct emergency_contacts{
    char name[10];
    int no;
    int dist;
    };


int main() {
    int c,i,j;
    while(1){
    printf("\n\n▶️ Menu:\n1.Add Information \n2.Display data\n3.Sort data\n4.Search information\n5.Exit\n\nEnter your choice:");
    scanf("%d",&c);
    switch(c){
        case 1: //input of data
        
        struct emergency_contacts em[5],temp;

        for(i=0; i<5;i++){
        
        printf("\nenter name of the Hospital: ");
        scanf("%s",em[i].name);
        
        printf("enter Number of the Hospital: ");
        scanf("%d",&em[i].no);
        
        printf("enter distance of that from college in meters: ");
        scanf("%d",&em[i].dist);
        printf("\n---------------------------------------------------\n");
        }
        break;
        
        
        
        case 2:  // Display records
            
            for(i=0;i<5;i++){
            printf("\n\nName of the Hospital: %s",em[i].name);
            printf("\nNumber of the Hospital: %d",em[i].no);
            printf("\nDistance of the Hospital: %d",em[i].dist);
            printf("\n---------------------------------------------------------");
        }
        break;
         
        case 3:// Sorting the data
            for (i=0; i<5;i++){
            for (j=i+1;j<5;j++){
                if(em[i].dist>em[j].dist){
                temp= em[i];
                em[i]=em[j];
                em[j]=temp;
                }
            }
            }
        
        printf("\nHospitals are arranged in ascending order of the distance from the college\n");
        printf("\n\n\n--------------NEAREST HOSPITALS FROM COLLEGE----------------");
        for(i=0;i<5;i++){
            printf("\n\nName of the Hospital: %s",em[i].name);
            printf("\nNumber of the Hospital: %d",em[i].no);
            printf("\nDistance of the Hospital: %d",em[i].dist);
            printf("\n---------------------------------------------------------");
        }
        break;
        
        
        case 4: // Search records
             {char search_name[10];
              int i;
             
             printf("\nEnter name of hospital to search: ");
             scanf("%s",search_name);
             
             for(i=0;i<5;i++){
                if(strcmp(search_name,em[i].name)==0){
                    printf("\n---hospital found---");
                    printf("\n\nName of the Hospital: %s",em[i].name);
                    printf("\nNumber of the Hospital: %d",em[i].no);
                    printf("\nDistance of the Hospital: %d",em[i].dist);
                    return 1;
                 break;
                }
             }
                return 0;
               
            
             
             }
        break;
        
        
        case 5: exit(1);
        
             
    }
    }
    return 0;
    
} 
