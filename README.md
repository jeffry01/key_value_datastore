=====================  File based Key Value Datastore ==================

============= Pypi link: https://pypi.org/project/KVDatastore/   ==================





This is a simple Key value datastore that supports CRD operations(Create, Read, Delete) hosted on Pypi libraries.
The datastore is initialized in your local machine.
The key-value datastore is implemented using inbuilt datastructure with keys having Time To Live property.
The dict datastructure is thread-safe by default and every read and write operation is protected with thread locks.


Since it is a package, you can initialize by following steps.



	=> open your terminal and run, pip install KVDatastore
	=> now open your python, run following code.
	
>>> from KVDatastore import *

>>> object=KVDatastore()
	
	The above code imports all methods to your code and creates instance of the class

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

This method is called with key and value. key is usually a string and value can be json object.
If create is invoked for existing key appropriate error is displayed.
Each key is subjected to Time To Live (TTL) property. Default TTL is 360 seconds. 
User cannot access the key to modify the value not more than 360 seconds.
The whole datastore is not more than 1Gb.


>>> object.create(key,value)

----------------------------------read(key)-------------------------------------------------------

This method is called with key as parameter. Once the key is expired from TTL, user cannot perform read method for the particular key.

>>> object.read(key)


----------------------------------delete(key)-----------------------------------------------------

This method is called with key as parameter. Once the key is expired from TTL, user cannot perform delete method for the particular key.

>>> object.delete(key)





