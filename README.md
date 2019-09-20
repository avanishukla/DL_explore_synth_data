# DL_explore_synth_data
Empirical and Theoretical Studies

## Sphere Shell Basic Analysis:
Analyse the training and success of Multilayer Perceptron for varying the distance between the positive and negative data, dimension of Sphere Shell binary data, and the number of nodes in the hidden layer.

<b>Dataset:</b>
Number of samples : 500 

<b>sphere_shell_binary_data.ipynb</b> file contains code to generate the data.
Methods used to generate data are:
1.	Compute n dimensional Cartesian coordinates using radial coordinate r, and n − 1 angular coordinates
2.	Generate n-dimensional gaussian distribution and get label for samples according to radius. 
3.	By direction chosen uniformly at random and a norm drawn uniformly at random from the interval [0,radius_of_shell+(thickness_of_shell/2)]

