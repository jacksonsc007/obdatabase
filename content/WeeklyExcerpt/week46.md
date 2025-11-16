The upper trajectory ==skirts== the unsafe region along its left and top sides, and thus is safe. The lower trajectory crosses the unsafe region, and thus is unsafe.

“Notice that the unsafe region abuts, but does not include, the states along its perimeter” (Bryant and O'Hallaron, 2016, p. 1036)


We see that running time decreases as we increase the number of threads, up to four threads, at which point it levels off and even starts to increase a little.



You probably noticed that life ==got much more complicated== once we were asked to synchronize accesses to shared data. So far, we have looked at techniques for mutual exclusion and producer-consumer synchronization, but this is ==only the tip of the iceberg==. Synchronization is a fundamentally difficult problem that raises issues that simply do not arise in ordinary sequential programs. This section is a survey (by no means complete) of some of the issues you need to be aware of when you write concurrent programs==. To keep things concrete, we will couch our== discussion in terms of threads. Keep in mind, however, that these are typical of the issues that arise when concurrent flows of any kind manipulate shared resources.


On our system it fails, but on other systems it might work correctly, leaving the programmer ==blissfully== unaware of a serious bug.

From this graph, we can ==glean== some important insights about deadlock


Deadlock is an especially difficult issue because it is not always predictable. Some lucky execution trajectories will ==skirt== the deadlock region, while others will ==be trapped by== it.


We used a concurrent network server as the ==motivating== application ==throughout==.

```
2	during the whole of a period of time or an event 在整个期间；自始至终；从头到尾

- House prices continued to rise throughout the 1980s. 在整个20世纪80年代，房价持续上涨。
- There was a terrible scandal, but my family and friends supported me throughout. 丑闻闹得沸沸扬扬，但我的家人和朋友始终支持着我。
```


Unfortunately, programmers are often reluctant to do error checking because it ==clutters== their code, turning a single line of code into a multi-line conditional statement.

![[Pasted image 20251116215230.png]]





![[Pasted image 20251117073322.png]]




