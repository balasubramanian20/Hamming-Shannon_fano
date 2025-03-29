# Ex08 Huffman-Shannon_fano
## Date:29/03/25
### Aim
    Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
    Apply the Huffman and Shannon-Fano to this source Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
### Tools Required
    Personal computer
    Google colab software.
### Program
```
#Huffman and Shannon-Fano coding
import numpy as np
import math 
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n): 
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    p.append(pr)
for j in range (n): 
    l = float(input(f"Enter the length of the sample values {j + 1}: "))  
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy 
red =  round(1 - eff,3) 
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
### Calculation
![Screenshot 2025-03-29 192604](https://github.com/user-attachments/assets/3c0cdf3a-747f-4c90-bdbb-7686e4e57354)
![WhatsApp Image 2025-03-29 at 19 44 47_8b867646](https://github.com/user-attachments/assets/3df0580d-0c21-4c1d-984d-e6bd91895568)
![WhatsApp Image 2025-03-29 at 19 44 49_384b0fd5](https://github.com/user-attachments/assets/b3948835-48fc-42b3-a1ea-7e927bc71c4e)
### Results
    The given probabilities 0.125,0.0625,0.25,0.0625,0.125,0.125,0.25 Average Codeword Length is : 2.625 Entropy is : 2.625 Efficiency is : 100.0 % Redudancy is : 0.0 Variance is : 0.484
