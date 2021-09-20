# C-Four-Pillars-Program

#include <iostream.h>
class shape
{

public:
    virtual void read()=0;
    virtual void show()=0;
};
class circle:public shape
{
private:
    float r;
public:
    void read()
    {
        cout<<"enter radius:";
        cin>>r;
    }
        void show()
        {
            cout<<"area of circle= "<<3.14*r*r<<endl;
        }
};
class rectangle:public shape
{

private:
    float l,b;
public:
    void read()
    {
        cout<<"enter the length of rectangle:";
        cin>>1;
        cout<<"enter the breadth of rectangle:";
        cin>>b;
    }
    void show()
    {
        cout<<"area of rectangle="<<l*b<<endl;
    }
};
class triangle:public shape
{
private:
    float b,h;
public:
    void read()
    {
        cout<<"enter the base of triangle:";
        cin>>b;
        cout<<"enter the height of rectangle:";
        cin>>h;
    }
    void show()
    {
        cout<<"area of triangle"<<b*h*0.5<<endl;
    }
};

void main()
{
    shape *s[10];
    int count=0,i,choice,menu();
    choice=menu();
    while(choice!=4)
    {
        switch(choice)
        {
            case 1:
                s[count]=new circle;
                s[count] ->read();
                count++;
                break;
            case 2:
                s[count]=new rectangle;
                s[count] ->read();
                count++;
                break;
            case 1:
                s[count]=new triangle;
                s[count] ->read();
                count++;
                break;
            default:
                cout<<"invalid choice\n";

        }
        choice=menu();
    }
    for(i=0; i<count;++i)
    {
        s[i] ->show();
    }
}
int menu()
{
    int ch;
    cout<<"1:circle\n";
    cout<<"2:rectangle\n";
    cout<<"3:triangle\n";
    cout<<"4:exit\n";
    cout<<"enter your choice:\n";
    cin>>ch;
    return ch;
}
