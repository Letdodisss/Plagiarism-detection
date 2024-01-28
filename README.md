#include <iostream>

bool checkArrayValue(int size, int array[], int targetValue, std::string condition) {
    if (size <= 0) return false;

    std::cout << "Enter array elements:" << std::endl;
    for (int i = 0; i < size; ++i) std::cin >> array[i];

    bool result = false;
    if (condition == "equals") for (int i = 0; i < size; ++i) if (array[i] == targetValue) result = true;
    else if (condition == "greater") for (int i = 0; i < size; ++i) if (array[i] > targetValue) result = true;
    else if (condition == "less") for (int i = 0; i < size; ++i) if (array[i] < targetValue) result = true;

    std::cout << "The result is: " << (result ? "true" : "false") << std::endl;
    return true;
}

int main() {
    int arraySize, targetValue;
    std::string condition;

    std::cout << "Enter size, value, and condition: ";
    std::cin >> arraySize >> targetValue >> condition;

    int array[arraySize];
    checkArrayValue(arraySize, array, targetValue, condition);

    return 0;
}
