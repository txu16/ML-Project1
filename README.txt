Letters Dataset: https://archive.ics.uci.edu/ml/datasets/Letter+Recognition
Income Dataset: https://www.kaggle.com/uciml/adult-census-income#adult.csv

Part 1: Getting Training and Test Set
Based on: https://youtu.be/uiDFa7iY9yo
1. open Weka
2. open Explorer; you should default into the Preprocess tab
3. open File (adult.arff or letter.arff)
4. in the Preprocess tab, choose Filter -> unsupervised -> instance -> Resample
5. change the sampleSizePercent to 80 and noReplacement to True
6. click OK then save the file as a adultTrain.arff or letterTrain.arff (depending on which data set you're modifying)
7. click Undo then click on the Resample bar to reconfigure
8. change invertSelection to True and click OK and save this as test set (adultTest.arff or letterTest.arff)

Part 2: Running Cross-validation 
1. open Weka
2. open Explorer; you should default into the Preprocess tab
3. Open File... (adult.arff or letter.arff)
4. Go to classify tab and Choose a classifier (WLOG for other algorithms, we will use J48)
5. Choose -> Trees -> J48 (location changes depending on which algorithm you run)
6. Click on the J48 bar so that you can configure the parameters
7. Change the hyperparameters to whatever configuration you want 
7a. for example, in my PDF for J48, I modified confidenceFactor by .05 increments, then minNumObj by increments of 2
8. under Test options, select "Cross-validation" (we will use default of 10 folds)
9. Click Start
10. Repeat step 7-9 for additional hyper parameter changes

Part 3: Running Training
1. open Weka
2. open Explorer; you should default into the Preprocess tab
3. Open File... (adultTrain.arff or letterTrain.arff that you made from part 1)
4. Go to classify tab and Choose a classifier (WLOG for other algorithms, we will use J48)
5. Choose -> Trees -> J48 (location changes depending on which algorithm you run)
6. Click on the J48 bar so that you can configure the parameters
7. Change the hyperparameters to whatever configuration you want 
7a. for example, in my PDF for J48, I modified confidenceFactor by .05 increments, then minNumObj by increments of 2
8. under Test options, select "Use training set"
9. Click Start
10. Repeat step 7-9 for additional hyper parameter changes

Part 4: Running Test
1. open Weka
2. open Explorer; you should default into the Preprocess tab
3. Open File... (adultTrain.arff or letterTrain.arff that you made from part 1)
4. Go to classify tab and Choose a classifier (WLOG for other algorithms, we will use J48)
5. Choose -> Trees -> J48 (location changes depending on which algorithm you run)
6. Click on the J48 bar so that you can configure the parameters
7. Change the hyperparameters to whatever configuration you want 
7a. for example, in my PDF for J48, I modified confidenceFactor by .05 increments, then minNumObj by increments of 2
8. under Test options, select "Use training set"
9. Click Start
10. after the training set is done running, under Test options, select "Supplied test set" and open the adultTest.arff or letterTest.arff created from part 1
11. Click Start
12. Repeat step 7-11 for additional hyper parameter changes

Part 5: Learning Curve (% of training vs accuracy on test set)
1. Using the same method for splitting your data in Part 1, we will now split the training set into 10%, 20%, 30%,...90%
2. open Weka
3. open Explorer; you should default into the Preprocess tab
4. open File (adultTrain.arff or letterTrain.arff)
5. in the Preprocess tab, choose Filter -> unsupervised -> instance -> Resample
6. change the sampleSizePercent to 10 and noReplacement to True
7. click OK then save the file as a adultTrain{Percent}.arff or letterTrain{Percent}.arff (depending on which data set you're modifying) (e.g. adultTrain10.arff)
8. click Undo then click on the Resample bar to reconfigure
9. repeat step 6-8 with sampleSizePercent 20, 30,...90
10. Open File... adultTrain{Percent}.arff or letterTrain{Percent}.arff 
11. Go to classify tab and Choose a classifier (WLOG for other algorithms, we will use J48)
12. Choose -> Trees -> J48 (location changes depending on which algorithm you run)
13. Click on the J48 bar so that you can configure the parameters
14. Change the hyperparameters to whatever configuration you want 
14a. for example, in my PDF for J48, I modified confidenceFactor by .05 increments, then minNumObj by increments of 2
15. under Test options, select "Use training set"
16. Click Start; record result as the training accuracy with {percent}% training data removed
17. after the training set is done running, under Test options, select "Supplied test set" and open the adultTest.arff or letterTest.arff created from part 1
18. Click Start; record result as the test accuracy with {percent}% training data removed
19. Repeat steps 10-18 with the remaining percentages of training data (20, 30,...90)

Additional Notes:
-for the MultilayerPerceptron, to have two layers of 70 nodes each, I input "70,70" as the parameter in hiddenLayers



