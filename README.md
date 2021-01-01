==========================  File based Key Value Datastore  ==================================
       
       
       Pypi page  :         https://pypi.org/project/KVDatastore/



This is a simple Key value datastore that supports CRD operations(Create, Read, Delete). 
This datastore creates a datastore in your local machine.
It is implemented using inbuilt datastructure- Dictionary. 
It is thread-safe by default and every read and write operation is protected with thread locks.


Since it is a package, you can initialize by following steps.



	=> open your terminal, run pip install KVDatastore
	=> now open your python, run following code.
	
>>> from KVDatastore import *

>>> object=KVDatastore()
	
	This imports all methods to your code and creates instance of the class

	=> The methods available are,
		--> initdatastore(location)
		--> create(key,value)	
		--> read(key)
		--> delete(key)


---------------------------------initdatastore(location)-----------------------------------------

This method is called to initialize the datastore.
It is called with optional location argument which can create custom directory with <datastore.json> file.
Else default directory name of <datastore> is created on your working file path.


>>> object.initdatastore(yourcustomdirectoryname)

---------------------------------create(key,value)------------------------------------------------

This method is called with key and value. key is usually string and value can be json object.
If create is invoked for existing key appropriate error is displayed.

Each key is subjected to Time To Live (TTL) property. Default TTL is 360 seconds. 
User cannot access the key to modify the value not more than 360 seconds.
The whole datastore is not more than 1Gb.
>>> object.create(key,value)



----------------------------------read(key)-------------------------------------------------------

This method is called with key. Once the key is expired from TTL, user cannot perform read method for the particular key.

>>> object.read(key)


----------------------------------delete(key)-----------------------------------------------------

This method is called with key. Once the key is expired from TTL, user cannot perform delete method for the particular key.

>>> object.delete(key)





