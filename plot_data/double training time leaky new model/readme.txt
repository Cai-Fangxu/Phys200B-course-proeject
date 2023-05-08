time delay dim = 10
time delay = 10
time step = 0.02 ms
# nearest neighbor for sigma = 8
double training time
stimulus rescale factor = 1, 2, 4, 6
all the stimulus has the same shape

new model: one extra layer of 10 neurons to preprocess I_{history}

leaky mlp: extra outpute terms: A-B*V(t), A and B are trainable parameters. (B ends up being negative, not good!)
beta = 0.01

leaky RBF: extra "RBF basis": 1, V(t) => extra "RBF weights" A and B. Here, A and B are fixed during back propagation. 
for each rescale factor, beta is chose so that the leaky term A+Bx has a negative B (of order -0.1).
rescale factor = 1, beta = 1
rescale factor = 2, beta = 0.01
rescale factor = 4, beta = 1
rescale factor = 6, beta = 0.1
