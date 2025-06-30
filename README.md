# Tic-Tac-Toe


#include <iostream>

using namespace std;
int i,j,k,y,g,h,ct;
char x,a[4][4];
bool win(char s)
{
    for (int i = 1; i <= 3; i++)
        if (a[i][1] == s && a[i][2] == s && a[i][3] == s)
            return true;
    for (int j = 1; j <= 3; j++)
        if (a[1][j] == s && a[2][j] == s && a[3][j] == s)
            return true;
    if (a[1][1] == s && a[2][2] == s && a[3][3] == s)
        return true;
    if (a[1][3] == s && a[2][2] == s && a[3][1] == s)
        return true;

    return false;
}
void tictac(int &g, int &h)
{

    for(int i=1;i<=3;i++)
        for(int j=1;j<=3;j++)
        if(a[i][j]=='0')
    {
        a[i][j]='O';
        if(win('O'))
        {
            g=i;
            h=j;
            return;
        }
        a[i][j]='0';
    }
    for(int i=1;i<=3;i++)
        for(j=1;j<=3;j++)
        if(a[i][j]=='0')
    {
        a[i][j]='X';
        if(win('x'))
        {
            g=i;
            h=j;
            return;
        }
        a[i][j]='0';
    }
    if(a[2][2]=='0')
    {
        g=2;
        h=2;
        return;
    }
    if(a[1][1]=='0')
    {
        g=1;
        h=1;
        return;
    }
    if(a[3][3]=='0')
    {
        g=3;
        h=3;
        return;
    }
    if(a[1][3]=='0')
    {
        g=1;
        h=3;
        return;
    }
    if(a[3][1]=='0')
    {
        g=3;
        h=1;
        return;
    }
    for(int i=1;i<=3;i++)
        for(int j=1;j<=3;j++)
        if(a[i][j]=='0')
    {
        g=i;
        h=j;
        return;
    }
}
int main()
{
    for (i=1;i<=3;i++)
        for(j=1;j<=3;j++)
           a[i][j]='0';
    cout<<"The positions :\n";
    k=0;
    for(i=1;i<=3;i++)
    {
        for(j=1;j<=3;j++)
        cout<<k++<<" ";
        cout<<endl;
    }
    cout<<endl;
    for(i=1;i<=3;i++)
    {
        for(j=1;j<=3;j++)
        cout<<a[i][j]<<" ";
        cout<<endl;;
    }
    cout<<endl;
    cout<<"Which one begins? - You(y) or me(m)";
    cin>>x;
    if(x=='y')
    {
        cout<<"OK";
        cout<<endl;
        ct=0;
        while(ct<9)
        {
            if(ct%2==0)
            {
                tictac(g,h);
                a[g][h]='O';
            }
            else
            {
                cin>>y;
                a[y/3+1][y%3+1]='X';
            }
        ct++;
        cout<<endl;
        cout<<endl;
             for(i=1;i<=3;i++)
    {
        for(j=1;j<=3;j++)
        cout<<a[i][j]<<" ";
        cout<<endl;;
    }
    if(win('X')) {
    cout << "YOU WIN!\n";
    break;
}
if(win('O')) {
    cout << "YOU LOSE!\n";
    break;
}
        }
    }
    if(x=='m')
    {
        ct=0;
        while(ct<9)
        {
            if(ct%2==0)
            {
        cout<<"OK, choose";
        cin>>y;
        a[y/3+1][y%3+1]='X';
            }
            else
            {
                tictac(g,h);
                a[g][h]='O';
            }
            ct++;
        cout<<endl;
        cout<<endl;
            for(i=1;i<=3;i++)
    {
        for(j=1;j<=3;j++)
        cout<<a[i][j]<<" ";
        cout<<endl;;
    }
    if(win('X')) {
    cout << "YOU WIN!\n";
    break;
}
if(win('O')) {
    cout << "YOU LOSE!\n";
    break;
}
        }

    }

    return 0;
}

