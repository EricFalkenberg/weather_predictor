LAB WRITEUP
======
This program will accept the following flags

1. train
2. testtraining
3. predict

### PROGRAM BEHAVIOR:

    If either testtraining or predict is chosen the program will load the optimal model from learned_model 
    which used 6 hidden nodes and learned to a threshold of 0.11 average error on the training set.
    Otherwise, the program will call network() and train a new model. Once that model has been trained 
    the program will run both the test and training sets through the network and give corresponding 
    performance metrics.

    If predict is chosen, the program will prompt for each attribute needed individually via standard input.
    The inputs are expected to have already been standardized.

### DATASET:
    The program reads from two files (test_in.csv and test_out.csv) of which are split into the training
    and testing set. The training set is  made up of the first two thirds of each file and the testing set
    is made up of the last third. All data in the input set has been standardized (useing standard deviation
    and mean) and all data in the output set has been formatted such that it adheres to the following 
    guidelines:
    
        0.0:    It is neither snowing nor raining
        0.333:  It is raining but not snowing
        0.666:  It is snowing but not raining
        1.0:    It is both raining and snowing

    
    (NOTE: This would be better suited via a multi-ouput network. A good deal of accuracy is lost when
           attempting to predict binary output via one continuous output.)
    I calculated this based off of whether or not there were non-zero values in SNWD and PRCP for any 
    given row.

### REMARKS:
    Overall, the network seemed to perform decently in predicting whether it would rain / snow. Most of 
    the time, if it didnt make a correct classification, it came close (i.e predicting snow when it was 
    both snowing and raining). The optimal network had 6 hidden nodes and a learning rate of 0.11 which 
    acheived prediction figures of 64.88% absolutely correct prediction on the training set and 52% for 
    the testing set.
