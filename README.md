# Big-Data
Processed the ‘Airline On-time Performance data set’ using fully distributed mode in Hadoop and measured corresponding workflow execution time as part of a Big data project.
Function Mapper()
1. Read File line by line and For Each Line
a. Get Key as Carrier
b. Get Arrival Delay and Departure Delay.
c. If delay has value and is larger than 5 consider it as Delay and map it as
i. Pair(Key, Value) = (Carrier,”1,1”) // If Value is greater than 5
d. else
i. Pair(Key, Value) = (Carrier,”1,0”) // If Value is less than equals to 5
Function Reducer()
1. Read File line by line and For Each Line
a. Get Key as Carrier
b. Read Value and split it on comma (,) as
i. First value is Total Value
ii. Second value is count of number of timers delay.
Function EvaluateProbability()
For Each Carrier as key we have Record like this (Key Value) = (Carrier Total,DelayNumber) 1. Read Reducer output file line by line
a. Calculate Probability as DelayNumber/Total and put the value in max and min heap of size 3. 2. At end of file Print the heap as Statistics.
TaxiTime:
Function Mapper()
1 Read File line by line and For Each Line
e. Get Key as Airport
f. Get Taxi In and Taxi Out.
g. map it as
Pair(Key, Value) = (Org,”1,TaxiOut”)
h. Else
Pair(Key, Value) = (Dest,”1,taxiIn”)
Function Reducer()
1. Read File line by line and For Each Line
c. Get Key as Airport
d. Read Value and split it on comma (,) as
i. First value is Total Value
ii. Second value is time delay.
Function EvaluateTaxiTime()
For Each Airport as key we have Record like this (Key Value) = (Airport Total,TimeDelay) 3. Read Reducer output file line by line
a. Calculate Probability as TimeDelay/Total and put the value in max and min heap of size 3. 4. At end end of file Print the heap as Statistics.
