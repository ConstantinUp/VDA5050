This markdown file is the original UML diagram from which handling_multiple_actions.png was created. Changes in the diagram can be tracked via changes in this file.

```
@startuml
scale 0.65
skinparam defaultTextAlignment center
start
:AGV arrives at node \nwith multiple actions;
#lightgreen:parallel execution list = [];
#lightgreen:iterate over action list;
repeat
    if (action:\n blockingType) then (HARD)
        #lightgreen: stop driving;
        #lightgreen: Execute actions in \n parallel execution list\n in parallel (if any);
        #lightgreen: Execute HARD action;
    else
        if () then(SOFT)
        #lightgreen: stop driving;
        else(NONE)
        endif
        #lightgreen: Add action to parallel\n execution list;
    endif
repeat while (More actions \non node?) is (Yes) not (No)
if (parallel\n execution list\n empty?) then(Yes)

else(No)
#lightgreen: Execute actions from\n parallel execution list;
endif
#lightgreen: Continue order\n handling;
@enduml
```