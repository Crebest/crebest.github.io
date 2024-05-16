# 每周一道算法题：

[合并两个有序数组：](https://leetcode.cn/problems/merge-sorted-array/description/?envType=study-plan-v2&envId=top-interview-150)

```js
/**
 * @param {number[]} nums1
 * @param {number} m
 * @param {number[]} nums2
 * @param {number} n
 * @return {void} Do not return anything, modify nums1 in-place instead.
 */
var merge = function (nums1, m, nums2, n) {
    let index = 0;
    for (let i = 0; i < n + m; i++) {
        console.log(nums1);
        for (let j = index; j < n; j++) {
            if (nums1[i] > nums2[j]) {
                console.log('第一种情况，找到了 nums2[j] 的插入位置 nums1[i] > nums2[j]');
            }
            if ( i>=n+index) {
                console.log('第二种情况，nums1 到头了（i>m+index），也就是后面的都是零');
            }
            if ((m==0 && nums1[i]===0)) {
                console.log('第三种情况，nums1 为 [0]');
            }
            //第一种情况，找到了 nums2[j] 的插入位置 nums1[i] > nums2[j]
            //第二种情况，nums1 到头了（i>n+index），也就是后面的都是零
            //第三种情况，nums1 为 [0]
            if (nums1[i] > nums2[j] || i>=m+index || (i==0 && nums1[i]===0 && index===0)) {
                
                index++;
                let temp = nums1[i];
                let temp1 = nums2[j];
                //把 nums2 找到的元素插入到 nums1，并且把 nums1 插入位置所有元素后移
                for (let k = i; k < n + m; k++) {
                    nums1[k] = temp1;
                    temp1 = temp;
                    temp = nums1[k + 1];
                }
            }
        }
    }
};
```



# 每周一篇文章点评：

[WebSockets vs Server-Sent-Events vs Long-Polling vs WebRTC vs WebTransport | RxDB - JavaScript Database](https://rxdb.info/articles/websockets-sse-polling-webrtc-webtransport.html)

服务端向客户端推送消息的方式有哪些？

1、客户端轮询

2、长连接

3、websocket

4、SSE

5、WebTransport

6、WebRTC



# 每周一个小技巧：

把 github 的链接里的 com 改成 dev，会得到一个在线版 vscode，还可以升级到虚拟机版本，每个月都有一定的免费使用时长。 



# 每周一篇学习分享：

最近一年面试了大量的技术候选人，有一个深刻的体会，技术的春天已经过去了，想当年，随随便便培训班培训几个月，就可以找到一份高薪的工作，而现在几乎所有的互联网公司都在节衣缩食，现在找工作的难度可想而知。很多人还是之前的思维，认为只要能干活，就能找到工作，类似的这些误区很多，这里简单总结一下。

一、除了技术硬，其它能力也很重要。实际上面试中技术面只是其中一个环节，很多人忽视的沟通能力、职业规划能力、管理能力、逻辑思维能力都是面试的考查范围。

二、学历越来越重要。现在候选人越来越多，很多公司都把学历当成一个简历筛选门槛。

三、技术上一定要有一方面非常突出，现在招人的逻辑是你的某方面能力可以补齐团队的短板，所以你的综合素质一定超过团队一半以上的人才有可能考虑给你 offer，所以在某一个技术领域深耕很重要。
