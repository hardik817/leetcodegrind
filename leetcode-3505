class Solution {
public:
long long func(int i,int k,vector<int>&nums ,int x,vector<vector<long long>>&dp,vector<long long>&cost){
    if(k == 0 ) return 0;
    if(i >= nums.size()) return 1e13;
    if (dp[i][k] != -1) return dp[i][k];
    long long take = 1e13;
    if(i + x <= nums.size()){
            take = cost[i] + func(i + x, k - 1, nums, x, dp,cost);
    }
    long long nottake = func(i+1,k,nums,x,dp,cost);
    return dp[i][k] =  min(take,nottake);
}
    long long minOperations(vector<int>& nums, int x, int k) {
        vector<vector<long long>>dp(nums.size(),vector<long long>(k+1,-1));
        multiset<int>rightmin;
        int n = nums.size();
        multiset<int,greater<int>>leftmax;
        vector<long long>cost(nums.size(),0);
        long long leftsum = 0,rightsum = 0;
        for(int i=0;i<x;i++){
            if(leftmax.empty() || nums[i] <= *leftmax.begin()){
                leftmax.insert(nums[i]);
                leftsum += nums[i];
            }
            else {
                rightmin.insert(nums[i]);
                rightsum += nums[i];
        }
            int left = leftmax.size() , right = rightmin.size();
            if(left - right > 1){
                leftsum -= *leftmax.begin();
                rightsum += *leftmax.begin();
                rightmin.insert(*leftmax.begin());
                leftmax.erase(leftmax.begin());
            }
            else if(left < right){
                leftsum += *rightmin.begin();
                rightsum -= *rightmin.begin();
                leftmax.insert(*rightmin.begin());
                rightmin.erase(rightmin.begin());
            }
        }
        for(int i=x;i<=n;i++){
            int leftsize = leftmax.size();
            int rightsize = rightmin.size();
            int mid = *leftmax.begin();
            cost[i-x] = ((leftsize *1LL* mid )- leftsum) +(rightsum - (rightsize *1LL * mid));
            if(i == n)break;
            int prev = nums[i-x];
            if(leftmax.find(prev) != leftmax.end()){
                leftsum -= prev;
                leftmax.erase(leftmax.find(prev));
            }
            else{
                rightsum -= prev;
                rightmin.erase(rightmin.find(prev));
            }
             int left = leftmax.size() , right = rightmin.size();
            if(left - right > 1){
                leftsum -= *leftmax.begin();
                rightsum += *leftmax.begin();
                rightmin.insert(*leftmax.begin());
                leftmax.erase(leftmax.begin());
            }
            else if(left < right){
                leftsum += *rightmin.begin();
                rightsum -= *rightmin.begin();
                leftmax.insert(*rightmin.begin());
                rightmin.erase(rightmin.begin());
            }
             if(leftmax.empty() || nums[i] <= *leftmax.begin()){
                leftmax.insert(nums[i]);
                leftsum += nums[i];
            }
            else {
                rightmin.insert(nums[i]);
                rightsum += nums[i];
        }
             left = leftmax.size() , right = rightmin.size();
            if(left - right > 1){
                leftsum -= *leftmax.begin();
                rightsum += *leftmax.begin();
                rightmin.insert(*leftmax.begin());
                leftmax.erase(leftmax.begin());
            }
            else if(left < right){
                leftsum += *rightmin.begin();
                rightsum -= *rightmin.begin();
                leftmax.insert(*rightmin.begin());
                rightmin.erase(rightmin.begin());
            }

        }
     
        return func(0,k,nums,x,dp,cost);
    }
};