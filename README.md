#include <stdbool.h>

bool canThreePartsEqualSum(int* arr, int arrSize) {
    int sum = 0;

    for (int i = 0; i < arrSize; i++) {
        sum += arr[i];
    }

    if (sum % 3 != 0) {
        return false;
    }

    int target = sum / 3;
    int currentSum = 0, c = 0;

    for (int i = 0; i < arrSize; i++) {
        currentSum += arr[i];

        if (currentSum == target) {
            c++;
            currentSum = 0; 
            if (c == 2 && i < arrSize - 1) {
                return true;
            }
        }
    }

    return false;
}
