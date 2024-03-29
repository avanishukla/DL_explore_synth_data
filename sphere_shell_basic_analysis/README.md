## Sphere Shell Basic Analysis:
Analyse the training and success of Multilayer Perceptron for varying the distance between the positive and negative data, dimension of Sphere Shell binary data, and the number of nodes in the hidden layer.

### Sphere Shell Dataset:
**sphere_shell_binary_data.ipynb** file contains code to generate the data. <br>
Number of samples : 500 <br>
sp : radius of Sphere <br>
rs : radius of Shell <br>
t : thickness of shell <br>
dim : dimension <br>

train\_sp{value}\_sh{value}\_t{value}\_{value}dim.csv (for example: train_sp1_sh1.2_t1_2dim.csv) data file contains 500 rows and dim+1 columns generated by the code. 

Methods used to generate the data are: <br>
- **Version 1 :**	Compute n dimensional Cartesian coordinates using radial coordinate r, and n − 1 angular coordinates drawn uniformly at random. <br>
- **Version 2 :** Generate n-dimensional gaussian distribution and get labels for sample according to radius. <br> 
- **Version 3 :** Generate n-dimensional point by direction chosen uniformly at random and a norm drawn uniformly at random from the interval [0,radius_of_shell+(thickness_of_shell/2)]. Get labels for sample according to radius. <br> 

### Model:
**MLP.ipynb** file contains Model and training code. 

**plot_code.ipynb** file contains code to visualize following result.
- All trained model's accuracy, cost and number of epoches with model details are stored in json file as **list of dictionaries**. <br>
  dict format: {'sphere_radius': , 'shell_radius': , 'thickness' : , 'dimension': , 'n_nodes': , 'random_seed': , 'epoch': , 'accuracy':   , 'cost':}
- To plot loss vs epoch graph, **dictionary** with model name as key and 2D list as value is stored in json format.   
  {'sh'+{value}+'dim'+{value}+'h'+{value}+'i'+{value} : [[{epoch},{loss}]]* Number of epochs } 
  one example of a key is 'sh1.2dim2h3i1000'. 

### Experiments Performed and Result (sphere_shell_basic_analysis) : 

**Experiment 1** <br>
- Dataset Used : sphere shell data version1 <br>
  points_dim = [2, 3, 4, 5, 6] <br>
  radius_of_sphere = 1 <br>
  radius_of_shell = [1.6, 1.8, 2, 2.4] <br>
  thickness_of_shell = 1 <br>
- Model Used : <br>
  Random_seed = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000] <br>
  N_nodes = [dim, dim+1, dim+3, dim+5, dim+7, dim+9] <br>
  Hidden layer : 1 <br>
- **Result stored in : result.json**

**Experiment 2** <br>
- Dataset Used : sphere shell data version1 <br>
  points_dim = [2, 4, 8, 16, 32] <br>
  radius_of_sphere = 1 <br>
  radius_of_shell = [1.6, 1.8, 2, 2.2, 2.4] <br>
  thickness_of_shell = 1 <br>
- Moddel Used : <br>
  Random_seed = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000] <br>
  N_nodes = [dim, dim+2, dim+4, dim+8, dim+16, dim+32] <br>
  Hidden layer : 1, 2 <br>
- **Result stored in : result2.json**

**Experiment 3** <br>
- Dataset Used : sphere shell data version2 <br>
  points_dim = [2, 4, 8, 16, 32] <br>
  radius_of_sphere = 1 <br>
  radius_of_shell = [1.2, 1.4, 1.6, 1.8, 2] <br>
  thickness_of_shell = 1 <br>
- Moddel Used : <br>
  Random_seed = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000] <br>
  N_nodes = [2, 3, 4, 6, 8, 12, 16, 24, 32, 48, 64] <br>
  Hidden layer : 1, 2 <br>
- **Result stored in : gaussian_result.json**

**Experiment 4** <br>
- Dataset Used : sphere shell data version3 <br>
  points_dim = [2, 4, 8, 16, 32] <br>
  radius_of_sphere = 1 <br>
  radius_of_shell = [1.2, 1.4, 1.5, 1.6, 1.8, 2] <br>
  thickness_of_shell = 1 <br>
- Moddel Used : <br>
  Random_seed = [100, 200, 300, 400, 500, 600, 700, 800, 900, 1000] <br>
  N_nodes = [2, 3, 4, 6, 8, 12, 16, 24, 32, 48, 64] <br>
  Hidden layer : 1, 2 <br>
- **Result stored in : uniform_result.json** and **loss_uniform.json** to plot loss vs epoch graph.

Only difference between two Experiments (3 and 4) is dataset used and shell radius 1.5 included in experiment 4.
Report sphere_shell_basic_analysis_report.docx contains detailed result of trained models and inferences.
