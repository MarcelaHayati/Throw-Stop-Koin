#include <iostream>
#include <cstdlib>
#include <ctime>
#include <algorithm>
using namespace std;

void sortCoins(int coins[], int size) {
    sort(coins, coins + size);
}

bool binarySearch(int coins[], int size, int target) {
    return binary_search(coins, coins + size, target);
}

int main() {
    srand(time(0));

    cout << "Welcome to Throw Stop Koin simulator" << endl;

    int coins[] = {100, 200, 500};
    int size = sizeof(coins) / sizeof(coins[0]);

    while (true) {
        cout << "Lempar coin (100/200/500)? ";
        char jawaban;
        cin >> jawaban;

        if (jawaban == 'a')
            break;
        else if (jawaban == 's') {

            int sisi = rand() % 2;

            sortCoins(coins, size);

            for (int i = 0; i < size; i++){
                cout << "Koin " << coins[i] << endl;
                if (sisi == rand() % 2)
                    cout << "Gambar" << endl;
                else
                    cout << "Angka" << endl;
            }
        } else {
            cout << "Masukan jawaban yang valid (a/s)!" << endl;
        }
    }
    int target;
    cout << "masukan coin: ";
    cin >> target;

    if (binarySearch(coins, size, target)) {
        cout << "coin " << target << " ditemukan dalam array." << endl;
    } else {
        cout << "coin " << target << " tidak ditemukan di dalam array." << endl;
    }

    return 0;
}
