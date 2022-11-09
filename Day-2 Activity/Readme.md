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

## The 7 CAPL Events and Functions

CAPL - Communication Access Protocol Language is used by Vector tools like CANoe and CANalyzer. It is an event based language, that can be used for automating/semi-automating in a CAN environment. Its mostly like C with few changes. Global variables can be declared in variables{} section, with functions and events following.

#### on start()
When we click the Measurement start - lightning icon to start our simulation in CANoe(or CANalyzer), the part of code here gets executed. 
Example:

on start()

{

write("This will be printed on start-up!");

}

### on pre-start()

This function will execute before start() event. This is useful for initting variables, setting delays etc. setStartdelay is a function unique to pre-start - that can be used to test timing parameters.

on pre-start()
		
		{
		
		write("this will be executed before start()!");
		
		}
		
#### on stop()

This event takes place on clicking the stop button in CANoe/CANalyzer window.

Example:

on stop()

{

write("You clicked the red stop button!");

}

### on key 'key-name'()

When key specified in 'key-name' is pressed, this event is triggered.

on key 'a'

{

write("When a is pressed, this happens");

}

#### on envvar "Envvar name"()

CANoe has objects called environment variables, which interact with the user. These environment variables must be created and defined in Database files associated with the simulation (".dbc" files). When the associated Env-var changes, this event is called. Example :

on envvar env_abc

{

write("Value of env_abc is %d",getvalue(this));

}

getvalue and putvalue are special functions, to get/put value of an environment value.
"this" pointer refers to current env_var here.

#### on message messagename()

This happens when the CAN message specified in messagename is received. messagename can be declared in variables{} portion and used here or else hex address can be given.

Example:

on message 0x100

{

int data=0;

data=0x100.byte(0);

write("Data in 0x100 first byte, %d",data);

}

variables

{

message 0x100 messagename;

}

		on message messagename()

{

write("Data in first byte, %d",messagename.byte(0));

}<

#### on timer()

Timers are special variables that trigger with a settimer() call and can be stopped with a canceltimer() call.

They are useful to run parallel tasks and sequentials tasks also and play a big role in automation.

Timers must be declared in variables{} section. There are two types of timers - mstimer and timer variables. Mstimer on setting, take values in Milliseconds and on timer event executes on completion of that value.

For Timer variable, on timer event takes place after the seconds specified in settimer call is lapsed.

Example:

variables

{

timer t1;

mstimer t2;

int t1delay=1;

int t2delay=1000;

}


on start()

{

settimer(t1,t1delay);

settimer(t2,t2delay);

}

on timer t1

{

write("One second has elapsed.");

settimer(t1,t1delay);

}

on timer t2

{

write("1000 Milliseconds have elapsed.");

settimer(t2,t2delay);

}

on key 'a'

{

canceltimer(t1);

canceltimer(t2);

}
			
