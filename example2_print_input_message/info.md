## Containerising a Print function with input text

In this quick tutorial, we will learn how to containerise a function able to print a text that we write as input. This is important because later we can create for example, big preprocessing workflows as micro-containers, where each container represent a small part of the whole preprocessing block.

Let's start with a simple Python script that prints a text that write as input. The code is available in `.py` and it can be as follows:

```commandline
in_v = input('write something to print in the container: ')
print(f'text written:\n{in_v}')
```