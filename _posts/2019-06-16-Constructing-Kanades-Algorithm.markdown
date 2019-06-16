---
layout: post
title:  "Constructing Kanades Algorithm"
date:   2019-06-16 18:09:37 -0400
description: Kanades Algorithm is an algorithm used for solving the maximum contiguous sum problem.
categories: softwareengineering
tags: "algorithms, software engineering, interview questions"
---
While practicing coding questions on Careercup.com. I decided to try a Bloomberg coding exercises. One of the challenges posted in the maximum contiguous sum problem. The algorithm that is used to solve this is Kanade's algorithm. The algorithm is named after the inventor of the algorithm, Jay Kadane. It is an O(n) time and O(1) space complexity.

The maximum contiguous sum problem is as follows. Given an array of negative and positive integers, determine the sub array that has the maximum sum.

To approach this problem, you must first determine a good initial sum. The must obvious starting sum is zero. We then see that we must continually add the numbers in the array. The next question is what determines if we keep summing or restart. We should continue to add numbers to the sum as long as the numbers contribute to maximizing the sum. The only time a number doesn't maximize the sum is when it is negative. This means that the running sum should be reset when a number is so large in the negative direction that it results in a negative sum. In addition to resetting the sum, we want to set the starting and end point to the next number inline. This moves our sum to the next range to test. In addition to testing a current range we want to track the maximum range so far. This leads to the next important step.
A max sum check should be done before testing if the sum still positive. If the sum so far is greater than the maximum sum the max sum, max end, and max start should be updated. Another consideration for this algorithm is to determine the best max sum starting sum. This could be the minimum int value or the first element in the array. The minimum int value is better because then a check for array greater zero is not needed.