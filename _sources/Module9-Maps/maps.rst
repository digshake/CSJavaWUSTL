.. qnum::
   :prefix: 8-1-
   :start: 1
   
.. |CodingEx| image:: ../../_static/codingExercise.png
    :width: 30px
    :align: middle
    :alt: coding exercise
    
    
.. |Exercise| image:: ../../_static/exercise.png
    :width: 35
    :align: middle
    :alt: exercise
    
    
.. |Groupwork| image:: ../../_static/groupwork.png
    :width: 35
    :align: middle
    :alt: groupwork

Maps
==========================

`Maps <https://docs.oracle.com/javase/8/docs/api/java/util/Map.html>`_ (sometimes referred to as hash tables or dictionaries) are one of the most useful data structures and are likely present in nearly every application, website, or program that you've ever used. For the purposes of this module, we'll introduce you to the concept of a Map and the basics on how to use it, but you will almost certainly run into this very important data structure again and explore it in more detail if you continue your computer science education beyond this course.

What makes Maps different than the other types of data structures that we've seen is the idea of a **key-value pair**. Maps associate every piece of data (the **values**) with a **key** much like a dictionary or a phone book. We can **put** values into the map and **get** values from the map as long as we know the associated key.

|CodingEx| **Coding Exercise**

Open the ``Phonebook`` program and examine the code as it adds values to a Map that is used as a phone book. Experiment with the code and make sure that you understand how values are stored and retrieved from the map.

More on Keys and Values
=======================

To make things even more interesting (and useful!), the types of the keys and values can be any valid type. For example, our phone book used Strings as the type of the keys and Integers as the type of the values, so that we could look up phone numbers by name. But what if we wanted to use a map to act as a dictionary instead? If we wish to have definitions (the value) associated with words (the keys), then what would the types of the keys and values be?

Think about what types you would use for the keys and values of the following maps:

* People and the city they are from
* Planets and their distance from the sun
* The name of a playlist and the list of songs it contains (wait, a List in a Map? Try it!)

Notice that it is not possible to have more than one value associated with a key. Or in other words, it is not possible to have duplicate keys in a map. This means that we can treat all of the keys as a set, a very handy thing to keep in mind if we need to retrieve all of the values from a map!

|CodingEx| **Coding Exercise**

Open the ``Keys`` program and examine the two ways shown to iterate through a map. Notice that both forms of iteration use a for-each style loop since we're dealing with sets, which are unordered.
