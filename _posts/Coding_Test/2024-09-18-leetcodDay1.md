---
title: "2024-09-18-leetcodDay1"
categories:
  - Coding_Test
toc: true
toc_sticky: true
tock_label: "List"
typora-root-url: ../
---



# Leetcode Top Interview 150 - 24.09.18

### 88. Merge Sorted Array

![image-20240919011644835](/../assets/images/2024-04-26-UploadTest/image-20240919011644835.png)

- **내 풀이**

```python
# 내 풀이
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        for i in range(len(nums1) - m):
            nums1.remove(0)

        nums1.extend(nums2)

        nums1.sort()
```



간단하게 두 개의 list (nums1과 nums2)를 merge한 후 오름차순 정렬을 해야하는 문제이다. 

하지만 특이사항으로 정답을 return하지 말고 nums1 list 자체를 modify하기만 하면 된다.

즉, 주어진 nums1 list 그 자체를 요구사항대로 수정을 하여야 한다는 것.



가장 먼저 떠오르는 방법으로는 nums1과 nums2를 더한 후 sort한 결과를 nums1에 할당하면 된다고 생각해서 제출을 했었는데...

```python
nums1 = sorted(nums1 + nums2)
```

위와 같은 방법을 사용하면 기존의 nums1이 아닌 새로운 list를 만들어 sorting을 하게 되므로 nums1 list 자체가 바뀌지는 않는다.

따라서 list를 직접 수정하는 방법을 사용하였는데, 

1. list.remove()를 이용해 nums1 list 뒷부분의 의미없는 0을 제거한 후
2. list.extend()로 nums1 list 뒤에 nums2 list를 이어붙였고
3. list.sort()를 통해 nums1 list 자체를 sort하였다.
   (sorted()를 사용하면 nums1의 sorting된 list가 새로 만들어진다.) 



- **다른 풀이**

```python
class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        l, r = 0, 0
        copy1 = deepcopy(nums1)

        for i in range(n+m):
            if r >= n or (l < m and copy1[l] <= nums2[r]):
                nums1[i] = copy1[l]
                l += 1
            else:
                nums1[i] = nums2[r]
                r += 1
```

다른 방법으로는 left와 right의 pointer를 만들어서 for loop을 순회하며 nums1의 각 요소와 nums2의 요소를 하나씩 대소비교를 하여 nums1의 요소를 nums2의 요소로 직접 바꿔주는 방법이 있다.
