# Counting app - Demo React and NodeJS app

[![Publish counter docker image](https://github.com/modul-i-ch-109/counter_kand/actions/workflows/docker.yml/badge.svg?branch=master)](https://github.com/modul-i-ch-109/counter_kand/actions/workflows/docker.yml)

## Scope
The goal was to create a dynamic counter app to replace the current paper-heavy counting tasks. The application must be able to run on the mobile and must be intuitive.

## Design
### Frontend
Using react in combination with the material design to create a intuitive UI.

![UseCaseView](documentation/usecaseView.PNG)
![ExecutionOfMeasurements](documentation/ExecutionOfMeasurementsView.PNG)
![MeasurementsView](documentation/measurementsView.PNG)

### Backend

Backend API is using node and postgres as persistent datastore.
# Development
Backend and frontend are combined in this project.
For the runtime the following env variable can control behavior of the application:
