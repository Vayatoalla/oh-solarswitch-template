# oh-solarswitch-template
This template creates a very simple rule that will allow you to control de state of a device based on the electricity that your house is spending. I will call this device 'the load'. The goal is to have a 'Solar Switch' that switches on/off the load only when your solar panels are generating enough power.

The rule should run every n minutes while the solar swith is on. This is achieve with another rule that you can create with the 'Threshold Alert and Open Reminder' template of @rlkoshak (thanks Rich).

So, hands on, here are the steps to create the 'Solar Switch'.

In Configuration, Model Menu, select a location and Add one Equipment. In the new Equipment you just created, add four points:
- Create the 'Solar switch', call it (for example) 'MyDevice Solar Switch': Add a point of type 'switch', and semantic class status. This will be the switch that you will use to activate the  rule, and thus, the device, but only when there is enough soloar production. Add a Metadata to define the type of switch that you prefer to use (here I use Default Cell Widget -> Default oh-cell).
- Add a point of type 'string' and semantic class Control. Lets call it 'ControlLoadifSunLastState' This is a variable that will 'remember' the last state that was set by this rule. If at any point, the rule finds that the state of the controled device is different that 'ControlLoadifSun', the rule will understand that someone wants to overule the SolarSwitch by any other means (i.e. a remote control), and thus, the rule will terminate.
- 'Switch off Threshold': Add a point of type 'number' and semantic class power. Add in Metadata the type of control you want to use here (I like to add 'Default List Item Widget' -> 'Stepper List Item' - oh-stepper-item).
- 'Switch on Threshold': Add a point of type 'number' and semantic class power. Add in Metadata the type of control you want to use here (I like to add 'Default List Item Widget' -> 'Stepper List Item' - oh-stepper-item).


Now we can begin with the Rules. We will need two rules.
- Rule 1 - Switch on/off depending of the power in the house and posible overules.
- Rule 2 - Will Run rule 1 every n minutes (the number of minutes is up to you :-)).

