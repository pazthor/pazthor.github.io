---
layout: post
title:  "Descripción de los problemas resueltos : primer semana"
date:   2015-06-12 22:00:50
categories: personal beer
---
A continuación les copio y pego  lo que serian las soluciones oficiales que dan sus respectivos autores, esperando que les sirva para  que manden su solución al evaluador.

En está ocasión no traduciré la solución para evitar alguna desambiguación.

Note, that if the array has two intersecting continuous non-decreasing subsequence, they can be combined into one. Therefore, you can just pass the array from left to right. If the current subsequence can be continued using the i-th element, then we do it, otherwise we start a new one. The answer is the maximum subsequence of all the found ones.

Asymptotics — O(n).
Source: [Kefa and First Steps]



It's easy to see that number x can appear in column i only once — in row x / i. For every column i, let's check that x divides i and x / i ≤ n. If all requirements are met, we'll update the answer.

The complexity is O(n)
Source: [Multiplication Table]

{% gist pazthor/be5c66f77eca71a1a8b6  %}

{% highlight c %}
#include<stdio.h>

int main(){
  int n,i, x,j;
  int count = j=0;

  scanf("%d %d", &n, &x);
  if (x <= n) count++;
  for( i = 2 ;i <= n ; i++){

    j = x / i;
    if( (j * i) == x && j <= n )   count++;

  }
  printf("%d\n", count);


  return 0;
}

{%endhighlight %}


[Multiplication Table]: http://codeforces.com/blog/entry/20226
[Kefa and First Steps]: http://codeforces.com/blog/entry/20468
