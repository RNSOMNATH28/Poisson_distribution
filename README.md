# Fitting Poisson  distribution
# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Experiment :

![image](https://user-images.githubusercontent.com/103921593/230282876-f4a5afbf-cac1-4648-a1b0-c78840638a8e.png)

# Program :

 ```
import numpy as np
import math
x = np.array([0, 1, 2, 3, 4, 5])
fo = np.array([8, 15, 20, 12, 4, 1])
N = np.sum(fo)
lam = np.sum(x * fo) / N
fe = []
for i in x:
    p = (math.exp(-lam) * (lam ** i)) / math.factorial(i)
    fe.append(N * p)
fe = np.array(fe)
chi_square = np.sum(((fo - fe) ** 2) / fe)
table_value = 9.488 
print("Mean (λ) =", round(lam, 4))
print("Observed Frequencies :", fo)
print("Expected Frequencies :", np.round(fe, 2))
print("Calculated Chi-Square Value =", round(chi_square, 4))
print("Table Chi-Square Value =", table_value)

if chi_square < table_value:
    print("Poisson distribution is fitted for the given data.")
else:
    print("Poisson distribution is NOT fitted for the given data.")
    
```

# Output : 

<img width="662" height="182" alt="image" src="https://github.com/user-attachments/assets/fe0834be-4144-47db-9aa2-f38d3d3567d6" />


# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
