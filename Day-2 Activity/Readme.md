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

The upper left window, the Events window, lists both the different types of CAPL events and the names of the
procedures associated with each event category in a tree view.
The upper right window, the Global Variables window, is used to declare all necessary global variables for the CAPL
program.
The lower right window, called the Event Procedure window, displays the source code entered for the selected
procedure highlighted in the Events window.
The bottom window, the Compiler window, shows compiler activities and results.
The windows have another layout that may be more suitable to some users. Global variables can be represented
either in an individual window or in the window displaying the procedure text. If the Event Procedure window is used
to display the global variables, then the global variables will not be shown if an event procedure is currently displayed.
This feature is in the Editor Options dialog, reached with the Options → Editor command. All CAPL programs
must be closed before it can be activated. 

#### The Events Window

The Events window lists all event procedure categories in a tree-type structure, which may be expanded by clicking on
it to view all currently defined event procedures.

The two types of events listed in the Events window are the following:

• System-specific events

• User-defined events

System-specific event categories include the following:

• System

• CAN Controller

• ErrorFrame

System-specific events only allow access to a set of pre-defined CAPL event procedures. Duplicates of these events
are not allowed.

User-defined event categories include the following:

• CAN Message

• Timer

• Keyboard

• Environment

• Function

The developer can create an unlimited number of user-defined events. 

## Day-2 Activity-2

## The 7 CAPL Events 

CAPL - Communication Access Protocol Language is used by Vector tools like CANoe and CANalyzer. It is an event based language, that can be used for automating/semi-automating in a CAN environment. Its mostly like C with few changes. Global variables can be declared in variables{} section, with functions and events following.

#### on start()
When we click the Measurement start - lightning icon to start our simulation in CANoe(or CANalyzer), the part of code here gets executed. 
Example:

on start()
		{
				write("This will be printed on start-up!");
		}
