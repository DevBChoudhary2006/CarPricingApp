# CarPricingApp
Car Deal Finder

Predicts what a used car should cost from its specs, then flags listings priced well below that value.

How the model works

Load the cars CSV and drop rows with missing or zero prices.

Preprocess: impute and one-hot encode categorical columns, pass numeric columns through.

Train a gradient boosting model on log-transformed price.

Generate out-of-fold predictions (5-fold CV) so each car is priced by a model that never saw it.

Compute savings = predicted price - listed price and rank by percentage below predicted.

Will then cross reference the price amongst different services (CarMax, Facebook marketplace, etc) for the best price. 
