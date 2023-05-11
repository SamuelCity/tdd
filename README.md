# TDD Demo
This repository is designed to teach you how to develop new functionality for a Spring Boot service using TDD. You will find some scenarios and expected outcomes below.

## Test Scenarios
We want to implement a cancel pass endpoint into this service, below you will find the expected endpoint, with the expected responses.

## Pass Model
- The default state for a pass in the system should be INACTIVE and have two choices.

## Input
```
PATCH /pass/{pass_number}

{
    "status": ACTIVE | FULLY_USED | CANCELLED
}
```

### PATCH Scenarios
Given my pass has been created
When I first use it
Then my pass will become active

Given my pass has not been activated
When I cancel my pass
Then my pass will become cancelled and I will not be able to use it 

Given my pass has been activated
When I use all my choices
Then my pass will become fully used

Given my pass has been activated
When I cancel my pass
Then my pass will become cancelled and I will not be able to use it anymore

Given my pass has been fully used
When I try to activate it again 
Then the activation will fail

Given my pass has been fully used
when I try to cancel my pass
Then the cancellation will fail
