# YAML

## Key Value Pair 
Ex:  
Fruit: Apple
Vegetable: Carrot

## Array/Lists
Fruits: 
    - Orange
    - Banana
Vegetables: 
    - Carrot
    - Cauliflower

## Dictionary / Map
Banana:
    Calories: 105
    Fat: 0.4g
    Carbs: 27g

Grapes:
    Calories: 102
    Fat: 0.5g
    Carbs: 28g

## Dictionary (Unordered is allowed) Vs List (Ordered /Unordered is not allowed) vs List of Dictionaries
### Dictionary
Color: Blue
Model: Toyota
Transmission: Auto
Price: $30000

### Dictionary within Dictionary
Color: Blue
Model: Toyota
    Name: Corolla
    Year: 2021
Transmission: Auto
Price: $30000

### List
- Blue Corolla
- Red Corolla
- Green Corolla

### List of Dictionaries

- Blue Corolla
  Model: Toyota
    Name: Corolla
    Year: 2021
  Transmission: Auto
  Price: $30000
- Red Corolla
  Model: Toyota
    Name: Corolla
    Year: 2021
  Transmission: Auto
  Price: $30000
- Green Corolla

# YAML in Kubernetes

## pod-definition.yml
| Root level properties | Description | Example |
|-----------------------|-------------|---------|
| apiVersion|Version of the K8s object | v1, apps,v1 |
| kind | Type of object | Pod, Service, ReplicaSet, Deployment |
| metadata | is a data about the object like names, labels, etc,. Its a key value. Say if there are 100 Pods if we label them as front end or database you will be able to filter the pods | |
| spec | Additional information to K8s pertaining that object. Spec is a dictionary and then followed by container list. | |