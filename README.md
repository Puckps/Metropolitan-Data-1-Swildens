# Metropolitan Data1 Swildens
## MSc MADE Amsterdam - Puck Swildens - September 2024

**WK 1**

---

For the first week of Metropolitan Data 1 we took a look at the first steps in Python

### Exercise 1
**Write a properly documented function with the following behaviour:**

- It has a meaningful name (i.e. it is related to its behaviour).
- It takes an integer that represents the length of a sequence that will be created.
- It creates a dictionary that is empty.
- It loops over the sequence and stores each number as the key of an entry in the dictionary, assigning either "odd" or "even" to the value, depending on the type of number.

- Returns the dictionary.

      def define_even_or_odd(len_seq):
  
          even_odd_dict = {}
  
          for i in range(0, len_seq + 1):
      
              if i % 2 == 0:
                  even_odd_dict[i] = "even"
              else:
                  even_odd_dict[i] = "odd"
  
          return even_odd_dict
___
### Exercise 2
**Create a tuple called `tup` with the following seven objects:**

- The first element is an integer of your choice
- The second element is a float of your choice  
- The third element is the sum of the first two elements
- The fourth element is the difference of the first two elements
- The fifth element is the first element divided by the second element

- Display the output of `tup`.  What is the type of the variable `tup`? What happens if you try and chage an item in the tuple?
  
   ```
    first_element = 64
    second_element = 5.67
    third_element = first_element + second_element
    fourth_element = first_element - second_element
    fifth_element = first_element / second_element
    
    tup = (first_element, second_element, third_element, fourth_element, fifth_element)
   ``` 
___
### Exercise 3
**Build a list that contains every prime number between 1 and 100, in two different ways:**
    
1. Using for loops and conditional if statements.

2. **(Stretch Goal)** Using a list comprehension.  You should be able to do this in one line of code. **Hint:** it might help to look up the function `all()` in the documentation.

```
# way 1
def list_primes_one(len_seq):

    prime_numbers = []
    list_numbers = range(2, len_seq + 1)

    for i in list_numbers:

        for j in range(2, i):
            if (i % j) == 0:
                break
        else:
            prime_numbers.append(i)
        
    return prime_numbers
    

# way 2
def list_primes_two(len_seq):

    prime_numbers = [i for i in range(2, len_seq + 1) if all(i % j != 0 for j in range(2, i))]

    return prime_numbers
```
___
### Exercise 4
**Write a function to test the "prime-ness" of a number.**
    
In Exercise 4, above, you wrote code that generated a list of the prime numbers between 1 and 100. Now, write a function called `isprime()` that takes in a positive integer $N$, and determines whether or not it is prime.  Return `True` if it's prime and return `False` if it isn't. Then, using a list comprehension and `isprime()`, create a list `myprimes` that contains all the prime numbers less than 100.  

```
def isprime(N):

    for i in range(2, N):
        if (N % i) == 0:
            return False     
        
    return True
        
    
def list_primes_two(len_seq):

    myprimes = [i for i in range(2, len_seq) if isprime(i)]

    return myprimes
```

