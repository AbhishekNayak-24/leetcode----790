# leetcode----790
Domino and Tromino Tiling
//code in java
public class Solution {
    private static final int MOD = 1000000007;

    public int numTilings(int n) {
        if (n == 1) return 1;
        if (n == 2) return 2;
        if (n == 3) return 5;

        long[] dp = new long[n + 1];
        dp[1] = 1;
        dp[2] = 2;
        dp[3] = 5;

        for (int i = 4; i <= n; i++) {
            dp[i] = 2 * dp[i - 1] + dp[i - 3];
            dp[i] %= MOD;
        }

        return (int) dp[n];
    }

    public static void main(String[] args) {
        Solution solution = new Solution();
        System.out.println(solution.numTilings(3)); // Output: 5
        System.out.println(solution.numTilings(4)); // Output: 11
        System.out.println(solution.numTilings(5)); // Output: 24
    }
}
