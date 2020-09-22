<div align="center">

## Prim's Algorithm


</div>

### Description

Implementataion of Prim's Algorithm
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Adri Jovin](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/adri-jovin.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[Algorithms](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/algorithms__3-29.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/adri-jovin-prim-s-algorithm__3-12930/archive/master.zip)





### Source Code

```
#include<iostream.h>
#include<conio.h>
class prim
{
int a,b,u,v,i,j,n,noofedge;
int visited[10],min,minicost,cost[10][10];
public:
prim()
{
noofedge=1;
minicost=0;
}
void read();
void prims(int cost[][10],int n);
};
void prim::read()
{
cout<<"\nEnter the number of vertices:\n";
cin>>n;
cout<<"\nEnter the adjacency matrix:\n";
for(i=1;i<=n;i++)
{
for(j=1;j<=n;j++)
{
cin>>cost[i][j];
if(cost[i][j]==0)
cost[i][j]=999;
}
}
prims(cost,n);
}
void prim::prims(int cost[][10],int n)
{
for(i=2;i<=n;i++)
visited[i]=0;
cout<<"\nEdges in the spanning tree are: \n";
visited[1]=1;
while(noofedge<n)
{
for(i=1,min=999;i<=n;i++)
for(j=1;j<=n;j++)
if(cost[i][j]<min)
if(visited[i]==0)
continue;
else
{
min=cost[i][j];
a=u=i;
b=v=j;
}
if(visited[u]==0||visited[v]==0)
{
noofedge++;
cout<<"\nEdge("<<a<<" , "<<b<<"):"<<min;
minicost+=min;
visited[b]=1;
}
cost[a][b]=cost[b][a]=999;
}
cout<<"\nMinimum cost spanning tree is:"<<minicost;
}
void main()
{
clrscr();
cout<<"\nPrim's algorithm\n";
prim p;
p.read();
getch();
}
```

