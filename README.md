# HoudiniEngineDev
A repository of tools to test your own Houdini Engine Implementation.
Houdini Engine is a product of SideFX. For more info on Houdini Engine please refer here:
https://www.sidefx.com/docs/hengine/

The repository is a $HOUDINI_PATH style directory of .hdas to test your custom integrations. There are a few categories of asset types including but not limited too :
  - User interface (ui)
  - Geometry types (geo)
  - Data types (attributes)
  - Dynamic scripts (scripts)
  - Inputs and outputs (inputs/outputs)
  - Contexts (obj/sop/rop)
  - Instances (instance)
  - Prints to console or from python (print)
  - Error handling (error)
  - Node creationn and deletion (nodes)
  - Multiple nodes, 
  - Code versus subnet tools (code), 
  - .otls vs .hdas
  - etc...

When integerating into your editor/engine, or dcc there is a wide array of features to implement. SideFX has this list of suggested steps which is a great start : 
https://www.sidefx.com/docs/hengine/_h_a_p_i__integration.html#HAPI_Integration_SuggestedSteps

As far as suggested requested features this is where this git repository is focused on. Generally people start with basic UI request and then expand from there. However in the UI alone there are over 39 parameter types, with over 20 per parameter options that are generally useful. The repo has 62 test cases currently for UI alone. Ontop of that are the hundred of other options you can integrate. In order to help I have created a tiered system based on thousands of hda I have come across in production of which features should be implemented in what order. Every integration is unique to the host system and what the pipeline needs, so this is more of a general hierachy and should be customized to your integration's needs.

### Tier 1
  - UI   - Parameters
    - float, int, toggle, string, vector float, vector int
  - UI   - Parameter Options
    - defaults, range, disable when, hide when, horizontal join(personal preference)
  - Geo  - Geometry Types
    - Polygon
  - Attr - Data Types
    - Point  - Position, Cd
    - Vertex - UVs, N
  
### Tier 2
  - UI   - Parameters
    - Variable numbers of floats, integers, strings that can have 2-16 values, or vector float/int from 2-4 values, buttons, labels, separators. You can limit your users to one type of parameter at first until you implement dynamic number of floats, integer, vectors.
  - UI   - Parameter Options
    - Drop down menus for integer and strings, then tags, invisible, help.
  - Geo  - Geometry Types
    - Nurbs, Heightfield, Packed Primitives
  - Attr - Data Types
    - Custom Data on 4 levels of attribute types - Point, Vertex, Primitive, Detail
    - Primitive - Material (This is highly unique to each system and will require multiple owners to implement)
    - Detail - Custom Data, Material can be define here too in different integrations
  - Instance
    - Object level, and copy to points  
  
### Tier 3
  - UI   - Parameters
    - multiparms as in standard folders, multiparm folders, ramps float and color
  - UI   - Parameter Options
    - folder end group, menu mini, menu replace, menu toggle,
  - Geo  - Geometry Types
    - 
  - Attr - Data Types
    - 
  - Prints - 
    - 
### Tier 4
  - UI   - Parameters
    - redundant parameters like menu ordered, operator path, operator list, file directory/geometry/image logarithmic float/integer, min/max float, color etc.
  - UI   - Parameter Options
    - 
  - Geo  - Geometry Types
    - 
  - Attr - Data Types
    - 
  - Inputs & Ouputs
  - Wiring multiple nodes together
  
### Tier 5
This tier is more for for error handling if one of these options does find it's way in. You don't want your whole system to crash because of an exception you could have have prevented. Additional this is for feature we never implemented, but could. Some were not fully implemented in the api at the time of our integrations, too.
  - UI   - Parameters
    - Key-Value Dictionary, Icon Strip,, Geometry Data, Data, Button Strip
  - UI   - Parameter Options
    - 
  - Geo  - Geometry Types
    - 
  - Attr - Data Types
    - 
  - Handles
    - These are a very cool option, but before they were implemented we just passed the geo data, based on the native handles. If you don't have native handles this becomes a lot more complex.

### Do not implement
There are somethings that should never be implemented.
  - UI   - Parameter Options
    - Import Blocks - These should never be used in production.
    
#Requested Features
These are a general list of additional test not in the repository yet.
- [ ] Per .hda test descriptions.
- [ ] TOPs test.

