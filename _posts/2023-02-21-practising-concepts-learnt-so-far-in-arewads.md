
**What is the output of this code and why?**
---

![What is the output of this code and why?](/resources/practice.png)


I selected this question as it covers many concepts we have covered in our  Arewa Data Science 30 days of Python so far.

It can be summarised as follows:
1. range(1,6,2) is the sequence 1,3,5

2. arr is [1,3,5]

3. The change made to arr1 reflects in arr. So arr also becomes [1,3,5,10]

4. *arr, converts arr to tuple and returns

The question covers the following topics
- range (day 10, introduced during loops)
- list comprehension (day 13)
- mutation (day 5, lists)
- unpacking (day 17)

range is a built-in function that helps in creating sequence of integers. It accepts three arguments; start, stop and step. Start is inclusive but stop is exclusive. In this question, range(1,6,2) gives the sequence of 1,3,5.

List comprehension The list comprehension statement, arr = [x for x in range(1,6,2)], goes through each element in the sequence range(1,6,2), and includes it in a list. Since it has been established that range(1,6,2) is 1,3,5 then arr ia [1,3,5].

Mutation: This is a concept that is hard for most Python beginners like me to grasp. 
arr1 = arr does not make a copy of arr and put it in arr1, rather it gives an additional name, arr1 to the object named arr. This implies that the list [1,3,5] now has two names, arr and arr1. This is how assignment works in Python. So any change done to arr1 will reflect in arr and vice versa. Hence arr1.append(10) will add ten to the same list object referenced by both arr and arr1




