---
title: "Second Post"
date: 2023-02-24T15:02:10+01:00
draft: false
tags: ["tag1", "tag3"]
categories: ["cat1"]
---

## Münchenhausen trilemma
In epistemology, the Münchhausen trilemma is a thought experiment intended to demonstrate the theoretical impossibility of proving any truth, even in the fields of logic and mathematics, without appealing to accepted assumptions. If it is asked how any given proposition is known to be true, proof may be provided. Yet that same question can be asked of the proof, and any subsequent proof. The Münchhausen trilemma is that there are only three ways of completing a proof:

The circular argument, in which the proof of some proposition presupposes the truth of that very proposition
The regressive argument, in which each proof requires a further proof, ad infinitum
The dogmatic argument, which rests on accepted precepts which are merely asserted rather than defended
The trilemma, then, is the decision among the three equally unsatisfying options. Karl Popper's suggestion was to accept the trilemma as unsolvable and work with knowledge by way of conjecture and criticism.

## some code please

```cpp
// Fibonacci Series using Recursion
#include <bits/stdc++.h>
using namespace std;

int fib(int n)
{
	if (n <= 1)
		return n;
	return fib(n - 1) + fib(n - 2);
}

int main()
{
	int n = 9;
	cout << fib(n);
	getchar();
	return 0;
}

```

## mermaid

{{< mermaid >}}
graph LR;
A[Lemons]-->B[Lemonade];
B-->C[Profit]
{{< /mermaid >}}

## image to the article

{{< figure
    src="img/pexels-yaroslav-shuraev-1553963.jpeg"
    alt="Abstract purple artwork"
    caption="Photo by [Yaroslav Shuraev](https://www.pexels.com/photo/white-mountain-range-1553963/)"
    >}}