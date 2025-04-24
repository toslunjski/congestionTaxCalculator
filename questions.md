# Questions
The following was discovered as part of analysing this project:

* How does tooling station work? 
    * Automatic plates registration?
    * Person input?
    * Vignette?
    
* What is the input for application? 
    * Every event on toll by car?
    * Daily actions by car?
    
* What is output of application?
    * Calculated daily amount of tax based on car toll actions?

* Congestion tax is charged during fixed hours for vehicles driving into and out of Gothenburg.

    * Is tax charged based on in, out or time period spent in city?

* Charge period? Somekind of postpaid bill is sent after some charging period?
    * Daily?
    * Monthly? 
    * Yearly?


* Car identification? 
    * Plates?
    

* How to identify tax exempt vehicles? Toll recognises them?

    * Emergency vehicles - special plates?

    * Busses - no idea...

    * Diplomat vehicles - special plates?

    * Motorcycles - no front plates?

    * Military vehicles - special plates?

    * Foreign vehicles - foreign plates?
    
* How exactly is the “60-minute rule” applied?

    * Assumed: if multiple timestamps fall within a 60-minute window, we take the highest tax rate among them, and only that one is charged. Next window starts after that first timestamp.



### Focus on

1) Creation of REST endpoint/endpoints which will get and store the data needed for charging

    
2) DB model for persisting data
    

3) Persistence of charging rules/fees
    * Stored as structured and precisely formatted file which will be loaded on application startup as config file
    

4) Charging processing
    * Thinking on somekind of scheduled daily job which will go through stored data and produce daily expenses by car

### Conclusion and additional work
Given the 6-hour limit, I chose to prioritize correctness, clean structure, and extensibility. If given more time, I would fully externalize tax rules, add unit/integration tests, and implement multi-city handling.