# WEEKELY-DSA-SERIES-WEEK-2-

# 📘 DSA Weekly Series - Week 2 Day 1

## 🔹 Topic Covered
- Introduction to **Strings** in C++
- Practiced string manipulation with **LeetCode #344 - Reverse String**

## 🚀 Problem Statement
**LeetCode 344. Reverse String**  
Write a function that reverses a string. The input string is given as an array of characters `s`.


## 📝 Learning
- Strings can be treated as **character arrays** in C++.
- Reversal can be done using **two-pointer technique**.


Today I continued my DSA Weekly Series journey. On Day 2 of Week 2, I practiced some fundamental array problems from LeetCode. These problems covered different concepts like hashing, two-pointer techniques, XOR tricks, and set usage — all very common in real-world problem solving and interviews.

001_two_sum/README.md

Problem (short): Given an array of integers nums and a target, return indices of the two numbers such that they add up to target. Assume exactly one solution.

Approach: A naive approach checks all pairs in O(n²). An improved approach uses a hash map for O(n).
#include <bits/stdc++.h>
using namespace std;


class Solution {
public:
vector<int> twoSum(vector<int>& arr, int target) {
unordered_map<int,int> mp; // value -> index
for (int i = 0; i < (int)arr.size(); i++) {
int need = target - arr[i];
if (mp.count(need)) {
return {mp[need], i};
}
mp[arr[i]] = i;
}
return {}; // should not reach as per problem constraints
}
};


int main() {
Solution sol;
vector<int> arr = {2,7,11,15};
int target = 9;
auto ans = sol.twoSum(arr, target);
for (int x : ans) cout << x << " ";
cout << "\n";
return 0;
}


344_reverse_string/README.md

Problem (short): Reverse the input string (given as an array of characters) in-place.

Approach: Two-pointer swap from ends moving inward.
#include <bits/stdc++.h>
using namespace std;


class Solution {
public:
void reverseString(vector<char>& s) {
int st = 0, end = (int)s.size() - 1;
while (st < end) {
swap(s[st++], s[end--]);
}
}
};


int main() {
Solution sol;
vector<char> s = {'h','e','l','l','o'};
sol.reverseString(s);
for (char c : s) cout << c;
cout << "\n";
return 0;
}

268_missing_number/README.md

Problem (short): Given n numbers in the range [0,n] with one missing, find the missing number.

Approach: Sorting is a simple O(n log n) approach. A more optimal O(n) way is using XOR or the sum formula.

#include <bits/stdc++.h>
using namespace std;


class Solution {
public:
int missingNumber(vector<int>& arr) {
sort(arr.begin(), arr.end());
int n = arr.size();
for (int i = 0; i < n; i++) {
if (arr[i] != i) return i;
}
return n; // if no mismatch, missing number is n
}
};


int main() {
Solution sol;
vector<int> arr = {3,0,1};
cout << sol.missingNumber(arr) << "\n"; // prints 2
return 0;
}

217_contains_duplicate/README.md

Problem (short): Given an integer array, return true if any value appears at least twice.

Approach: Sort the array and check adjacent elements. Simpler and clean.
#include <bits/stdc++.h>
using namespace std;


class Solution {
public:
bool containsDuplicate(vector<int>& arr) {
sort(arr.begin(), arr.end());
for (int i = 1; i < (int)arr.size(); i++) {
if (arr[i] == arr[i-1]) return true;
}
return false;
}
};


int main() {
Solution sol;
vector<int> arr = {1,2,3,1};
cout << (sol.containsDuplicate(arr) ? "true" : "false") << "\n";
return 0;
}

        
    
