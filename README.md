#include <iostream>
using namespace std;

const int SIZE = 5;

void readNumbers(double nums[], int n) {
    for (int i = 0; i < n; i++) {
        cout << "Enter number " << i + 1 << ": ";
        cin >> nums[i];
    }
}

double findSum(const double nums[], int n) {
    double sum = 0;
    for (int i = 0; i < n; i++) sum += nums[i];
    return sum;
}

double findProduct(const double nums[], int n) {
    double product = 1;
    for (int i = 0; i < n; i++) product *= nums[i];
    return product;
}

double findAverage(const double nums[], int n) {
    return findSum(nums, n) / n;
}

double findMin(const double nums[], int n) {
    double min = nums[0];
    for (int i = 1; i < n; i++)
        if (nums[i] < min) min = nums[i];
    return min;
}

double findMax(const double nums[], int n) {
    double max = nums[0];
    for (int i = 1; i < n; i++)
        if (nums[i] > max) max = nums[i];
    return max;
}

double findRange(const double nums[], int n) {
    return findMax(nums, n) - findMin(nums, n);
}

void printResults(double sum, double product, double avg,
                  double min, double max, double range) {
    cout << "\n--- Results ---" << endl;
    cout << "Sum            : " << sum << endl;
    cout << "Multiplication : " << product << endl;
    cout << "Average        : " << avg << endl;
    cout << "Minimum        : " << min << endl;
    cout << "Maximum        : " << max << endl;
    cout << "Range          : " << range << endl;
}

int main() {
    double nums[SIZE];

    readNumbers(nums, SIZE);

    printResults(findSum(nums, SIZE),
                 findProduct(nums, SIZE),
                 findAverage(nums, SIZE),
                 findMin(nums, SIZE),
                 findMax(nums, SIZE),
                 findRange(nums, SIZE));

    return 0;
}
