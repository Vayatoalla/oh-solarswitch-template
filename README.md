# oh-solarswitch-template
A rule template to switch on/off a device depending off a a max and min threshold, like the power consumption of a house

This is mainly an step by step method to setup the switch of a 'Load device', depending of the power that you have in your house.

In Configuration, Model Menu, select a location and Add Equipment
In the new Equipment you just created, add four points:
- Add a point of type 'switch', and semantic class status. This will be the switch that you will use to activate the  rule. Add a Metadata to define the type of switch that you prefer to use (here I have Default Cell Widget -> Default oh-cell
- Add a point of type 'string' and semantic class Control. This is a variable that will 'remember' the last state that was set by this rule. If at any point, the rule finds that the state of the controled device is not the same that the state in this variable, the rule will understand that someone switched on/off the controled device by any other means (i.e. a remote control), and thus, the rule with terminate.
- 'Shut down Threshold': Add a point of type 'number' and semantic class power. Add in Metadata the type of control you want to use here (I like to add 'Default List Item Widget' -> 'Stepper List Item' - oh-stepper-item).
- 'Shut on Threshold': Add a point of type 'number' and semantic class power. Add in Metadata the type of control you want to use here (I like to add 'Default List Item Widget' -> 'Stepper List Item' - oh-stepper-item).


Now we can begin with the Rules. We will need two rules.
Rule 1 - Switch on/off depending of the power in the house and posible overules.
