1Introduction

A framework for visualizing worldly phenomena using custom information graphics. The world is essentially an interconnected web of complex transactions being undertaken by its inhabitants who can have a direct or indirect impact on all or a subset of the populace.

The goal of this framework is to visualize the causes and effects of these transactions by simulating the scenarios. The fundamental assumption and objective behind developing this framework is that most of the worldly phenomena are invisible to us and their impact is only felt when it impacts us in the form of struggle (for example, struggle for survival). Be it the US subprime crisis, or the global warming, every such crisis has its root on an equilibrium state of the world which is disturbed as a result of a series of transactions. This framework could be used to visualize the entire cause and effect story from the equilibrium state to the imbalanced state and vice versa.

Similarly, it is also hoped that this framework can help to model and visualize many such phenomena which are difficult to gauge or perceive through naked eye. The best possible example which I can offer is the distribution of government collected tax from the treasury to the public scheme. An assessment of such processes through a visual model can help us to visualize the invisible and foresee the unforeseen. That is the final goal of this framework
2Overview

Model the world using the information stored and shared between the inhabitants of the world. An ideal way to visualize any worldly phenomena and its impact on the world.

A world consists of a boundary, a set of resources and a number of inhabitants. Inhabitants interact with each and the world to further their goals and objectives in their lives.  This is akin to the earth and the living beings which inhabit the planet. Earth is the world with plenty of natural resources and the living beings are the inhabitants of this world. The inhabitants interact with other inhabitants and the natural resources for their survival and that is their first objective. Further, they collaborate or connive with other inhabitants to either make progress of cause destruction, both resulting in a state of different equilibrium or instability.  

To model any phenomena in this way, we have to have a world defined by a set of boundaries and a set of resources. And then we also need to define inhabitants of the world, their senses, behaviours and actions. Based on these, we can model the phenomena occurring in the world and can visualize it .  Now lets take a deeper look at the components of this model framework.

The model will consist of three components.

1)The world view
2)The Visualized View
3)The shadowing interface

The World view is a scenegraph of the world, its resources and its inhabitants. It consists of all the data which constitutes the world, its resources, the inhabitants their senses, behaviours and actions. Apart from this, the world view also maintains additional things as follows
1.Additional information which identifies with some aspect of the inhabitants that need to be tracked.
2.Information related to the position and location on inhabitants within the world
3.Metadata related to the physical laws which govern the interaction in the world.  
4.Inhabitants acting as worlds for other inhabitants hence forming a tree hierarchy. 

The visualized view is the front end visualization which depicts the world view. It has a bounding shape to define the limits of the world, a visual representation of the world’s resources, of all the kinds of inhabitants, their senses, behaviour and actions and any other additional information. The visualized view can have the following features
1)Pan , tilt and zoom options
2)Viewing the information on a world resource
3)Viewing the information of an inhabitant 
4)Transforming the appearance of the inhabitant
5)Showing additional information as overlays
6)Showing derived information
7)Represent the senses, behaviour and actions and inhabitants with history.

The shadowing interface allows the constituents of the world view to interact with a real world system to emulate their behaviour. This helps to hook the model with a real system and visualize its model in real time or near real time basis. 

3Components

3.1World View

The world view is the container of the world and its constituent parts which consists of the inhabitants, which themselves can act as world for other inhabitants. Hence we have a tree like structure where we have a top world which can consist of many sub worlds. 

At the world or sub world level we have the following common elements
1.Traits – A trait identifies a set of behaviours, actions and observers exhibited by an inhabitant of the world.  Traits also include a set of common information. Several such traits can be defined within a world.
2.Constraints – Constraints are a set of rules  which enhance or limit the behaviour or actions of inhabitants
3.Space – The space defines the overall bounds of the world and its position in the parent world. For the root level World (known as Universe) there is no position.
4.Environment – A set of environments each of which consists of data parameters.
5.Event – Event is a set of changes on a environment . Every world maintains a set of such events. 
6.Children – All the inhabitants of the world represent the children of the world
7.Parent – The containing world of the world represent the parent of the world, The root world has no parent
8.Resources – A list of resources globally shared by all inhabitants of the world. There are a few types of resources available.

3.1.1Trait

A trait represents a set of things which are common to all the inhabitants of the world. The things are as follows

3.1.1.1Information

Information is identified by a set of data parameters which are maintained by all the inhabitants sharing the trait. There can be any number of data parameters defined per information set within a trait. The data parameters can be either transient or permanent.

3.1.1.2Behaviour

Behaviour is defined as a set of procedures performed by an inhabitant either implicitly or explicitly as a result of an action invoked upon it. Behaviours are modelled as follows

1.List of data parameters touched & actions to be initiated.
2.List of data parameters originated ( applicable only for transient data parameters)
3.List of data parameters modified
4.List of data parameters terminated ( applicable only for transient data parameters)

Every behaviour is also assigned a start time and end time with time intervals and for every time interval the above types of operations on data parameters and actions are modelled.

An implicit behaviour is also modelled by associating itself with a time and time frequency when it will be triggered.  And explicit behaviour is associated with one or more actions.

3.1.1.3Action

Action is defined as a named identity for any operation that is allowed by an inhabitant to be performed upon itself.   Actions act as an interface for an external entity to interact with the inhabitant. This external entity could be another inhabitant or world.

Actions are modelled as a name and a mapped set of behaviours .  An action can also be mapped to no behaviour. 

Actions can be either explicit or implicit. Explicit actions on an inhabitant are always initiated by an external entity whereas the internal actions are always a result of the observer triggers.
3.1.1.4Observers

Observer act as the sensory mechanism which help the inhabitants decipher the happenings in their surroundings.

Four types of observers are defined
1.Sight – Allows an inhabitant to gauge the proximity of the other inhabitants and the world’s bounds.
2.Touch – Touch allows the inhabitant to know if any other inhabitant has touched it or not which basically means that the two inhabitants have shared some common space within the world
3.Hearing – Hearing allows the inhabitants to gauge certain behaviours being exhibited by other inhabitants within its vicinity. 
4.Monitoring – Monitoring allows the inhabitant to sense any events occurring in its world. 


3.1.2Constraints

A constraint is a rule which applies to the entire world and its inhabitants.
A rule is consisting of a decision logic and a result
The rule can have any number of steps based on conditional logic performed on the following

1.Data parameters of an inhabitant
2.Data parameters of an environment
3.Action mapped / not mapped to a behaviour
4.Observer mapped / not mapped to a action
5.Position of inhabitant
6.Trigger of any of the observer senses

The result of the rule can be as follows
1.Modification of data parameter of and inhabitant
2.Modification of data parameter of an environment
3.Mapping or unmapping of action to a behaviour
4.Enabling or disabling of observer senses
5.Triggering of an event or changing of event trigger parameters.

3.1.3Space

Space consists of two things
1.Overall bounds of the world / inhabitant – Rectangular bounded space occupied by the world/inhabitant
2.Position – Coordinate Position of the inhabitant in its parent world.

3.1.4  Environment

An environment is a set of data parameters which hold some information related to a particular aspect of the world. 

3.1.5Events

An event is like a behaviour which is exhibited by the world as a whole.
It is modelled just like the behaviour but the data parameters over here can be either belonging to the environments or any of the constituent inhabitants

Events can be fired either implicitly based on pre programmed time and frequency or as a result of a constraint.

3.1.6Children

Children is a list of all the immediate inhabitants of the world.

The inhabitants will have to following things associated with them
1.Adhere to one of the traits. Once an inhabitant belongs to a trait , it maintains an instance of each trait parameter within itself.
2.A set of data parameters which are specific to the inhabitant
3.A set of behaviours and actions which are specific to the inhabitants. These behaviours and actions are not known to the other inhabitants hence they can be invoked only implicitly by mapping them with observers.  
4.A name to globally identify the inhabitant within its parent world.
5.If the inhabitant acts as a world then it will also define the traits , constraints, environments and  events to be applied to its children. 


3.1.7Parent
Parent is the immediate parent world of the world in question. There is a top level world which is known as the universe and it does not have any parent. It is known as the supreme world entity.

3.1.8Resources
Any number of resources can be defined which can be a store of some quantity of heterogeneous stuff. Resources can be utilized by either taking the stuff or adding to it. A resource can be a depleting resource if the stuff cannot be added back to it.  

3.2Visualized View

The visualized view is the front end application which renders the entire world in a custom visualization. The primary goal of this application is to interface with the backend world view application and render all the interactions in the world view as a custom visualization.

For the visualized view to work properly it needs to understand three things
1)Underlying protocol for communication with the world view
2)Visual symbols for all the traits defined in the world view and their altered manifestations as per individual inhabitants
3)Visual elements which depict the actions and behaviours on inhabitants and events and constraints which impact the inhabitants. 

So just like the hierarchical model of the world view , we have a parallel hierarchical model of the visualized view which is modelled in the same way. This model maintains a set of data for the following
1.Visual representation of all traits, their behaviours, actions and observer senses.
a.This is based on the impacted inhabitants
b.The visual representation can be in form of transitions or a fixed representation.
2.Visual representation of all events 
a.This is also be either a global visual representation or a representation based on the impacted inhabitants

3.3 Shadowing Interface

Shadowing interface allows the world view to interact with a real system. Many a times the world view is actually a model of a real system and rather than visualizing it in a simulated way we would want to hook it with a real system in  execution so that we can visualize the innards of that system to understand its working. The shadowing interface allows this kind of hook-ups

The shadowing interface has two components, the server side and client side.

The client side component is the one which is integrated into the external real world system and sends information to the server. The server side component is the module which is integrated into the world view.

The messages exchanged through the shadowing interface tell the world view about
1)Creation / Destruction of inhabitants
2)Invoking actions on inhabitants
3)Invoking events on the world
 

The world view accepts each message and explicitly invokes the commands on the respective inhabitants to actuate the system. 

The world view can work either in a shadowing mode or auto mode. The shadowing interface is applicable only in shadowing mode.
   
4Implementation

The entire framework will be based on discrete event simulation for allowing world events or individual inhabitant actions to fire at certain discrete points of time.

4.1Initialization

At the time of initialization the system will initialize the world view followed by the connectivity with the visualized view and optionally the shadowing interface.

4.1.1Initialization of the world view

#1 -	Prepare the scene graph by loading and storing the world data
#2 - 	Load the initial set of inhabitants and their data
#3 -	Initialize communication with the visualized view
#4 -	Initialize the shadowing interface ( Optional)
#5 -	Start simulation

4.1.2Initialization of the visualized view

#1 -	Get the top level world space parameters and render it
#2 -	Get the list of all children inhabitants and render them as per their trait
#3 - 	Wait for the world  view to start off the simulation

4.1.3Initialization of Shadowing interface

TBD

4.2Modelling

Modelling the various aspects of the world view is of prime importance for the maximum utilization of the framework. Modelling involves two aspects, data mode and visual model. 

Data model refers to the constituent data parameters which contain essential information about the various aspects   and visual model contains the data which will be used for rendering the visual look and feel. 
4.2.1 Behaviour Modelling

Every inhabitant exhibits a behaviour, either unique or a common set of behaviours as part of its trait. Each behaviour involves a series of steps for updating or modifying its internal state information or performing action on itself or another inhabitant. Every behaviour also has a time span wherein the desired series of steps are spread across the entire time span.

So the data model for behaviour consists of the following
-Time span
-Logic to be performed on each time span and its resultant update
-The resultant update could be on data parameters of it could be an action ( internal or external) . This update information is stored as follows
oList of data parameters touched & actions to be initiated.
oList of data parameters originated ( applicable only for transient data parameters)
oList of data parameters modified
oList of data parameters terminated ( applicable only for transient data parameters)
-The logic is optional and can be ignored. In such cases the resultant update always happens. Logic is only a way to include decisions for performing resultant updates.
 The visual model of a behaviour consists of the following
-A combination of new , altered or overlaid visual representation combined with optional visual translation ( move, resize , scale rotate , overlay , additional shapes ) of the inhabitant who exhibits the behaviour 
-The visual representation can be derived from the information in the data parameters of the inhabitant
-The visual representation can be in the form of transition across the time span of the behaviour. 

4.2.2Action Modelling

Actions refers to a certain activity which is actuated upon an inhabitant either by itself or by another inhabitant or as a result of a world event. An action always elicits behaviour and the action model consists of the triggering decision and the mapped behaviour
  
The Data model of an action consists of
-Trigger logic. Trigger logic is based on self-data parameters or constraints or a preset time and/or interval or world event
-Target – Target refers to the set of inhabitants on which the action is invoked. Target is either applicable to all inhabitants or is decided based on a decision logic under the influence of constraints.
-Mapped behaviour -   Every action elicits behaviour so for every action there is a behaviour which is defined.

The visual model of an action consists of 
-An overlaid visual representation of the action being initiated by an actor and performed on an acted.

4.2.3Observer Modelling

Observers act as the senses for the inhabitants of the world. But every inhabitant’s observatory senses may be enabled or disabled based on their behaviour or constraints. Also each observer sense can be hooked to one implicit action.

Hence the data model for the observers comprise of the flag to indicate whether its enabled or disabled and a mapping to an action.

Visual model of the observers will consist of micro icons overlayed on the visual representation of the inhabitant to indicate which observers are enabled for it. When an observer is actuated it will trigger an action which will be visible via the actions visual model. 
4.2.4Constraint Modelling

Constraint is a global rule which applies to all inhabitants of the world.

Every constraint is a set of conditional logic and its result defined in a sequence of steps. The constraints are triggered at every time interval of the world simulation but can be disabled by other constraints either definitely or indefinitely. 

A constraint has no visual model, however at an inhabitant level, the visualized view should be able to show the history of all the constraints which have been applied to it.

4.2.5Resource Modelling

A resource is identified by a set quantity of some arbitrary data stuff which is maintained as the world level.   The data model of resource is the numeric value of the data , either in integer or floating point form and the total capacity. Visual model of the resource is expressed in the form of a bar to display the percentage of resource available and in case of unlimited capacity it is just the number display of the quantity.

   









Visual elements also have senses which help them to interact with the world and respond to the various external triggers.

Just like we have the five basic senses namely , touch , sight , hearing , taste and smell , in the world of visualization the three essential sense are touch , sight and hearing.

Touch allows the visual elements to sense whether they have collided with each other or not.

Sight allows the visual elements to sense the proximity to other visual elements or the external objects or boundaries of the world.

Hearing allows the visual elements to sense and perceive shout out calls from other elements. It is like listening to other elements.

Like the physical world around us , the visual elements are also encompassed within a world which is defined by a definite space and just like our physical world exhibits some behaviour based on physical phenomena , the visualized world view also has some similar behaviours.  And lastly , just like our world has some natural resources, on which we chiefly rely upon for our well-being, similarly the visualized world also has some of resources which are utilized by all visual elements.

So the visual elements are the so called inhabitants of the visualized virtual world which interact with the world , and other visual elements.

Now if we equate visual elements with the living beings of the world, then we can also say that the visual elements have a state, and a set of traits & behaviours.  This is akin to our state of mind and a set of basic behaviours which govern our interaction with the fellow living beings around us and the world at large.      

So visual elements have a state (state of mind), a set of traits which decide the state and a set of behaviours which are derived from the current state.  These behaviour manifest as external actions which allow the visual elements to interact with the world and other inhabitants.

So here is the top down world view of the visualized virtual world (VVW).

A VVW consist of many scenes, each of them containing a world with certain resources and a set of inhabitants as visual elements (VE). Each VE has a set of states, traits and behaviours.  And apart from this the world also defines a set of actions that can be performed by a VE on other VEs and the world’s resources and a set of physical phenomena which defines the rules for those actions.   
