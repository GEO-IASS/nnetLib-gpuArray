nnetLib-gpuArray
================

Fast deep neural network with adaptive learning rate AdaGrad and AdaDec using gpuArray

This project was forked from Nicolas Le Roux's nnetLib which you can find on [his website](http://nicolas.le-roux.name/code.html)
 and (MATLAB Central File Exchange)[http://www.mathworks.com/matlabcentral/fileexchange/authors/226827].
 
 The major improvements are porting to GPU and adding adaptive learning rate.
 
 Training deep neural network on GPU is more than 10 times faster than on CPU. So we can experiment and tuning various algorithms
 in fast iterative cycles.
 
 Adaptive learning rate scheduling policies set parameter wise learning rate based on the gradient histories of each parameter.
 AdaGrad uses 1 ./ sqrt(K + sum(gradient_histories .^ 2)). AdaDec extends AdaGrad by introduces forgetting factor to do exponential averaging
 of the sum of squared gradients. The denominator becomes sqrt(K + S_t(gradient_histories)) in which 
 S_t = forgetting_factor * S_t-1 + sum_k=0^n(gradient_k .^ 2).