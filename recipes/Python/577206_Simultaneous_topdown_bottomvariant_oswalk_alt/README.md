## Simultaneous topdown and bottomup variant of os.walk() (alt. title: "Delete .pyc files and empty directories recursively") 
Originally published: 2010-04-21 20:16:08 
Last updated: 2010-04-21 20:16:09 
Author: George Sakkis 
 
The standard lib os.walk() function provides a topdown parameter that determines whether entries are yielded in a top-down or a bottom-up order. Sometimes though you may want each directory yielded twice; once before any of its children directories (and recursively their descendants) are yielded and once after they are all yielded. The walk2() function below does this by yielding 4-tuples; the first 3 elements are the same yielded by os.walk() and the 4th is True the first time (topdown) and False the second (bottomup).