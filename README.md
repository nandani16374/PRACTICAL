# _Practicals

# 1.roots of an equation 

import math


# Quadratic equation: ax² + bx + c = 0

a = 1

b = -3

c = 2


d = b**2 - 4*a*c


if d > 0:

    root1 = (-b + math.sqrt(d)) / (2*a)
    
    root2 = (-b - math.sqrt(d)) / (2*a)
    
    print("Real and distinct roots:", root1, "and", root2)
    
elif d == 0:

    root = -b / (2*a)
    
    print("Real and equal roots:", root)
    
else:

    realPart = -b / (2*a)
    
    imagPart = math.sqrt(abs(d)) / (2*a)
    
    print(f"Complex roots: {realPart}+{imagPart}i and {realPart}-{imagPart}i")
    

      _________output__________

      

Real and distinct roots: 2.0 and 1.0




# 2. finding prime number 



def is_prime(num):

    if num < 2:
    
        return False
        
    for i in range(2, int(num**0.5)+1):
    
        if num % i == 0:
        
            return False
            
    return True
    

def primes_till_n(n):

    return [i for i in range(2, n+1) if is_prime(i)]
    

def first_n_primes(n):

    primes = []
    
    num = 2
    
    while len(primes) < n:
    
        if is_prime(num):
        
            primes.append(num)
            
        num += 1
        
    return primes
    

n = 10

print(n, "is prime?", is_prime(n))

print("Prime numbers till", n, ":", primes_till_n(n))

print("First", n, "prime numbers:", first_n_primes(n))



     _________output________
     


10 is prime? False

Prime numbers till 10 : [2, 3, 5, 7]

First 10 prime numbers: [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]




# 3. pyramid pattern



rows = int(input("Enter number of rows: "))


# Pyramid

print("Pyramid Pattern:")

for i in range(1, rows + 1):

    print(" " * (rows - i) + "* " * i)
    

# Reverse Pyramid

print("\nReverse Pyramid Pattern:")

for i in range(rows, 0, -1):

    print(" " * (rows - i) + "* " * i)
    


      ______output_______
      

# for 4 rows 

Pyramid Pattern:

   *
   
  * *
    
 * * * 
 
* * * * 


Reverse Pyramid Pattern:

* * * * 

 * * * 

  * *

   *






# 4. entering a character and operations on the same 




ch = input("Enter any character: ")


if ch.isalpha():

    print("It is a letter.")
    
    if ch.isupper():
    
        print("It is uppercase.")
        
    else:
    
        print("It is lowercase.")
        
elif ch.isdigit():

    print("It is a numeric digit.")
    
    num_names = {
    
        '0': 'ZERO', '1': 'ONE', '2': 'TWO', '3': 'THREE',
        
        '4': 'FOUR', '5': 'FIVE', '6': 'SIX', '7': 'SEVEN',
        
        '8': 'EIGHT', '9': 'NINE'
        
    }
    
    print("Digit in words:", num_names[ch])
    
else:

    print("It is a special character.")
    



       _______output________
       



     for ch=9 


It is a numeric digit.

Digit in words: NINE




# 5. String Operations



s = input("Enter a string: ")


# a) Frequency of a character

ch = input("Enter character to find frequency: ")

print("Frequency of", ch, ":", s.count(ch))


# b) Replace a character

old = input("Enter character to replace: ")

new = input("Enter new character: ")

print("String after replacement:", s.replace(old, new))


# c) Remove first occurrence

ch = input("Enter character to remove first occurrence: ")

print("After removing first occurrence:", s.replace(ch, '', 1))


# d) Remove all occurrences

ch = input("Enter character to remove all occurrences: ")

print("After removing all occurrences:", s.replace(ch, ''))



      _____output_____
      


    for s= banana


s = "banana"


print("Frequency of 'a':", s.count('a'))

print("Replace 'a' with 'o':", s.replace('a', 'o'))

print("Remove first occurrence of 'a':", s.replace('a', '', 1))

print("Remove all occurrences of 'a':", s.replace('a', ''))



Frequency of 'a': 3

Replace 'a' with 'o': bonono

Remove first occurrence of 'a': bnana

Remove all occurrences of 'a': bnn






# 6. swap function 




str1 = "Hello"

str2 = "World"

n = 2


new_str1 = str2[:n] + str1[n:]

new_str2 = str1[:n] + str2[n:]


print("After swapping:")

print("String 1:", new_str1)

print("String 2:", new_str2)



       _____output_____



After swapping:

String 1: Werlo

String 2: Holld




# 7. indices program




def find_indices(s1, s2):

    indices = []
    
    start = 0
    
    while True:
    
        pos = s1.find(s2, start)
        
        if pos == -1:
        
            break
            
        indices.append(pos)
        
        start = pos + 1
        
    return indices if indices else -1
    

print(find_indices("banana", "an"))




          _____output_____
          


[1, 3]






# 8. list operations




lst = [1, 2, 3, 4, 'a', 6, 8.5, 10]

cubes = []

for i in lst:

    if isinstance(i, int) and i % 2 == 0:
    
        cubes.append(i**3)
        
print("Cubes of even integers (for loop):", cubes)


lst = [1, 2, 3, 4, 'a', 6, 8.5, 10]

cubes = [i**3 for i in lst if isinstance(i, int) and i % 2 == 0]

print("Cubes of even integers (list comprehension):", cubes)




     ______output______
     



Cubes of even integers (for loop): [8, 64, 216, 1000]

Cubes of even integers (list comprehension): [8, 64, 216, 1000]




# 9. file operations 



'''

SAMPLE TEXT


Hello world

Python is fun

File handling 

'''




filename = "sample.txt"


with open(filename, 'r') as f:

    lines = f.readlines()
    

char_count = sum(len(line) for line in lines)

word_count = sum(len(line.split()) for line in lines)

line_count = len(lines)


print("Characters:", char_count)

print("Words:", word_count)

print("Lines:", line_count)


# Frequency of each character

freq = {}

for line in lines:

    for ch in line:
    
        freq[ch] = freq.get(ch, 0) + 1
        
print("Character frequency:", freq)


# Words in reverse order

words = []

for line in lines:

    words.extend(line.split())
    
print("Words in reverse:", ' '.join(words[::-1]))


# Copy even/odd lines

with open('File1.txt', 'w') as even, open('File2.txt', 'w') as odd:

    for i, line in enumerate(lines, 1):
    
        if i % 2 == 0:
        
            even.write(line)
            
        else:
        
            odd.write(line)
            




                   _____output_____



Characters: 37

Words: 6

Lines: 3

Character frequency: {'H':1,'e':3,'l':6,'o':2,' 

':4,'w':1,'r':1,'d':2,'P':1,'y':1,'t':1,'h':1,'n':1,'i':3,'s':1,'f':1,'u':1,'F':1,'a':1,'g':1,'\n':2}

Words in reverse: handling File fun is Python world Hello





# 10. Class Function 



import math


class Point:

    def __init__(self, x, y):
    
        self.x = x
        
        self.y = y
        

    def __str__(self):
    
        return f"({self.x}, {self.y})"
        

    def distance(self, other):
    
        return math.sqrt((self.x - other.x)**2 + (self.y - other.y)**2)
        

p1 = Point(3, 4)

p2 = Point(7, 8)

print("Point 1:", p1)

print("Point 2:", p2)

print("Distance:", p1.distance(p2))




        ______output______



Point 1: (3, 4)

Point 2: (7, 8)

Distance: 5.656854249492381




# 11. Dictionary functions



def cube_dict():

    d = {x: x**3 for x in range(1, 6)}
    
    print(d)
    

cube_dict()




       _____output_____
       


{1: 1, 2: 8, 3: 27, 4: 64, 5: 125}





# 12. Tuple Operations




t1 = (1, 2, 5, 7, 9, 2, 4, 6, 8, 10)

half = len(t1)//2

print("First half:", t1[:half])

print("Second half:", t1[half:])


even_tuple = tuple(i for i in t1 if i % 2 == 0)

print("Even tuple:", even_tuple)


t2 = (11, 13, 15)

t3 = t1 + t2

print("Concatenated:", t3)

print("Max:", max(t3))

print("Min:", min(t3))




       ______output______
       



First half: (1, 2, 5, 7, 9)

Second half: (2, 4, 6, 8, 10)

Even tuple: (2, 2, 4, 6, 8, 10)

Concatenated: (1, 2, 5, 7, 9, 2, 4, 6, 8, 10, 11, 13, 15)

Max: 15

Min: 1




# 13. Exception Handling 




try:

    name = "Aman@123"
    
    if not name.isalpha():
    
        raise ValueError("Name should contain only alphabets.")
        
    print("Valid name:", name)
    
except ValueError as e:

    print("Error:", e)
    




    _____output_____
    



Error: Name should contain only alphabets.






 ------------END-------------
 







                   


