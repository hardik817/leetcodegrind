class Solution {
public:
    long long digitsUpTo(int x) {
        long long digits = 0;
        long long len = 1;
        long long start = 1;

        while (start <= x) {
            long long end = min((long long)x, start * 10 - 1);
            digits += (end - start + 1) * len;
            start *= 10;
            len++;
        }
        return digits;
    }

    int findNthDigit(int n) {
        int lo = 1, hi = INT_MAX;
        int number = 0;

        // Binary search to find the smallest number where the nth digit lies
        while (lo <= hi) {
            int mid = lo + (hi - lo) / 2;
            if (digitsUpTo(mid) >= n) {
                number = mid;
                hi = mid - 1;
            } else {
                lo = mid + 1;
            }
        }

        // Now, we know the digit is inside `number`
        long long totalDigitsBefore = digitsUpTo(number - 1);
        int offset = n - totalDigitsBefore; // digit offset inside the number
        string numStr = to_string(number);
        return numStr[offset - 1] - '0';
    }
};