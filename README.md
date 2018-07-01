# coin-flip-1
simulation of a coin flip that ends when three heads appear consecutively.
#include <iostream>
#include <string>
#include <ctime>
using namespace std;
//initializing of inputs
enum { Head, Tail };
int flip();
string label(int);
int flip()
{
    return rand()%2 == 0 ? Head : Tail;
}
string label(int value)
{
    return (value == Head ? "Head.." : "Tail..");
}
   int main (int argc, const char * argv[])
{
    srand( (unsigned int)time(NULL) );
    // variable declaration
    int headCount = 0, tossCount = 0;
    int flipValue = -1;



    // gives the programmer the ability to know the number of heads to restrict before it stops the loop.
    while ( headCount < 3 )
    {
        flipValue = flip();
        headCount = (flipValue == Head) ? (headCount + 1) : 0;
        ++tossCount;
        cout << label(flipValue) << endl;
    }
    // this outputs the answer of total flips and number of heads that have appeared
    cout << "It took " << tossCount << " tosses to get " << headCount << " consecutive heads." << endl;
    system("pause");
    return 0;
}
