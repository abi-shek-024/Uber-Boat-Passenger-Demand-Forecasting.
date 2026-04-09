UBER BOAT PASSENGER DEMAND
FORECASTING: INTERNSHIP TASK
SUBMISSION
Candidate: Abishek Chinnappan
Task: Uber Boat Passenger Prediction - ML Forecasting Task
“ All code development, training, and evaluation were performed using
Google Colab, utilizing a T4 GPU for faster computation and efficient
model training.”
1. PROJECT OVERVIEW
This project aims to forecast the expected number of passengers for Uber Boat journeys
using historical trip and weather data. Accurate forecasting supports better fleet
planning, scheduling, and enhances the commuter experience.
I approached the problem with the mindset of solving a real-world challenge What drives
passenger demand on the river? I focused on extracting the most informative features
such as time, route, temperature, and weather and translating them into inputs a
machine learning model could understand.
2. DATA PREPARATION & FEATURE ENGINEERING
Two datasets were used:
• Passenger Data: Included route, timestamp, and passenger count.
• Weather Data: Provided hourly weather snapshots.
Steps followed:
• Merged both datasets using hourly timestamps.
• Extracted hour, weekend flags, start/end piers, and encoded weather
conditions.
• Dropped missing values and prepared final training data.
3. EXPLORATORY DATA ANALYSIS
I visualised passenger trends by:
• Hour of Day: Revealed peak demand in the morning and evening.
• Weekend vs Weekday: Higher averages on weekends.
• AM vs PM: Showed strong patterns for operational planning.
These visuals validated the choice of features and confirmed the intuition that external
factors affect ferry usage.
2
4. Model Selection & Evaluation
I tested four models:
• Random Forest Regressor
• XGBoost
• LightGBM
• Gradient Boosting Regressor
Each model was tuned using GridSearchCV. Evaluation was based on:
• MAE (Mean Absolute Error)
• RMSE (Root Mean Squared Error)
Figure 1: displays the MAE & RMSE values of each model
FINAL RECOMMENDATION:
I selected Light Gradient Boosting Machine (LightGBM) as the final model for this
internship project.
While XGBoost recorded the lowest MAE (28.03), LightGBM achieved the lowest RMSE
(97.50) which was the key deciding factor.
Because RMSE penalizes larger errors more heavily, it's better suited for applications
like ours where reducing large deviations in predicted passenger counts is critical.
Moreover, LightGBM is known for its high training speed and low memory usage, making
it ideal for real-time or large-scale operational environments.
3
In summary, LightGBM offered the best trade off between precision, efficiency, and
deployability, which made it the most suitable choice for this forecasting task.
Figure 2: Chosen the best-fit sustainable model.
5. Explainability with SHAP
To ensure interpretability, I used SHAP to:
• Identify top features globally affecting predictions.
• Explain individual predictions for transparency.
This is helpful for stakeholders who want to understand what drives model decisions.
6. UBER BOAT PASSENGER DEMAND PREDICTOR ( Own idea )
To bridge the gap between technical modeling and real-world usability, I designed a fully
interactive Uber Boat Demand Predictor using “ipywidgets” inside Google Colab
Notebook.
This interface wasn’t just a cosmetic addition it was built with the goal of demonstrating
how machine learning can be practically used by non-technical stakeholders, such
as route planners, ferry managers, or even customer service teams.
Key Features of the Interface:
• Time of Departure (Dropdown): I used a 12-hour AM/PM format to make time
selection intuitive.
4
• Peak Hour Toggle: Users can easily indicate whether the trip falls in a peak
travel window.
• Route Selector: Each route is labeled clearly with start and end piers so that
operational staff can relate to real routes.
• Weather & Temperature Input: Since weather influences passenger demand
significantly, I made it possible to simulate this condition with dropdowns and
sliders.
• Instant Prediction Display: Upon clicking the button, the model makes a real-
time prediction and displays it in a clean, readable format like:
“Prediction: We estimate approximately 124.4 passengers onboard.”
Figure 3: Uber boat passenger demand predictor interface
.
WHY I BUILT IT:
I wanted to show how a technical model built in code can be turned into something that
feels like a tool. This helps stakeholders make data-driven decisions without needing
to understand machine learning pipelines.
5
This user interface reflects my broader mindset throughout the project: solve the real
problem, and make it usable for the people who face that problem every day.
7. FINAL DELIVERABLES
As per the internship task checklist, the following files are submitted:
• UberBoat_PassengerPrediction_AbishekChinnappan.ipynb
• final_model.pkl
• x_test.csv
• y_test.csv
• requirements.txt
8. FINAL REFLECTION
This task challenged me to apply end-to-end machine learning from cleaning and
visualisation to model building, tuning, interpretation, and deployment. I especially
enjoyed designing the interface to bridge technical results with operational use.
I'm confident this solution is production-ready, interpretable, and relevant to real-world
demand forecasting challenges.
9. REAL-WORLD RELEVANCE
In real urban settings like London's Thames Clippers or New York’s NYC Ferry,
passenger demand fluctuates drastically based on hour, weather, and day type. For
instance, a clear Friday evening tends to see a surge in commuters and tourists, similar
to what our model captured through SHAP values and AM/PM peaks. This alignment
between our model insights and actual ferry operations reinforces the practicality of our
approach. The LightGBM model’s precision and efficiency make it highly applicable to
such live city transport systems.
Thank you for the opportunity to demonstrate my skills and thought process.
