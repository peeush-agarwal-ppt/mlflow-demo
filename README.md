# MLFlow demo

This is the source control for Blog series on End-to-end MLOps pipeline using MLFlow.

## Setup dev env

1. `pip install virtualenv`
1. `virtualenv mlops-env`
1. `source mlops-env/bin/activate`
1. `pip install mlflow pandas scikit-learn`

## Serve the trained model

`mlflow models serve -m "runs:/65e225aac4ce422fac26e012087e9ffd/bike_prediction_model" -p 1234 --no-conda`

### Test with sample data

`curl -X POST -H "Content-Type: application/json" -d '{"dataframe_split":{"columns":["season","holiday","workingday","weather","temp","atemp","humidity","windspeed","casual","registered","hour","day_of_week", "month","is_clear_weather","is_rainy_weather","is_holiday_workingday"],"data":[[3.0,0.0,1.0,1.0,33.62,40.15,59.0,0.0,29.0,98.0,11.0,1.0,7.0,1.0,0.0,0.0]]}}' http://127.0.0.1:1234/invocations`
