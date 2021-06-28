.. role:: raw-html(raw)
    :format: html

#############
PFCF Language
#############

About PFCF
**********


Python For Change Format is a flexible marked language which allows to implement Python For Change solutions to several problems.

Python For Change Ecosystem easy integration
============================================

PFCF Language allows to easily integrate different Python For Change Ecosystem functionalities.


Advantages
==========

1. PFCF Language is written 100% in python and allows to write in python. :raw-html:`<br />`
2. Then, PFCF can improve it itselft. That allows PFCF to get new special commands everyday. :raw-html:`<br />`
3. PFCF have special eigen commands (NQS scripts) that simplify the development of code with IBM Qiskit. This scripts are currently deprecated. [Learn more about NQS here.](https://nqs.rtfd.io)


Sofware (for developers)
************************

Get the last version of this software here <https://github.com/PythonForChange/FilesFormat>`__

.. image:: https://readthedocs.org/projects/pyfoch/badge/?version=latest

###########
Quick Start
###########

Installation (last stable version)
**********************************

1. Install pyforchange

    pip install pyforchange ::

2. Import pfcf in your python file

    import pyforchange.pfcf ::

3. Enjoy!

Writting PFCF code with `Pyfoch Editor <https://pythonforchange.github.io/pyfoch>`__
*************************************************************************************

Example
=======

1. Open `Pyfoch <https://pythonforchange.github.io/pyfoch>`__.

2. Write the following lines:


    hello,world",|
    
    ~this text can not be printed~ :raw-html:`<br />`
    Hi!,
    
    1. Run main.py, :raw-html:`<br />`
    2. Edit this file and see the magic, :raw-html:`<br />`
    3. This is the first real-time editor of .pfcf files,|
    
    Welcome to pfcf, :raw-html:`<br />`
    ~ :raw-html:`<br />`
    multiline :raw-html:`<br />`
    commentary :raw-html:`<br />`
    ~ :raw-html:`<br />`
    a new lang..., :raw-html:`<br />`
    a new experience..., :raw-html:`<br />`
    Welcome to the future,\:),|
    
    May 10 2021\\, 13\:45, :raw-html:`<br />`
    by Eanorambuena,|
    
    Add code like this\:,|
    
    \\<qiskit\\>, :raw-html:`<br />`
    q0  q1, :raw-html:`<br />`
        X, :raw-html:`<br />`
    H, :raw-html:`<br />`
    .---X, :raw-html:`<br />`
    c1, :raw-html:`<br />`
    $host qasm_simulator, :raw-html:`<br />`
    $hist true, :raw-html:`<br />`
    $draw true, :raw-html:`<br />`
    \\</qiskit\\>\\,, :raw-html:`<br />`
    | :raw-html:`<br />`
    \\<python\\>, :raw-html:`<br />`
    print(\"hello world\"), :raw-html:`<br />`
    \\</python\\>\\,, :raw-html:`<br />`
    | :raw-html:`<br />`
    \\<wolfram\\>, :raw-html:`<br />` 
    Range[5], :raw-html:`<br />`
    \\</wolfram\\>\\,, ::


3. In "File" menu, click on "Export". :raw-html:`<br />`
4. Give a name to your exported file and save. :raw-html:`<br />`
5. Open the exported file. :raw-html:`<br />`
6. The exported file will have the following text:

    hello :raw-html:`<br />`
    world
    
    Hi! :raw-html:`<br />`
    1. Run main.py :raw-html:`<br />`
    2. Edit this file and see the magic :raw-html:`<br />`
    3. This is the first real-time editor of .pfcf files
    
    Welcome to pfcf :raw-html:`<br />`
    a new lang... :raw-html:`<br />`
    a new experience... :raw-html:`<br />`
    Welcome to the future :raw-html:`<br />`
    \:)

    May 10 2021, 13:45 :raw-html:`<br />`
    by Eanorambuena
    
    Add code like this\:
    
    <qiskit> :raw-html:`<br />`
    q0  q1 :raw-html:`<br />`
        X :raw-html:`<br />`
    H :raw-html:`<br />`
    .---X :raw-html:`<br />`
    c1 :raw-html:`<br />`
    $host qasm_simulator :raw-html:`<br />`
    $hist true :raw-html:`<br />`
    $draw true :raw-html:`<br />`
    </qiskit>,
    
    <python> :raw-html:`<br />`
    print("hello world") :raw-html:`<br />`
    </python>,
    
    <wolfram> :raw-html:`<br />`
    Range[5] :raw-html:`<br />`
    </wolfram>, ::

7. Enjoy!

Export PFCF code using pyforchange package
******************************************

Import executepfcf from pyforchange.pfcf.read.

    from pyforchange.pfcf.read import executepfcf ::

Execute yourfilename.pfcf
    
    executepfcf(yourfilename) ::

Using pyforchange package in order to create log files
******************************************************
 
Example 1
=========

Import pfcf and give the instructions.

    from pyforchange.pfcf.files import *
    
    l=LogFile("log1") :raw-html:`<br />`
    l.row("hello[") #this [ can not be printed :raw-html:`<br />`
    l.row("world\\"") #this " can not be printed :raw-html:`<br />`
    l.section() #break :raw-html:`<br />`
    l.row("hello"+l.vip("[")) #this [ can be printed :raw-html:`<br />`
    l.row("world"+l.vip("\\"")) #this " can be printed :raw-html:`<br />`
    l.section() #break :raw-html:`<br />`
    l.row("by Eanorambuena"+l.den("this text can not be printed")) :raw-html:`<br />`
    l.read() ::

First, log1_0.pfcf file is made.

v2.0.2 or upper:

    hello[,world",|hello\\[,world\\",|by Eanorambuena~this text can not be printed~, ::

Then, log1_0.pfcf is read and printed.

    hello :raw-html:`<br />`
    world
    
    hello[ :raw-html:`<br />`
    world"
    
    by Eanorambuena ::

Finally, `0` is append to log1_hist.pfcf file.

    0 ::
 
Example 2
=========

    l.reset() :raw-html:`<br />`
    l.p.den="\:" :raw-html:`<br />`
    l.row(l.den("this text can not be printed")) :raw-html:`<br />`
    l.read() ::
 
First, log1_1.pfcf file is made.

v2.0.2 or upper:

    \:this text can not be printed\:, ::

Then, log1_1.pfcf is read and printed.

      ::

Finally, `1` is append to log1_hist.pfcf file.

    0 :raw-html:`<br />`
    1 ::
 
Example 3
=========

    data = {}  :raw-html:`<br />`
    data['clients'] = []  :raw-html:`<br />`
    data['clients'].append({  :raw-html:`<br />`
        'first_name'\: 'Sigrid',  :raw-html:`<br />`
        'last_name'\: 'Mannock',  :raw-html:`<br />`
        'age'\: 27,  :raw-html:`<br />`
        'amount'\: 7.17})  :raw-html:`<br />`
    data['clients'].append({  :raw-html:`<br />`
        'first_name'\: 'Joe',  :raw-html:`<br />`
        'last_name'\: 'Hinners', :raw-html:`<br />`
        'age'\: 31, :raw-html:`<br />`
        'amount'\: [1.90, 5.50]}) :raw-html:`<br />`
    data['clients'].append({ :raw-html:`<br />`
        'first_name'\: 'Theodoric', :raw-html:`<br />`
        'last_name'\: 'Rivers', :raw-html:`<br />`
        'age'\: 36, :raw-html:`<br />`
        'amount'\: 1.11}) :raw-html:`<br />`
    l2=LogFile("log2") :raw-html:`<br />`
    l2.fromDict(data) ::

First, log2.json file is made.

    {
    :raw-html:`<br />`
        "clients"\: [
        :raw-html:`<br />`
            {
            :raw-html:`<br />`
                "first_name"\: "Sigrid",
                :raw-html:`<br />`
                "last_name"\: "Mannock",
                :raw-html:`<br />`
                "age"\: 27,
                :raw-html:`<br />`
                "amount"\: 7.17
                :raw-html:`<br />`
            },
            :raw-html:`<br />`
            {
            
                "first_name"\: "Joe",
                :raw-html:`<br />`
                "last_name"\: "Hinners",
                :raw-html:`<br />`
                "age"\: 31,
                :raw-html:`<br />`
                "amount"\: [
                :raw-html:`<br />`
                    1.9,
                    :raw-html:`<br />`
                    5.5
                    :raw-html:`<br />`
                ]
                :raw-html:`<br />`
            },
            :raw-html:`<br />`
            {
            :raw-html:`<br />`
                "first_name"\: "Theodoric",
                :raw-html:`<br />`
                "last_name"\: "Rivers",
                :raw-html:`<br />`
                "age"\: 36,
                :raw-html:`<br />`
                "amount"\: 1.11
                :raw-html:`<br />`
            }
            :raw-html:`<br />`
        ]
        :raw-html:`<br />`
    } ::

Then, log2.json is read as a .pfcf file.

Finally, it is printed.

        clients\: 
            
                first_name\: Sigrid
    
                last_name\: Mannock
    
                age\: 27
    
                amount\: 7.17
            
    :raw-html:`<br />`
      :raw-html:`<br />`
      :raw-html:`<br />`
                first_name\: Joe
    
                last_name\: Hinners
    
                age\: 31
    
                amount\: 
                    1.9
    
                    5.5
                :raw-html:`<br />`
                :raw-html:`<br />`
                :raw-html:`<br />`
                
                first_name\: Theodoric
 
                last_name\: Rivers

                age\: 36 ::
                
##############
Style commands
##############

Adding a new line
*****************
Add the comma symbol to create a new line.

    This is a line,This is other line ::

Our exported file will be something like this:

    This is a line
    :raw-html:`<br />`
    This is other line ::


Paragraphs
**********
Add the vertical line symbol to create a new paragraph. :raw-html:`<br />`
Always we must write a comma before the vertical line symbol.

    This is a paragraph,|This is other paragraph ::

Our exported file will be something like this:

    This is a paragraph
    
    This is other paragraph ::

We can also write the comma symbol twice, but Pyfoch will not recognize it like a new paragraph.

    This is a paragraph,,This is a a line in the same paragraph\\, which looks like another paragraph ::

The aesthetic result will be the same:

    This is a paragraph
    
    This is a a line in the same paragraph, which looks like another paragraph ::

Note we use the "\\" symbol in order to Pyfoch do not recognize the comma like a new line command. :raw-html:`<br />`
In general, we say that the "\\" symbol scapes the next character. 

Adding a new block of text
**************************

Write the text between the labels "$block begin" and "$block end". :raw-html:`<br />`
Pyfoch will recognize it like Python code.

    This is a common line.,| :raw-html:`<br />`
    $block begin :raw-html:`<br />`
    This is a line in a block of text.,| :raw-html:`<br />`
    $block end :raw-html:`<br />`
    This is another common line ::

Our exported file will be something like this:

    This is a common line.
    
      This is a line in a block of text.
      
    This is another common line ::

$block begin" and "$block end" are both changeability commands. :raw-html:`<br />`
Changeability commands are further explored below.


##################
Insertion commands
##################

Adding code written in Python
*****************************

Write the text between the labels "<python>" and "</python>". :raw-html:`<br />`
Pyfoch will recognize it like Python code.

    <python>
    :raw-html:`<br />`
    print("Hello World")
    :raw-html:`<br />`
    </python>::

Our exported file will be something like this:

    print("Hello World") ::

This will be useful when you domain changeability commands. :raw-html:`<br />`
Changeability commands are further explored below.

Adding code written in Wolfram Language
***************************************

Write the text between the labels "<wolfram>" and "</wolfram>". :raw-html:`<br />`
Pyfoch will recognize it like Wolfram Language code.

    <wolfram>
    :raw-html:`<br />`
    Range[5]
    :raw-html:`<br />`
    </wolfram> ::

Our exported file will be something like this:

    Range[5] ::

In general, if "alanguage" is a supported programming language, write the text between the labels "<alanguage>" and "</alanguage>" in order to Pyfoch recognize it like "alanguage" code.

#################################
Introduction to the changeability
#################################

The heart of PFCF language is the changeability. Changeable code has a marked tendency to change. :raw-html:`<br />`
PFCF use the changeability in order to improve the efficience in the coding development experience.

Add the "$" symbol to write a new changeability command. For example, let's say Pyfoch we want to start a new text block.

    $block begin ::

The general sintaxis is simple:

    $command parameter ::

Always we must write in a new line after writting a changeability command.

####################################
Writting NQS code with Pyfoch
####################################

PFCF suports Natural Quantum Script code, language that simplifies the quantum code development. :raw-html:`<br />`
This scripts are currently deprecated. [Learn more about NQS here](https://nqs.rtfd.io)

NQS is first-based in IBM qiskit. Write the text between the labels "<qiskit>" and "</qiskit>". :raw-html:`<br />`
Pyfoch will recognize it like NQS commands. 

    <qiskit>
    :raw-html:`<br />`
    "Your code"
    :raw-html:`<br />`
    </qiskit>::
