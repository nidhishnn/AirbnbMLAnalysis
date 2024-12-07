# AirbnbMLAnalysis
Prescribing Optimal Prices for Airbnb Listings in New York City

Nidhish Nerur & Maya Nesen 
Machine Learning Under a Modern Optimization Lens Final Project

**Introduction**: Airbnb hosts struggle with pricing their listings to maximize their booking rate and customer satisfaction. With multi-modal data, our project provides a framework to address this challenge by providing hosts with actionable guidance. In particular, we use classification machine learning algorithms to predict the rating score of a given listing. The primary issue is we only know the observed rating score for the specific price assigned to the listing by the host. Consequently, we perform counterfactual estimation to assess the potential rating outcome if the listing had been priced in a different range. We utilize two counterfactual methods, namely, Direct Method and Doubly Robust to estimate a rewards matrix representing the rating scores across various price buckets. Finally, we build interpretable Optimal Policy Trees which display relevant features driving the optimal price prescription that will maximize rating outcomes.

**Data Description**: For this project, we selected the AirBnB U.S. Properties Images dataset from Kaggle, which contains 53,063 rows of listings in the U.S., with 24,688 of them being for listings in New York City. Each row contains an Airbnb listing described by 29 features: id, log price, property type, room type, amenities, accommodates, bathrooms, bed type, cancellation policy, cleaning fee, city, description, first review, host has profile pic, host identity verified, host response rate, host since, instant bookable, last review, latitude, longitude, name, neighbourhood, number
of reviews, review scores rating, thumbnail url, zipcode, bedrooms, and beds.

Dataset Source: https://www.kaggle.com/datasets/eren2222/airbnb-properties-image/data?select=Airbnb_Data_Images.csv

**Key Results**: 
<img width="809" alt="OPTDirectMethodFinalTree" src="https://github.com/user-attachments/assets/00abe7f0-a66e-4f67-92ba-84a27a627890">

The Optimal Policy Tree highlights that the number of people the Airbnb listing accommodates, distance to Times Square, and number of customer reviews drive which price to prescribe in order to
optimize the rating range. Logically, these features make business sense in determining how to
price an NYC listing. In particular, if the listing is geographically close to the popular Times
Square attraction, accommodates more people, or has more reviews, then we would expect the
listing to be pricier on average. 

The average estimated rating outcome score under our prescribed treatments is about 1.326, whereas the average rating score under the treatment prices observed in the data is roughly 1.096. Thus, our tree provides a 20.94% improvement in the rating bucket score, raising both customer satisfaction and host revenue.

<img width="533" alt="DoublyRobustFinalTree" src="https://github.com/user-attachments/assets/41add9ad-bb22-416a-ad33-124f7f0bf5b1">

Similar to our first tree, this one also suggests that number of reviews and accommodates are key drivers of the optimal pricing strategy to yield improved ratings. We also see that the room type being listed as a private room rather than a shared room is an important determinant of the prescribed price. Furthermore, we see this tree does not prescribe the middle price range of 80 to 150 dollars, and tells hosts to keep the price cheap or on the more expensive side.

For this tree, we made the outcome binary rather than multi-class for ease of computation, so we have perfect rating as one bucket and all other scores in the remaining class. The average estimated rating outcome score under our prescribed treatments is about 0.360, whereas the average rating score under the treatment prices observed in the data is roughly 0.293. Thus, our tree provides a 22.81% improvement in the rating bucket score.



