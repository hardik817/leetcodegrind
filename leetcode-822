class Solution {
public:
    int flipgame(vector<int>& fronts, vector<int>& backs) {
        unordered_map<int, int> mp;
        int ans = INT_MAX;
        for (int i = 0; i < fronts.size(); i++) {
            if (fronts[i] == backs[i])
                mp[fronts[i]]++;
        }

        for (int i = 0; i < fronts.size(); i++) {
            if (!mp.count(fronts[i])) {
                ans = min(ans, fronts[i]);
            }
            if (!mp.count(backs[i])) {
                ans = min(ans, backs[i]);
            }
        }
        return ans!=INT_MAX?ans:0;
    }
};