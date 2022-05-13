# Masha Okunevich
### IT Manager
___
### Contact information
**Phone:** +375 29 7754022  
**Email:** mar.okunevich@gmail.com  
**Telegram:** @masha
___
### Skills   
* C++  
* PowerPoint  
* Illustrator
* Microsoft Exel  
* Microsoft Word
___
### Education
IT Manager, 1 grade, VSU named after P. M. Masherov
___
### English level
B1
___
### Code example

C++  
Find a multiplication of two matrixes  
```
#include <iostream> 
#include <iomanip> 
using namespace std; 
 
template <typename T> 
class MAS 
{ 
private: 
    int length, i, j, k; 
    T** Array; 
public: 
 
 
    MAS(int length) 
    { 
        this->length = length; 
        Array = new T * [length]; 
        for (int i = 0; i < length; i++) 
            Array[i] = new T[length]; 
 
        for (int i = 0; i < length; i++) 
            for (int j = 0; j < length; j++) 
                Array[i][j] = 0; 
 
    } 
 
    friend istream& operator>>(istream& in, MAS& m) 
    { 
 
        cout << endl; 
        for (int i = 0; i < m.length; i++) { 
            for (int j = 0; j < m.length; j++) { 
                cout << "a[" << i << "]" << "[" << j << "]="; 
                in >> m.Array[i][j]; 
            } 
        } 
 
        return in; 
    } 
 
    friend ostream& operator<<(ostream& out, MAS& m) 
    { 
        for (int i = 0; i < m.length; i++) { 
            for (int j = 0; j < m.length; j++) { 
                out << m.Array[i][j] << "\t"; 
            } 
            cout << endl; 
        } 
        return out; 
    } 
 
    void Mult(MAS m1, MAS m2, MAS m4, int size) { 
        /*MAS<int> m4(size);*/ 
        for (int i = 0; i < length; ++i) 
        { 
            for (int j = 0; j < length; ++j) 
            { 
                for (int k = 0; k < length; ++k) 
                { 
                    m4.Array[i][j] += m1.Array[i][k] * m2.Array[k][j]; 
                } 
            } 
        } 
 
        for (int i = 0; i < m4.length; i++) { 
            for (int j = 0; j < m4.length; j++) { 
                cout << m4.Array[i][j] << "\t"; 
            } 
            cout << endl; 
        } 
    } 
 
    MAS(const MAS& m) 
    { 
        length = m.length; 
        Array = new T * [length]; 
        for (int i = 0; i < length; i++) { 
            Array[i] = new T[length]; 
        } 
 
        for (int i = 0; i < length; i++) { 
            for (int j = 0; j < length; j++) { 
                Array[i][j] = m.Array[i][j]; 
            } 
        } 
    } 
 
 
    ~MAS() 
    { 
        for (int i = 0; i < length; i++) 
            delete[] Array[i]; 
        delete[] Array; 
    } 
}; 
 
 
int main() 
{ 
    setlocale(0, "rus"); 
    int l = 0; 
    int size; 
    cout << "Введите размерность массива" << endl; 
    cin >> size; 
    MAS<int> m1(size); 
    cout << "Enter elements of matrix 1:" << endl; 
    cin >> m1; 
    cout << endl << m1 << endl; 
    MAS<int> new2(m1); 
    cout << new2 << endl; 
    cout << "Конструктор копирования закончил работу и вывел результат" << endl; 
 
 
    MAS<int> m2(size); 
    cout << "Enter elements of matrix 2:" << endl; 
    cin >> m2; 
    cout << m2 << endl; 
 
    MAS<int> new3(m2); 
    cout << new3 << endl; 
    cout << "Конструктор копирования закончил работу и вывел результат\n" << endl; 
 
    /*MAS<int> m3(size);*/ 
    MAS<int> m4(size); 
    m4.Mult(m1, m2, m4, size); 
 
    system("pause"); 
    return 0; 
}
```
