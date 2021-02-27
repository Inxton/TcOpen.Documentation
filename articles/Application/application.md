# TcOpen application

## Dissection

TcOpen application has a structure that aims to provide a standardized skeleton, series of helper features to aid to write scalable, observable applications.

### Core components

Basic components of TcOpen application are in ```TcoCore``` library. There are several abstract blocks and interfaces that need to be take concrete definition in the consumer application.

These are the core blocks

#### TcoContext : ITcoContext

Provides context for an TcOpen application or its part(s). There are some core function that relay on the members of the context block, such state auto-restore of objects (e.g. components, state machines). This object should contain other block that logically belong to its context.

#### TcoObject : ITcoObject

Anu block of the TcOpen application should inherit from ```TcoObject``` class in order to get access the applications resources. ```TcoObject``` must have a context assigned at the construction via ```FB_init()```. In this way ```TcoObject```s are organized in a tree like structure in which querying of parent and child object is applicable. This allow for a streamlined communication of contextualized information between the object.

#### TcoState : ITcoState

Provides a simple mechanism for controlling the state and state transitions.

#### TcoTask : ITcoTask

Provides a form of Task pattern that allow for asynchronous execution and control of a tasks.

#### TcoSequencer : ITcoSequencer

This is more advanced coordination primitive that provided control over sequential logic execution, controlled state change and advanced step mode (e.i. step-by-step operations, step skipping).
