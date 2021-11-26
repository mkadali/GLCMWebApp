#include<iostream>
#include<stdlib.h>
#include<time.h>

int main()
{
  int p[3][3], a,b,c,r,maxnum,temp,dist,angle;
 
 std::cout<<" This program prints GLCM";
 std::cout<<'\n';
 std::cout << "Enter dimension of the row: ";
  std::cin >> r;
   std::cout << "Enter dimension of the column: ";
  std::cin >> c;
   
  // int q[r][c];
 //std::cin>>;
 
//Generate input matrix;

 for(a=0;a<r;a++)
 {
    for(b=0; b<c;b++)
    {
    p[a][b]=rand()%10;
    }
  }
   for(a=0;a<r; a++)
 {
    for(b=0;b<c;b++)
    {
    std::cout<<p[a][b]<<'\t';
   
    }
    std::cout<<'\n';
  }
 
//Get max number

   maxnum=p[0][0];
    for(a=0;a<r; a++)
    {
       for(b=0;b<c;b++)
       {
          if(p[a][b]>maxnum)
          {
            maxnum=p[a][b];
          }
   
        }
         
    }
     std::cout<<"max num is "<<maxnum;
          std::cout<<'\n';
 //temp=maxnum;
 int q[maxnum][maxnum];
 std::cout<<"output matrix is ready";
  std::cout<<'\n';
 //int[][] arr = new int[][];
//generate empty output matrix;

 for(a=0;a<maxnum;a++)
 {
    for(b=0; b<maxnum;b++)
    {
    q[a][b]=0;
    }
  }
   
for(a=0;a<maxnum; a++)
    {
       for(b=0;b<maxnum;b++)
       {
           std::cout<<q[a][b]<<'\t';
         
        }
       
          std::cout<<'\n';
    }

std::cout<<"enter the distance of offset: ";
std::cin >> dist;
std::cout<<'\n';
std::cout<<"enter the angle of offset: ";
std::cin >> angle;
std::cout<<"enter two values for searching: ";
int m, n,count=0;
std::cin >> m >>n;
std::cout<<m <<'\t' <<n;
std::cout<<'\n';

//this is to print co occurence in output matrix;

for(b=0;b<c;b++)
{
   for(a=0;a<r;a++)
   {
      if(p[a][b]==m)
      {
          std::cout<<p[a][b]<<m<<angle;
          if(angle==0)
          {
             //std::cout<<p[a][b+d]<<d;
             if(p[a][b+dist]==n)
             {
               //std::cout<<p[a+d][b]<<d;
                count++;
              }
          }
      }
   }
}  
std::cout<<'\n';
std::cout<<count;
std::cout<<'\n';
}