---
title: "The Cardinality of a Set and The Peano's Axioms"
date: 2022-07-08T16:00:21+01:00
draft: false
categories: ["Mathematics", "Musings"]
description: "Counting is one of the most intuitive concepts we learn and use frequently on daily basis. However, not everyone realises how difficult it is to formally describe counting. For instance ..."
tags: ["Counting", "Peano", "Nature-of-Mathematics"]
---

![Counting-is-Easy.-Says-Who.gif](https://img.ashwinbalaji.xyz/images/2023/02/25/Counting-is-Easy.-Says-Who.gif)

{{< alert >}}
**Warning!** This article is one among many salvaged from my previous blog! It is not on par with my demands of quality but I didn't feel like abandoning it. Please don't disappoint me by becoming fond of this.
{{< /alert >}}

{{< katex >}}

Counting is one of the most intuitive concepts we learn and use frequently on daily basis. However, not everyone realises how difficult it is to formally describe counting. For instance, take this example - when we see 5 fingers in one hand, we see 5 apples on a table etc we associate the equality of both groups and set the number 5 representing such an equivalence relation. Similar to number 2, we have 2 hands, 2 eyes, 2 ears, 2 legs, 2 wings etc and we associate a symbol 2 to represent the equivalence of the number of objects equalling 2 as number 2. But how do we actually count? This problem of the cardinality of a set is one of the difficult and confusing problems to tackle in Real Analysis.

First, we need to know how to equate two different sets. We say it intuitively in the above examples, but for a rigorous approach, we can say that if there is a function \\(f: A \to B \\) that is a bijection, then both sets A and B are having an equal number of elements. However, it turns out that finding bijection is difficult, so, another method is to find functions such that \\(f_1: A \to B \\) and \\(f_2: A \to B \\) where both \\(f_1\\) and \\(f_2\\) are injective, then the sets A and B are said to be of equal cardinality. But by how much? That we can do so only if we map an injection from set A to natural numbers and B to natural numbers. But what are natural numbers? We use them to count and we are in a quest to decide how we end up using them, but here we are, using them again to define counting.

I hope you get the frustration here. It is an intuitive process to count, but to define it formally we struggle badly. So, let’s formalise the Natural Numbers and observe if there are any inferences we could draw from such observation.

It was not until 1899 that the arithmetic of cardinal numbers was axiomatised, by the Italian mathematician Giuseppe Peano. His axioms are five in number. They are formulated with the help of three undefined terms, acquaintance with the latter being assumed. The terms are, '*number*', '*zero*' and '*immediate successor of*'. Peano’s axioms can be stated as follows:

1. Zero is a number.
1. The immediate successor of a number is a number.
1. Zero is not the immediate successor of the number.
1. No two numbers have the immediate successor.
1. Any property belonging to zero, and also to the immediate successor of every number that has the property, belongs to all numbers.
The last axiom formulates what is often called the "principle of mathematical induction".

We can easily imagine how to generate the Integer set from these axioms. We just have to modify the 3rd and add another axiom to support the existence of negative numbers. However, as we can see, the terms, 'number', 'zero' and 'immediate successor of' are given, and their meaning is taken for granted. So, we truly don’t have access to the understanding go what the numbers are in the first place. Is it like Plato’s world of math entities that exists between the mind and physical space of this world? Or, is it just an abstraction for our convenience and actually doesn’t exist? A lot of mathematicians and philosophers struggle to try to understand this question(answering is secondary). We can only hope for answers from them after their full-blown work in these areas.