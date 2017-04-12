HAMMING DISTANCE
====


=====

        // XOR returns no.of bits that are not same at corresponding positions
        // 2- 0010 and 6 - 0110. Both integers differ at positions (left to right) 3. 2 ^ 6 = 0010 ^ 0110 = 0100
        // You may notice the 1 in the result.
        // Now if we could calculate all those 1's from the result above we get the hamming distance

        // Any two consecutive numbers when written in base2 always differ by either
        // only one bit or differ by all bits - Ex 10000 (16) and 1111(15) differ by all bits
        // (ignore leading zeros) and 1111 (15) 1110(14) differ by 1.Doing & operation on the result
        //continuously will exhaust all 1s and leads to zero. If we want to calculate number of bits in
        //4...0100(4) & 0011(3) becomes zero by then n is incremented by 1 which is our answer


...
public class Solution {
    public int HammingDistance(int x, int y) {
        int z=x^y;
        int n=0;
        while(z>0)
        {
            z=z&(z-1);
            ++n;
        }
        return n;
    }
}
...
