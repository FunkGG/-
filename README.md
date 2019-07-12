# leetcode刷题记录
## day1
### 1.两数之和
**题解：** 给定一个数组nums和目标值target，找出和为目标值的两个整数，并返回下标。<br>
·暴力法：双循环，时间复杂度O(n^2)，空间复杂度O(1)。<br>
·两遍哈希表：哈希表保存元素与索引。哈希表将查找时间从O(n)降到O(1)，时间复杂的O(n),空间复杂度O(n)。<br>
·一遍哈希表法：一边遍历一边存入哈希表，时间复杂的O(n),空间复杂度O(n)。<br>
### 15.三数之和
**题解：** 排序，固定一个数字然后头尾双指针。时间复杂度O(n^2)，空间复杂度O(1)。<br>
### 16.最接近的三数之和
**题解：** 排序+双指针
### 18.四数之和
**题解：** 双循环+双指针。--时间还可继续优化。
### 14.最长公共前缀
**题解：** 编写一个函数来查找字符串数组中的最长公共前缀。如果不存在公共前缀，返回空字符串 ""。<br>
·依次扫描法：依次遍历字符串，遍历第i个字符串的时候，找到公共前缀，时间复杂的O(s),s是所有字符数量总和,空间复杂度O(1)。<br>
·同时扫描法：水平扫描时遍历所有字符串，如果相同，继续扫描。时间复杂的O(s),s是所有字符数量总和,空间复杂度O(1)。<br>
·分治：将原问题分成两个子问题。时间复杂的O(s),s是所有字符数量总和,空间复杂度O(mlog(n))。<br>
·二分查找法：时间复杂的O(slog(n)),s是所有字符数量总和,空间复杂度O(1)。<br>
### 125.验证回文串
**题解：** 双指针法。设置左右指针，向中间判断，跳过非数字字母的字符；将字母全部装化为小写。<br>
python可使用filter(str.isalnum,s)。<br>
### 151.反转字符串里的单词
**题解：** 倒序遍历字符串，遇到字母记录位置i，继续遍历遇到空格记录j，添加s[j+1:i+1]。由于首部没有空格，可以在字符串前加' '，或者最后加上s[:i+1]。<br>
### 33.搜索旋转排序数组
**题解：** 二分查找法，时间复杂度O(logn)。<br>  
### 153.寻找旋转排序数组中的最小值
**题解：** 二分查找法，时间复杂度O(logn)。<br>
### 859.亲密字符串
**题解：** 对于两个小写字符串A、B,通过交换A中两个字母得到B相等的结果则返回True，否则返回False。首先判断字符串A、B长度是否相等，如果不相等直接返回False。<br>
·A、B如果相等，需要交换两个相同的元素，判断A中是否有相同元素；<br>
·如果不等，且不相等的字符为两个，判断能否交换两个字母使A、B相等，否则返回False。<br>
## day2
### 2.两数相加
**题解：** 给出两个非空的链表用来表示两个非负的整数。其中，它们各自的位数是按照逆序的方式存储的，并且它们的每个节点只能存储一位数字。注意进位。
### 21.合并两个有序列表
**题解：** 将两个有序链表合并为一个新的有序链表并返回。新链表是通过拼接给定的两个链表的所有节点组成的。
### 23.合并K个排序链表
**题解：** 合并 k 个排序链表，返回合并后的排序链表。请分析和描述算法的复杂度。<br>
解法一：暴力（列表加速）<br>
解法二：逐一比较（用队列优化）<br>
解法三：逐一两两合并<br>
解法四：分治<br>
### 19.删除链表的倒数第N个节点
**题解：** 给定一个链表，删除链表的倒数第 n 个节点，并且返回链表的头结点。<br>
解法一：两次遍历法<br>
解法二：双指针一次遍历<br>
解法三：列表作弊法。<br>
### 24.两两交换链表中的节点
**题解：** 给定一个链表，两两交换其中相邻的节点，并返回交换后的链表。你不能只是单纯的改变节点内部的值，而是需要实际的进行节点交换。<br>
解法一：列表法 一个列表存单数，一个列表存偶数，然后连起来。<br>
解法二：递归。<br>
解法三：直接翻转（栈思想）。
### 25.K个一组反转链表
**题解：** 给你一个链表，每 k 个节点一组进行翻转，请你返回翻转后的链表。k 是一个正整数，它的值小于或等于链表的长度。如果节点总数不是 k 的整数倍，那么请将最后剩余的节点保持原有顺序。<br>
解法一：用栈，把K个数压入栈中，然后弹出来的顺序就是翻转的。<br>
解法二：尾插法，一个指针移动到要翻转部分的最后一个元素（tail）,从要翻转的第一个元素一次翻转<br>
解法三：递归。
### 61.旋转链表
**题解：** 给定一个链表，旋转链表，将链表每个节点向右移动 k 个位置，其中 k 是非负数。主要优化k大于链表长度的情况。
### 62.不同路径
**题解：** 一个机器人位于一个 m x n 网格的左上角。机器人每次只能向下或者向右移动一步。机器人试图达到网格的右下角。问总共有多少条不同的路径？<br>
解法一：动态规划 时间复杂度O(mn),空间复杂度可优化至O(n)<br>
解法二：排列组合(比较简单)<br>
### 63.不同路近2
**题解：** 现在考虑网格中有障碍物。网格中的障碍物和空位置分别用 1 和 0 来表示。使用动态规划，遇到1跳过并且置0，时间复杂度O(mn),空间复杂度O(1)
### 64.最小路径和
**题解：** 给定一个包含非负整数的 m x n 网格，请找出一条从左上角到右下角的路径，使得路径上的数字总和为最小。<br>
依然动态规划，grid[i][j] += min(grid[i][j-1], grid[i-1][j])，第一行与第一列单独算。时间复杂度O(mn),空间复杂度O(1)。

