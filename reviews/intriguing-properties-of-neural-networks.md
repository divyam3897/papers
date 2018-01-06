# Intriguing Properties of Neural Networks

Christian Szegedy, Wojciech Zaremba, Ilya Sutskever, Joan Bruna, Dumitru Erhan, Ian Goodfellow, Rob Fergus

## Summary

In this paper, two counter intutive properties of deep neural networks are discussed:  
- Semantic Meaning of Individual Units.  
  - Previous work analyzed the semantic meaning of various units by finding set of inputs that maximally activate a given unit.  
  - Authors observe that it is the entire space of activations, rather than individual units that contain bulk of semantic information.  
  - There is no distinction between individual high level units and random linear combination of high level units, it the space that contains the semantic information
  in the high layers of neural networks rather than the individual units.  

- Stability of neural networks with respect to small perturbations to their inputs
  - A deep neural network that generalizes well on an object recognition task is robust on small perturbations because small perturbations cannot change object category of an image.  
  - However, gradual non random perturbation to the test image can change the network's prediction.  
  - These perturbations are found by optimzing the input to maximize the prediction error.  
  - Authors call the perturbed examples as adversarial examples.  
  - It was observed that if we use one neural net to generate a set of adversarial examples, we find that these examples are still statistically hard for another
    neural network even when it was trained with different hyperparameters on a different set of examples.  
  - As you go to higher layers of the network, instability induced by adversarial instances increases.  

## Strengths
- The authors propose a way to improve generalization of models by backfeeding adversarial examples to training.  
- Adversarial examples are somewhat universal and not just the results of overfitting to a particular model or to the specific selection of the training set.  
- Adversarial examples tend to stay hard even for models trained with different hyperparameters, the autoencoder based version seems most resilient to adversarial examples,
  it is not fully immune either.  

# Weaknesses/Notes
- It's an intiguing concludion that adversarial examples remain hard for models trained even on a disjoint training set.  
- Doesn't explain why these examples generalize across different hyperparameters or training sets.  
- The existence of the adversarial negatives appears to be in contradiction with the network’s ability to achieve high generalization performance.  
