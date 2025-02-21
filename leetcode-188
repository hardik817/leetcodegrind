class Solution {
    int solve(int index,int buy,int cnt,int n,vector<int> &prices,vector<vector<vector<int>>> &dp){
        if(index==n){
            return 0;
        }
        if(cnt==0){
            return 0;
        }
        if(dp[index][buy][cnt]!=-1){
            return dp[index][buy][cnt];
        }
        int profit=0;
        if(buy){
            int pick=-prices[index]+solve(index+1,false,cnt,n,prices,dp);
            int notPick=0+solve(index+1,true,cnt,n,prices,dp);
            profit=max(pick,notPick);
        }
        else{
            int pick=prices[index]+solve(index+1,true,cnt-1,n,prices,dp);
            int notPick=0+solve(index+1,false,cnt,n,prices,dp);
            profit=max(pick,notPick);
        }
        return dp[index][buy][cnt]=profit;
    }
public:
    int maxProfit(int k, vector<int>& prices) {
        int n=prices.size();
        vector<vector<vector<int>>> dp(n,vector<vector<int>>(2,vector<int>(k+1,-1)));
        return solve(0,true,k,n,prices,dp);
    }
};