#include <iostream>
#include <vector>
#include <clocale>

using namespace std;

double Lagrange(vector<double> x, vector<double> y, double X) {
    double result = 0;

    for (int i = 0; i < x.size(); i++) {
        double term = y[i];

        for (int j = 0; j < x.size(); j++) {
            if (i != j) {
                term *= (X - x[j]) / (x[i] - x[j]);
            }
        }

        result += term;
    }

    return result;
}

int main() {
    setlocale(LC_ALL, "Russian");

    int n;

    while (true) {
        cout << "Введите количество точек (не меньше 2): ";

        if (cin >> n && n >= 2) {
            break;
        }
        else {
            cout << "Количество точек должно быть целым числом не меньше 2." << endl;
            cin.clear();
            cin.ignore(1000, '\n');
        }
    }

    vector<double> x(n);
    vector<double> y(n);

    cout << endl;
    cout << "Введите координаты точек:" << endl;

    for (int i = 0; i < n; i++) {

        while (true) {
            cout << "x[" << i << "] = ";

            if (cin >> x[i]) {
                break;
            }
            else {
                cout << "Введено не число." << endl;
                cin.clear();
                cin.ignore(1000, '\n');
            }
        }

        while (true) {
            cout << "y[" << i << "] = ";

            if (cin >> y[i]) {
                break;
            }
            else {
                cout << "Введено не число." << endl;
                cin.clear();
                cin.ignore(1000, '\n');
            }
        }
    }

    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {

            if (x[i] == x[j]) {
                cout << endl;
                cout << "Ошибка! Значения x должны быть различными." << endl;
                return 0;
            }

        }
    }

    double X;

    while (true) {
        cout << endl;
        cout << "Введите значение X для интерполяции: ";

        if (cin >> X) {
            break;
        }
        else {
            cout << "Введено не число." << endl;
            cin.clear();
            cin.ignore(1000, '\n');
        }
    }

    double result = Lagrange(x, y, X);

    cout << endl;
    cout << "L(" << X << ") = " << result << endl;

    return 0;
}
