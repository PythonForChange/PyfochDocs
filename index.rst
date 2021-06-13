#############
PFCF Language
#############

Python For Change Format Language allows to easily integrate different Python For Change Ecosystem functionalities


Sofware (for developers)
************************

`Get the last version of this software here <https://github.com/PythonForChange/FilesFormat>`__


Installation (last stable version)
**********************************

1. Install pyforchange

    pip install pyforchange ::

2. Import pfcf in your python file

.. code-block:: python
    import pyforchange.pfcf

3. Enjoy!

Writting PFCF code with `Pyfoch Editor <https://pythonforchange.github.io/pyfoch>`__
*************************************************************************************

Example
=======

1. Open `Pyfoch <https://pythonforchange.github.io/pyfoch>`__.

2. Write the following lines:


    hello,world",|
    
    ~this text can not be printed~
    Hi!,
    
    1. Run main.py,
    2. Edit this file and see the magic,
    3. This is the first real-time editor of .pfcf files,|
    
    Welcome to pfcf,
    ~
    multiline
    commentary
    ~
    a new lang...,
    a new experience...,
    Welcome to the future,:),|
    
    May 10 2021\, 13:45,
    by Eanorambuena,|
    
    Add code like this:,|
    \<qiskit\>,
    q0  q1,
        X,
    H,
    .---X,
    c1,
    $host qasm_simulator,
    $hist true,
    $draw true,
    \</qiskit\>\,,
    |
    \<python\>,
    print(\"hello world\"),
    \</python\>\,,
    |
    \<wolfram\>,
    Range[5],
    \</wolfram\>\,, ::


3. In "File" menu, click on "Export".
4. Give a name to your exported file and save.
5. Open the exported file.
6. The exported file will have the following text:

    hello
    world
    
    Hi!
    1. Run main.py
    2. Edit this file and see the magic
    3. This is the first real-time editor of .pfcf files
    
    Welcome to pfcf
    a new lang...
    a new experience...
    Welcome to the future
    :)

    May 10 2021, 13:45
    by Eanorambuena
    
    Add code like this:
    
    <qiskit>
    q0  q1
        X
    H
    .---X
    c1
    $host qasm_simulator
    $hist true
    $draw true
    </qiskit>,
    
    <python>
    print("hello world")
    </python>,
    
    <wolfram>
    Range[5]
    </wolfram>, ::

7. Enjoy!

Export PFCF code using pyforchange package
******************************************

Import executepfcf from pyforchange.pfcf.read.

.. code-block:: python
    from pyforchange.pfcf.read import executepfcf

Execute yourfilename.pfcf
    
.. code-block:: python
    executepfcf(yourfilename)

Using pyforchange package in order to create log files
******************************************************
 
Example 1
=========

Import pfcf and give the instructions.
.. code-block:: python
    from pyforchange.pfcf.files import *
    
    l=LogFile("log1")
    l.row("hello[") #this [ can not be printed
    l.row("world\"") #this " can not be printed
    l.section() #break
    l.row("hello"+l.vip("[")) #this [ can be printed
    l.row("world"+l.vip("\"")) #this " can be printed
    l.section() #break
    l.row("by Eanorambuena"+l.den("this text can not be printed"))
    l.read()

First, log1_0.pfcf file is made.

v2.0.2 or upper:

    hello[,world",|hello\[,world\",|by Eanorambuena~this text can not be printed~, ::

Then, log1_0.pfcf is read and printed.

    hello
    world
    
    hello[
    world"
    
    by Eanorambuena ::

Finally, `0` is append to log1_hist.pfcf file.

    0 ::
 
Example 2
=========

.. code-block:: python
    l.reset()
    l.p.den=":"
    l.row(l.den("this text can not be printed"))
    l.read()
 
First, log1_1.pfcf file is made.

v2.0.2 or upper:

:this text can not be printed:, ::

Then, log1_1.pfcf is read and printed.

     ::

Finally, `1` is append to log1_hist.pfcf file.

    0
    1 ::
 
Example 3
=========

.. code-block:: python
    data = {}
    data['clients'] = []
    data['clients'].append({
        'first_name': 'Sigrid',
        'last_name': 'Mannock',
        'age': 27,
        'amount': 7.17})
    data['clients'].append({
        'first_name': 'Joe',
        'last_name': 'Hinners',
        'age': 31,
        'amount': [1.90, 5.50]})
    data['clients'].append({
        'first_name': 'Theodoric',
        'last_name': 'Rivers',
        'age': 36,
        'amount': 1.11})
    l2=LogFile("log2")
    l2.fromDict(data)

First, log2.json file is made.

    {
        "clients": [
            {
                "first_name": "Sigrid",
                "last_name": "Mannock",
                "age": 27,
                "amount": 7.17
            },
            {
                "first_name": "Joe",
                "last_name": "Hinners",
                "age": 31,
                "amount": [
                    1.9,
                    5.5
                ]
            },
            {
                "first_name": "Theodoric",
                "last_name": "Rivers",
                "age": 36,
                "amount": 1.11
            }
        ]
    } ::

Then, log2.json is read as a .pfcf file.
Finally, it is printed.

        clients: 
            
                first_name: Sigrid
    
                last_name: Mannock
    
                age: 27
    
                amount: 7.17
            
    
            
                first_name: Joe
    
                last_name: Hinners
    
                age: 31
    
    
                amount: 
                    1.9
    
                    5.5
                
            
    
            
                first_name: Theodoric
    
                last_name: Rivers
    
                age: 36 ::
