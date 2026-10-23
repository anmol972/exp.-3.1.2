class Solution {
public:
    vector<int> topKFrequent(vector<int>& nums, int k) {
        
        unordered_map<int,int>c;

        for(auto x:nums)// ele,freq
        {
            c[x]++;
        }
        // now using max heap

        priority_queue<pair<int,int>>p;

        for(auto x:c)
        {
            int freq=x.second;
            int ele = x.first;

            // work
            p.push({freq,ele});
        }

        vector<int>v;

        while(p.size()>0 && k)
        {
            int ele=p.top().second;
            p.pop();
            v.push_back(ele);
            k--;
        }
        return v;
    }
};
