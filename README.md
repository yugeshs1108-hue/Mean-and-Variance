#  Mean and variance of a discrete  distribution


# Aim : 

To find mean and variance of arrival of objects from the feeder using probability distribution


# Software required :  

Python and Visual components tool

# Theory:

The expectation or the mean of a discrete random variable is a weighted average of all possible
values of the random variable. The weights are the probabilities associated with the corresponding values. 
It is calculated as,

![image](https://user-images.githubusercontent.com/103921593/192938463-e34177f4-f188-48a0-bda2-8f6d1d660ed2.png)

The variance of a random variable shows the variability or the scatterings of the random variables.
It shows the distance of a random variable from its mean. It is calcualted as

![image](https://user-images.githubusercontent.com/103921593/192938695-99fedc01-34d5-4d36-84df-5880e766ed0c.png)


# Procedure :

1. Construct frequency distribution for the data

2. Find the  probability distribution from frequency distribution.

3. Calculate mean using 
   
   ![image](https://user-images.githubusercontent.com/103921593/192940431-03b81777-c54d-4286-b4f4-82dfe7666b4c.png)

4. Find  
   
      ![image](https://user-images.githubusercontent.com/103921593/192940255-2d9dd746-6875-4a6d-877b-6da6cdb96ab1.png)

5.  Calculate variance using 
  
      ![image](https://user-images.githubusercontent.com/103921593/192942852-913550a9-fabe-4a55-b956-0487b18bbd97.png)


# Experiment :

![image](https://user-images.githubusercontent.com/103921593/229993174-5b67e57e-3e01-4ac4-9f83-410a932b22bf.png)

# Program :
Name: SANJAY SRISANTH V
Register No: 212225040375
import numpy as np

# Read the data
L = [int(i) for i in input("Enter the arrival data: ").split()]

# Number of observations
N = len(L)

# Maximum arrival value
M = max(L)

# Find frequency of each value
x = []
f = []

for i in range(M + 1):
    count = 0
    for j in range(N):
        if L[j] == i:
            count += 1

    x.append(i)
    f.append(count)

# Total frequency
Sf = np.sum(f)

# Probability
p = []

for i in range(M + 1):
    p.append(f[i] / Sf)

# Mean
mean = np.inner(x, p)

# E(X^2)
Ex2 = np.inner(np.square(x), p)

# Variance
var = Ex2 - mean ** 2

# Standard deviation
sd = np.sqrt(var)

# Display results
print(f"Mean arrival rate = {mean:.3f}")
print(f"Variance of arrival from feeder = {var:.3f}")
print(f"Standard deviation of arrival from feeder = {sd:.3f}")



# Output : 
Enter the arrival data: 12  9 8 6 32 9  
Mean arrival rate = 12.667
Variance of arrival from feeder = 77.889
Standard deviation of arrival from feeder = 8.825

# Results :
The mean and variance of arrivals of objects from feeder using probability distribution are calculated

