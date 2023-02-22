
**What is the output of this code and why?**
---

![practice](https://user-images.githubusercontent.com/110518958/220537039-b3b32d1e-3076-4143-bace-97d40d346b36.png)


---

I selected this question as it covers so many of concepts we have covered in our  Arewa Data Science 30 days of Python so far.

It can be summarised as follows:
1. range(1,6,2) is the sequence 1,3,5

2. arr is [1,3,5]

3. The change made to arr1 reflects in arr. So arr also becomes [1,3,5,10]

4. *arr, converts arr to tuple and returns (1,3,5,10)

The question covers the following topics: 
- range (day 10, introduced during loops)
- list comprehension (day 13)
- mutation (day 5, lists)
- unpacking (day 17)

range is a built-in function that helps in creating sequence of integers. It accepts three arguments; start, stop and step. Start is inclusive but stop is exclusive. In this question, range(1,6,2) gives the sequence of 1,3,5.

List comprehension: The list comprehension statement, arr = [x for x in range(1,6,2)], goes through each element in the sequence, range(1,6,2), and includes it in a list. Since it has been established that range(1,6,2) is 1,3,5 then arr is [1,3,5].

Mutation: This is a concept that is hard for most Python beginners like me to grasp. 
arr1 = arr does not make a copy of arr and put it in arr1, rather it gives an additional name, arr1 to the object named arr. This implies that the list [1,3,5] now has two names, arr and arr1. This is how assignment works in Python. So any change done to arr1 will reflect in arr and vice versa. Hence arr1.append(10) will add ten to the same list object referenced by both arr and arr1.

Unpacking: The final ingredient is the unpacking operator- asterisk. The functions returns *arr, and this is what we need to define. Unpacking means separating the items of an iterable, in this case the elements of the list arr. The question is then, what happens to the separated elements? If only *arr is run, an error is raised as the separated elements need to go into something e.g. list, tuple etc. So *arr will not work but [*arr] will work as the elements will be unpacked into a list. The code surrounding the operator determines where the output will be unpacked into. In our case, *arr, is given and the syntax for a tuple is an item followed by a comma. Therefore a tuple will be returned. 

In conclusion, the answer is C for all the reasons above. 

> Everyday I learn something new in my Data Science journey with Arewa Data Science Fellowship. Less than a month ago, I knew almost nothing in Python but right now, everyday my confidence is increasing when it comes to my Python skills. It is a pleasure to be a part of this and I am incredibly grateful to the mentors for the opportunity to be a part of this amazing journey. 





