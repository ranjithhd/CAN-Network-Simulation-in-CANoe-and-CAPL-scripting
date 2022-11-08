## Day-2 Activity-1

### The CAPL Browser

The CAPL Browser provides an easy-to-use “edit-thru-compilation” development process and is used to organize,
create, edit, and modify event procedures. The CAPL Browser is more than a text editor because it not only supports
source code development - it also organizes CAPL software into a tree-like structure of events, and it has an internal
compiler.
In this programmer’s environment, we can develop new programs, import and export source files, associate a
database, and compile CAPL software. The Browser is designed to quickly edit CAPL programs, and the integrated
compiler also makes it easy to trace errors after compilation. 

##### Figure shows a general example of the CAPL Browser API. 
![CAPL BROWSER](https://user-images.githubusercontent.com/115522470/200554394-b1e42294-fb95-4622-966a-5294883746c7.png)

### Starting the CAPL Browser

While the CAPL Browser can be started in several ways, the developer normally first adds program blocks to the
appropriate window in CANoe or CANalyzer and then double-clicks on the blocks to access the corresponding CAPL
program. In CANoe, clicking on the pencil icon on a network node within the Simulation Setup window will also
activate the CAPL Browser.
Although the CAPL Browser can be started as a stand-alone application, it is recommended that the program be used
from inside the CANoe or CANalyzer application to ensure that it properly recognizes the associated database,
hardware parameters, and CAPL-related DLLs. An example of incorrect compiling would be if the browser cannot find
the variables in the program that are defined in the database. 

#### Browser Organization
The CAPL Browser uses an event-driven control architecture with the corresponding CAPL program that is organized
into event procedures. The CAPL Browser’s main window is organized as shown in Figure. This arrangement
shows and supports the creation and modification of event procedures.

![CAPL Browser organization](https://user-images.githubusercontent.com/115522470/200554972-e50d658a-d8f6-4246-984a-5fbb51f49a2c.png)
