# Pytorch Tips:
## difference between NLLLoss and CrossEntropyLoss:
Fundamentally same. 
For CrossEntropyLoss: log(softmax(inputs)) 
For NLLLoss:  nn.LogSoftmax(inputs)  
Example:                  
import torch           
import torch.nn as nn  
loss1 = nn.CrossEntropyLoss(reduction="none") 
loss2 = nn.NLLLoss(reduction="none")       
input = torch.randn(3,5)             
target = torch.empty(3, dtype=torch.long).random_(5)   
loss1(input, target)         
m = nn.LogSoftmax(dim=1)     
loss2(m(input), target)                     

## How is Pytorch’s binary_cross_entropy_with_logits function related to sigmoid and binary_cross_entropy
https://zhang-yang.medium.com/how-is-pytorchs-binary-cross-entropy-with-logits-function-related-to-sigmoid-and-d3bd8fb080e7
