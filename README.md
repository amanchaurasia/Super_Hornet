## Project Goal

Create a predictive model that would say the number of interactions that a property would receive in a period of time. For simplicity let’s say i want to predict the number of interactions that a property would receive within 3 days of its activation and 7 days of its activation.

### Data Description

Properties form one of the most important data entity in nobroker data ecosystem. Properties receive interactions on NoBroker. One interaction is defined as one user requesting an owner contact on a property. A property can receive 0 to many interactions.

*property\_data\_set.csv:*

* Properties data containing various features like activation\_date, BHK type, locality, property size, property age, rent, apartment type etc.

* activation\_date is the date property got activated on NoBroker. Fields like lift, gym etc are binary valued - 1 indicating presence and 0 indicating absence. All other fields are self-explanatory.

*property\_photos.tsv:*

* Data containing photo counts of properties

* photo\_urls column contains string values that you have to parse to obtain the number of photos uploaded on a property

* Each value in the photo\_url column is supposed to be a string representation of an array of json where each json object represents one image. However due to some unforeseen events, these values got corrupted and lost their valid json array representation.

* Objective is to get the number of photos uploaded for a property.

*property\_interactions.csv:*

* Data containing the timestamps of interaction on the properties.

* Each request\_date value represents the timestamp of a unique valid interaction on a property (contact owner happened and a user received the owner contact phone number)

* Therefore if you count the number of times each property has appeared in this table, it tells you the number of interaction received on this property

* Use this request\_date along with the activation\_date in the first table and other features
