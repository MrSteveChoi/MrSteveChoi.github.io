---
title: "Day016 - 42. Trapping Rain Water "
categories:
  - leetcode_150
toc: true
toc_sticky: true
tock_label: "List"
typora-root-url: ../
---


# [42. Trapping Rain Water](https://leetcode.com/problems/trapping-rain-water/)

Given `n` non-negative integers representing an elevation map where the width of each bar is `1`, compute how much water it can trap after raining.

**Example 1:**

<div style="float: left; margin-right: 10px;">
    <img src="../assets/images/2024-10-03-Leetcode150_Day016/rainwatertrap.png" width="450" height="150"/>
</div>
<div style="clear: both;"></div>

git_clone\MrSteveChoi.github.io\_posts\leetcode_150\2024-10-03-Leetcode150_Day016.md
git_clone\MrSteveChoi.github.io\assets\images\2024-10-03-Leetcode150_Day016\rainwatertrap.png

```
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.
```

**Example 2:**

```
Input: height = [4,2,0,3,2,5]
Output: 9
```