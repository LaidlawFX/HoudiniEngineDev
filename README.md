# HoudiniEngineDev
A repository of tools to test your own Houdini Engine Implementation.
Houdini Engine is a product of SideFX.
For more info on Houdini Engine please refer here:
https://www.sidefx.com/docs/hengine/

The repository is a $HOUDINI_PATH style directory of .hdas to test your custom integrations. 

There are a few categories starting with user interface (ui), geometry types (geo), data types (attributes), dynamic scripts (scripts), inputs and outputs (inputs/outputs), contexts (obj/sop/rop), instances (instance), prints to console or from python (print), error handling (error), node creationn and deletion (nodes), multiple nodes, code versus subnet tools, .otls and .hdas, etc.



There are a few category to test when doing your integration.

I had a system of tiers of parameters, and parameter options.
They each have an .hda to test them against and as sets.
There are 39 parameters and about 20 different parameter options you can implement. Some of them being redundant.
The github has a repo to test different components of the Houdini Engine connection. The UI ones would be the ones you'd be after about 59 test cases. (edited) 
Tier 1 was float, int, toggle, string, vector float, vector int, with parameter options of defaults, range, disable when, hide when, horizontal join(my preference). (edited) 

Ben Laidlaw [1:50 PM]
Tier 2 was variable numbers of floats, integers, vectors, strings(because you can have a float with 2 values or float vector 2) buttons, labels, separators. You can limit your users to one type of parameter at first until you implement dynamic number of floats, integer, vectors. Parameter Options were drop down menus for integer and strings, then tags, invisible, help.
Tier 3 were the multiparms as in standard folders, multiparm folders, ramps float and color, Parameter Option of folder end group
Tier 4 was the redundant parameters like menu ordered, operator path, operator list, file directory/geometry/image logarithmic float/integer, min/max float, color etc. Parameter Options  menu mini, menu replace, menu toggle,
Tier 5 was the ones I don't think we implemented or couldn't such as Key-Value Dictionary, Icon Strip,, Geometry Data, Data, Button Strip. But it was important to test these so they didn't crash the program when some one added something not supported
