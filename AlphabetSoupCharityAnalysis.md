# Overview

The purpose of this analysis is to detail how the deep learning model for Alphabet Soup was constructed and what attempts were made to optimize it accuracy.

# Results

--Data Preprocessing:

    --Target Variable: IS_SUCCESSFUL
    --Feature Variables: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
    --Variables to Be Removed: EIN, NAME

IS_SUCCESSFUL appears to be the most reasonable candidate for the target since a charity being successful would probably be what Alphabet Soup would be most interested in when considering who to fund. EIN and NAME are columns used only to identify the different charities. They have no relevance to whether or not a charity is successful. After a lot of experimentation, it was discovered that eliminating other columns compromised the accuracy of the model. Thus, all the remaining columns were left intact.

--Compiling, Training, and Evaluating the Model:

    --Model: tf.keras.models.Sequential()
    --Number of Input Features: len(X_train[0])
    --First Layer: 
        --Nodes: 8
        --Activation Function: relu
    --Second Layer:
        --Nodes: 5
        --Activation Function: relu
    --Third Layer:
        --Nodes: 5
        --Activation Function: relu
    --Output Layer:
        --Nodes: 1
        --Activation Function: sigmoid
    --Epochs: 100
    --Random State: 42
    --Test Size: 0.25
    --Cutoff for APPLICATION_TYPE: 100
    --Cutoff for CLASSIFICATION: 100

    

    This is the setup for the optimized version of my model. No amount of experimentation enabled much of a noticeable rise in accuracy. I tried adding layers, taking away layers`, increasing the number of epochs, decreasing the number of epochs, eliminating more columns, changing the activation functions, adding neurons, taking away neurons, and changing the test size. Most of the time the accuracy decreased. Even if all these factors are held constant, different levels of accuracy can be reported each time the model is run, although the differences are not huge. That said, I was able to modify the model to get a slightly higher level of accuracy, but not by much. I can't seem to get the accuracy much above 73%.
    
    When constructing the initial model, I made use of the code used to construct the model used in one of the activities in the class session. I used that as a starting point and proceeded from there.

# Summary

The deep learning model's accuracy doesn't rise much above 73%. A deeper, more nuanced understanding of the techniques used to optimize deep learning models, along with more time, would likely help in alleviating this problem. I think a model that accounts for fewer columns, uses more neurons and layers, and uses different activation functions might achieve greater accuracy. To create such a model, I would need to better understand:

    --what features are unnecessary, 
    --the inner workings of the neurons and layers
    --the mathematics of the functions, and
    --how the algorithms link everything together.

I really don't believe that a specific recommendation for a model is possible with my level of knowledge, so I can only describe what such a model might look like in general.

Screenshots showing the original model and its accuracy, along with 3 of my many attempts to optimize the model and the accuracy of each attempt, are included in the repository. The names on the image files are fairly self-explanatory. The original version of this model, including each of the featured optimization attempts, use 100 epochs, the same cutoff values, and there are no differences in which columns are used. Once again, featured here are only 3 of my attempts to optimize the model.