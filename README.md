# Neural Networks Challenge

## Solution

- Parts 1-2
    - [AlphabetSoupCharity.ipynb](solution/AlphabetSoupCharity.ipynb)
- Part 3
    - [Attempt_1](solution/AlphabetSoupCharity_optimize_attempt_1.ipynb)
    - [Attempt_2](solution/AlphabetSoupCharity_optimize_attempt_2.ipynb)
    - [Attempt_3](solution/AlphabetSoupCharity_optimize_attempt_3.ipynb)

## Report 

1. **Overview:** The purpose of this analysis was to use past data to help Alphabet Soup select companies with the best chance of success to give their funding to.  This data contains the company EIN, the company name, the company affiliation, the company organization classification, the use case that the company would use the funding for, the status of the company, the income level of the company, special considerations for the company's application, the ask amount, and if the company was successful or not.  With this, the data was split up into training and testing groups, so that a neural network could be trained and evaluated.  The idea is that with a well-optimized neural network, Alphabet could feed the network new company applications and quickly determine if they would be successful or not.
2. **Results:**
    - Data preprocessing
        - The targets for the model were the "IS_SUCCESSFUL" column from the data.
        - The features for the model included the "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", and "ASK_AMT" columns.
        - The variables that were removed from the data, due to the fact that they were neither targets nor features, were the "EIN" and "NAME" columns.
    - Compiling, training, and evaluating the model
        - For the parameters of the network, I tried three different methods:
            1. Attempt 1 parameters
                - Input layer and an output layer 
                - Three hidden layers of sizes 128, 64, and 32, respectively.  I did this because I figured increasing the networks complexity by adding another layer would enable it to better classify the company's applications.
                - Using sigmoid for all of the activation functions.  I decided to do this because sigmoid's graph is curved and I figured this would help with making more accurate predictions.
            2. Attempt 2 parameters 
                - Input layer and an output layer 
                - Three hidden layers of sizes (128, 64, and 32).  I did this for the same reason as stated before
                - For the activation functions, I used ReLU for the first hidden layer and sigmoid for the rest.  I did this because after seeing the results from using sigmoid for all the activation functions, I figured the ReLU function's rigidness could be helpful in the model.
            3. Attempt 3 parameters
                - Input layer and an output layer 
                - Four hidden layers of sizes (128, 64, 32, and 16).  After seeing an improvement with using ReLU as the activation function for the first hidden layer and sigmoid as the activision function for the rest of the layers, I decided to try adding another layer, as I felt that increasing the total number of neurons in the network would increase the robustness of the neural network.
                - I again used ReLU for the first hidden layer and sigmoid for the rest.
        - Unfortuantely, I did not acheive the target performance.  The best accuracy I acheive was with my second optimization attempt, where I received an accuracy of 73\%

3. **Summary:** The overall results of the deep learning model I implemented led to an accuracy of 73\%.  To achieve this score, I primarily tweaked the number of layers in the network, the number of neurons in the network, and the activation functions used within each hidden layer of the network.  Other methods could also be taken to boost accuracy scores like using a different optimizer, considering different activation functions, increasing or decreasing the number of features used from the data, implementing more hyperparameters like a learning rate and momentum, etc.  In terms of another recommendation for a model to solve this problem, a random forest classifier could be a good alternative, as this model is not as affected by outliers within the data.