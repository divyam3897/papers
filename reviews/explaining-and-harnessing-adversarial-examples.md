# Explaining and Harnessing Adversarial Examples
Ian J. Goodfellow, Jonathon Shlens & Christian Szegedy

## Body
- The authors showed that the earlier speculative hypothesis like extreme nonlinearity of deep neural networks, combined with insufficient model  
  averaging and insufficient regularization of the purely supervised learning problem suggested for adversarial examples were unnecessary.  
- Linear behavior in high-dimensional spaces is sufficient to cause adversarial examples.  
- Generic regularization strategies such as dropout, pretraining, and model averaging do not confer a significant reduction in a model’s
  vulnerability to adversarial examples, but changing to nonlinear model families such as RBF networks can do so.  

### Existence of adversarial examples for linear models  
 - The precision of an individual input feature is limited.  
 - Digital images often use only 8 bits per pixel so they discard all information below 1/255 of the dynamic range.  
 - Due to less precision, the classifier responds differently to an input x than to an adversarial input x̃ = x + η if every element of the perturbation
  η is smaller than the precision of the features.  
 - If w has n dimensions and the average magnitude of an element of the weight vector is m, then the activation will grow by mn.  
 - Thus for high dimensions, we can make many infinitesimal changes to the input that add up to one large change to the output.  

### Linear perturbation of non-linear models  
 - Authors hypothesize that neural networks are too linear to resist linear adversarial perturbation.  
 - LSTMs, ReLUs, and maxout networks are all intentionally designed to behave in very linear ways, so that they are easier to optimize.  
 - This linear behavior suggested that cheap, analytical perturbations of a linear model also damaged neural networks.  

## Summary
- Adversarial examples can be explained as a property of high-dimensional dot products.  
- They are a result of models being too linear, rather than too nonlinear.  
- The direction of perturbation, rather than the specific point in space, matters most.  
- Linear models lack the capacity to resist adversarial perturbation.  
- RBF networks are resistant to adversarial examples.  
