---
layout: post
title:  "Notas de la clase de introducción a la programación reactiva"
date:   2015-11-2 22:00:50
categories: personal beer
---

En sistemas tradicionales: los sitemas estan compuestos de multiples hilos, los cuales se comunican para compartir, sincronizar estados
systems are compose from loosely coupled event handlers
Ahora: los sistemas se componen de controladores de evento debilmente acoplados
Los eventos pueden manejarse de manera asincrona, sin bloqueo.

An Application is scalable if it is able to be expanded according to its usage

Una aplicación es escalable si esta es capaz de expandirese  de acuerdo a su uso.


Scale up : make use of parallelism in multi-core systems
Scale down: make use of multiple server nodes.

Important for scalability:  Minimize shared mutable state.
Important for scale out: Location Transparency, resilience.


An Application is ##Resilient## if it can recover qucky from failures 
Failures can be
-software failures
hardware failures 
connection failures




A continuación les copio y pego  lo que serian las soluciones oficiales que dan sus respectivos autores, esperando que les sirva para  que manden su solución al evaluador.

En está ocasión no traduciré la solución para evitar alguna desambiguación.

Note, that if the array has two intersecting continuous non-decreasing subsequence, they can be combined into one. Therefore, you can just pass the array from left to right. If the current subsequence can be continued using the i-th element, then we do it, otherwise we start a new one. The answer is the maximum subsequence of all the found ones.

Asymptotics — O(n).
Source: [Kefa and First Steps]
{% highlight C %}
#include<stdio.h>
int array[100003];
int main(){
  int n,i,max,count;
  scanf("%d",&n);
  for( i =0; i< n; i++)
    scanf("%d", &array[i]);
  max = count =1;
  for(i =1; i < n ; i++){
    if(array[i] >= array[i-1])
      count++;
    else if(max < count){
      max = count;
      count =1;
    }else count =1;

  }
  if(max < count) max = count;
  printf("%d",max);


return 0;
}
{% endhighlight %}



It's easy to see that number x can appear in column i only once — in row x / i. For every column i, let's check that x divides i and x / i ≤ n. If all requirements are met, we'll update the answer.

The complexity is O(n)
Source: [Multiplication Table]



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
