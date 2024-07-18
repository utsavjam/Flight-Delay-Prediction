# Flight-Delay-Prediction

## Problem Statement

Having a Rock on Pizza franchise, with its factory located in Washington, D.C, operates multiple outlets at strategic locations including New Yok and, New Jersey State. This setup is pivotal for the franchise’s ability to distribute fresh pizza ingredients swiftly, leveraging the strategic positioning of airports for fast and efficient delivery. The timely and efficient stocking and delivery of ingredients from the Washington DC factory to these outlets are crucial to maintaining the quality and freshness of the pizza ingredients.
Recent flight delays from the Ronald Reagan Washington National Airport (DCA) have presented significant logistical challenges, with ingredients arriving late and in less-than-optimal condition at the outlets. This has impacted the freshness of the pizzas and posed risks to customer satisfaction and the franchise’s financial health. Furthermore, these delays have complicated the stocking processes stockouts, thus exacerbating the challenges in inventory management.
To address these challenges, having a Rock on Pizza plans to harness its analytics team to conduct a comprehensive analysis of its supply chain and stocking strategies. By implementing machine learning models like K-Nearest Neighbors, Naive Bayes Classifier, and Random Forest, the franchise aims to proactively manage its supply chain, optimize delivery schedules, and improve stocking accuracy. This approach is designed to minimize the risk of ingredient spoilage and stock discrepancies, ensuring the consistent quality of its pizzas across all locations, enhancing customer experience, and reducing potential financial losses associated with spoilage and inefficient inventory management.

## About Dataset:

The Flight Delays dataset comprises 13 features and focuses on flights originating from the Washington, DC area to the New York City area in January 2004. Specific### ally, we've narrowed down the data to flights departing from DCA, as this is the exclusive airport from which Planty-Fresh ships its produce. Here's a rundown of the important attributes utilized in this analysis. 

### Carrier: Eight airline codes: CO (Continental), DH (Atlantic Coast), DL (Delta), MQ (American Eagle), OH (Comair), RU (Continental Express), UA (United), and US (US Airways).
### Dep_Time: Departure time between 6:00 AM and 10:00 PM.
### Dest: Destination with three airport codes: DCA (Reagan National), IAD (Dulles), BWI (Baltimore-Washington Int's).
### FL_Date: Flight Date.
### Origin: The airport codes. DCA is the only record.
### Weather: Binary, coded as ‘1’ if there was a weather-related delay ‘0’ Otherwise
### Day_Week: Day of the week coded as 1=Monday, 2=Tuesday, 3=Wednesday, 4=Thursday, 5=Friday, 6=Saturday, 7=Sunday.
### Day_Of_Month: Calendar Day of the month.
### Flight Status: Ontime or Delayed

## Preprocessing and Statistics:

In the process of preparing for the modeling, we focused exclusively on flight data from the busiest airports in the U.S., as they provided a vast number of scheduled arrival flight records. The data underwent a cleaning process, particularly for the flight carrier names and the airports (origin and destination), using the IATA code abbreviations. We discarded attributes with over 50% missing data that offered no significant insights for the analysis, as well as irrelevant attributes like those documenting the status of canceled or diverted flights. Since our primary goal was to forecast flight delays, we specifically removed data related to canceled flights. Records with missing values were also excluded, which was justified as these missing values constituted less than 1% of the data, a minor proportion.
For the purpose of classification, we introduced a binary attribute called "FLIGHT_STATUS" to denote the flight’s status. We derived the month, day, and weekday from the actual flight dates. In preparation for modeling, we transformed all categorical data, such as destination airport, weekday, flight carrier, and flight delay reasons, into numerical values using the one-hot encoding technique. This method creates a dummy variable for each category: the variable is marked as one if the category is present, and zero if it is not

## Model Evaluation

Model	                Class	  Precision	  Recall	  f1-score	  Support

KNN	                    0	    0.86	      0.98	    0.92	      226
	                      1	    0.75	      0.25	    0.38	      48
                       
Naive Bayes Classifier	0	    0.83	      1	        0.91	      226
	                      1	    1	          0.06	    0.12	      48
                       
Decision Tree	          0	    0.88	      0.9	      0.89	      226
	                      1	    0.46	      0.4	      0.43	      48

## Conclusion

After considering all the algorithm models, to predict flight delays and optimize its supply chain for distributing fresh pizza ingredients from Washington D.C. to its outlets. The K-Nearest Neighbors (KNN) algorithm shows the highest accuracy at 85.4%, followed by Naive Bayes at 83.57%, and the Decision Tree at 81.02%. While all models exhibit strong overall accuracy, they vary in performance when predicting delayed flights. Therefore, the franchise must select a model that aligns with its operational goals, whether it's minimizing disruptions or improving delay detection to ensure ingredient freshness and customer satisfaction.
