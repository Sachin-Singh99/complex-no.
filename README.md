// All arithematic operation of complex number using classes in c++

#include <iostream>
#include <cmath>
using namespace std;
class complex{
    private:
        float areal;
        float aimag;
        float breal;
        float bimag;
    public:
        void getinfo(float a,float b,float c,float d);
        void display();
        void menu();
        void add(float areal,float aimag,float breal,float bimag);
        void sub(float areal,float aimag,float breal,float bimag);
        void mul(float areal,float aimag,float breal,float bimag);
        void div(float areal,float aimag,float breal,float bimag);
};
void complex::getinfo(float a, float b,float c, float d){
    areal=a;
    aimag=b;
    breal=c;
    bimag=d;
}
void complex::display(){
    cout<<endl<<"First complex number:- ";
    cout<<areal<<"+";
    cout<<aimag<<"i"<<endl;
    cout<<endl<<"Second complex number:- ";
    cout<<breal<<"+";
    cout<<bimag<<"i"<<endl;
}
void complex::menu(){
cout<<"\tMENU\n";
cout<<"a - >>  Addition\n";
cout<<"s - >>  Subtraction\n";
cout<<"m - >>  Multiplication\n";
cout<<"d - >>  Division\n";
}
void complex::add(float areal,float aimag,float breal,float bimag){
    float creal,cimag;
    creal = areal+breal;
    cimag = aimag+bimag;
    cout<<endl<<"The Addition is "<<creal<<"+"<<cimag<<"i";
}
void complex::sub(float areal,float aimag,float breal,float bimag)
{
    float creal,cimag;
    creal = areal-breal;
    cimag = aimag-bimag;
    cout<<endl<<"The Subtraction is "<<creal<<"+"<<cimag<<"i";   
}
void complex::mul(float areal,float aimag,float breal,float bimag)
{
    float creal,cimag;
    creal = areal*breal;
    cimag = aimag*bimag;
    cout<<endl<<"The Multiplication is "<<creal<<"+"<<cimag<<"i";
}
void complex::div(float areal,float aimag,float breal,float bimag)
{
    float creal,cimag;
    float temp;
    temp = (breal*breal)+(bimag*bimag);
    creal = ((breal*breal)+(bimag*bimag))/temp;
    cimag = ((breal*aimag)-(areal*bimag))/temp;
    cout<<endl<<"The Division is "<<creal<<"+"<<cimag<<"i";
}
int main(){
    complex comp;
    float a,b,c,d;
    char ch;
    cout<<endl<<"Enter the real part of 1st complex number: ";
    cin>>a;
    cout<<endl<<"Enter the imaginary part of 1st complex number: ";
    cin>>b;
    cout<<endl<<"Enter the real part of 2nd complex number: ";
    cin>>c;
    cout<<endl<<"Enter the imaginary part of 2nd complex number: ";
    cin>>d;
    comp.getinfo(a,b,c,d);
    comp.display();
    comp.menu();
    cout<<"Choose any one : ";
    cin>>ch;
    switch (ch)
    {
        case 'a':
            comp.add(a,b,c,d);
            break;
        case 's':
            comp.sub(a,b,c,d);
            break;
        case 'm':
            comp.mul(a,b,c,d);
            break;
        case 'd':
            comp.div(a,b,c,d);
            break;
     default:
            cout<<"Invalid Choice!";   
    }
   return 0;
}
