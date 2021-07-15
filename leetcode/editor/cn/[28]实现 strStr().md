<p>实现 <a href="https://baike.baidu.com/item/strstr/811469" target="_blank">strStr()</a> 函数。</p>

<p>给你两个字符串 <code>haystack</code> 和 <code>needle</code> ，请你在 <code>haystack</code> 字符串中找出 <code>needle</code> 字符串出现的第一个位置（下标从 0 开始）。如果不存在，则返回  <code>-1</code><strong> </strong>。</p>

<p> </p>

<p><strong>说明：</strong></p>

<p>当 <code>needle</code> 是空字符串时，我们应当返回什么值呢？这是一个在面试中很好的问题。</p>

<p>对于本题而言，当 <code>needle</code> 是空字符串时我们应当返回 0 。这与 C 语言的 <a href="https://baike.baidu.com/item/strstr/811469" target="_blank">strstr()</a> 以及 Java 的 <a href="https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#indexOf(java.lang.String)" target="_blank">indexOf()</a> 定义相符。</p>

<p> </p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>haystack = "hello", needle = "ll"
<strong>输出：</strong>2
</pre>

<p><strong>示例 2：</strong></p>

<pre>
<strong>输入：</strong>haystack = "aaaaa", needle = "bba"
<strong>输出：</strong>-1
</pre>

<p><strong>示例 3：</strong></p>

<pre>
<strong>输入：</strong>haystack = "", needle = ""
<strong>输出：</strong>0
</pre>

<p> </p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>0 <= haystack.length, needle.length <= 5 * 10<sup>4</sup></code></li>
	<li><code>haystack</code> 和 <code>needle</code> 仅由小写英文字符组成</li>
</ul>
<div><div>Related Topics</div><div><li>双指针</li><li>字符串</li><li>字符串匹配</li></div></div><div><li>👍 959</li><li>👎 0</li></div>





#### **参考答案：**

```java
class Solution {
    public int strStr(String haystack, String needle) {
        return haystack.indexOf(needle);
    }
}
```

**1. 暴力匹配**

```java
```

**复杂度分析**

- 时间复杂度：![O(n \times m)](http://latex.codecogs.com/svg.latex?O(n \times m))，其中 ![n](http://latex.codecogs.com/svg.latex?n) 是字符串 ![\textit{haystack}](http://latex.codecogs.com/svg.latex?\textit{haystack}) 的长度， ![m](http://latex.codecogs.com/svg.latex?m)是字符串 ![\textit{needle}](http://latex.codecogs.com/svg.latex?\textit{needle}) 的长度。最坏情况下我们需要将字符串 ![\textit{needle}](http://latex.codecogs.com/svg.latex?\textit{needle}) 与字符串  的所![\textit{haystack}](http://latex.codecogs.com/svg.latex?\textit{haystack})有长度为  的子串![m](http://latex.codecogs.com/svg.latex?m)均匹配一次。

- 空间复杂度：![O(1)](http://latex.codecogs.com/svg.latex?O(1))。我们只需要常数的空间保存若干变量。

**2. Knuth-Morris-Pratt 算法**

```java
```

**复杂度分析**

- 时间复杂度：![O(n + m)](http://latex.codecogs.com/svg.latex?O(n + m))，其中 ![n](http://latex.codecogs.com/svg.latex?n) 是字符串 ![\textit{haystack}](http://latex.codecogs.com/svg.latex?\textit{haystack}) 的长度， ![m](http://latex.codecogs.com/svg.latex?m)是字符串 ![\textit{needle}](http://latex.codecogs.com/svg.latex?\textit{needle}) 的长度。我们至多需要遍历两字符串一次。

- 空间复杂度：![O(m)](http://latex.codecogs.com/svg.latex?O(m))，其中  ![m](http://latex.codecogs.com/svg.latex?m)是字符串  的![\textit{needle}](http://latex.codecogs.com/svg.latex?\textit{needle})长度。我们只需要保存字符串  的前![\textit{needle}](http://latex.codecogs.com/svg.latex?\textit{needle})缀函数。

