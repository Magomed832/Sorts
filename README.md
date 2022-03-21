# Sorts
#include <iostream>;
using namespace std;

void selection(){
    int a[20], n;
    cout << "enter the size (0 < n < 20): ";
    cin >> n;
    cout << "enter the values:\n";
    for (int i = 0; i < n; i++) {
        cin >> a[i];
    }
    cout << "[";
    for (int i = 0; i < n; i++) {
        if (i == 0) cout << a[i];
        else cout << ", " << a[i] ;
    }
    cout << "]\n";
    int min; 
    for (int i = 0; i < n - 1; i++)
    {
        min = i; 
        for (int j = i + 1; j < n; j++)
        {
            if (a[j] < a[min]) 
            min = j;
        }
        //change
        int k = a[i];
        a[i] = a[min];
        a[min] = k;
    }
    cout << "[";
    for (int i = 0; i < n; i++) {
        if (i == 0) cout << a[i];
        else cout << ", " << a[i];
    }
    cout << "]\n";
}
void shell() {
    int a[20], n, i,j, step;
    cout << "enter the size (0 < n < 20): ";
    cin >> n;
    cout << "enter the values:\n";
    for (int i = 0; i < n; i++) {
        cin >> a[i];
    }
    cout << "[";
    for (int i = 0; i < n; i++) {
        if (i == 0) cout << a[i];
        else cout << ", " << a[i];
    }
    cout << "]\n";
    for (step = n / 2; step > 0; step /= 2)
        for (i = step; i < n; i++)
        {
            int k = a[i];
            for (j = i; j >= step; j -= step)
            {
                if (k < a[j - step])
                    a[j] = a[j - step];
                else
                    break;
            }
            a[j] = k;
        }
    cout << "[";
    for (int i = 0; i < n; i++) {
        if (i == 0) cout << a[i];
        else cout << ", " << a[i];
    }
    cout << "]\n";
}

int main()
{
    cout << "choose a sort: " << endl << "1. selection" << endl << "2. shell\n";
    char k;
    bool b = false;
    while (b!=true) {
        cout << "cin: ";
        cin >> k;
        if ((k == '1') || (k == '2')) {
            switch (k) {
            case '1':
                selection();
                break;
            case '2':
                shell();
                break;
            }
            b = true;
        }
        else b = false;
    }
}
