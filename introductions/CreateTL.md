##### 1. Concept and Thinking Process
Timeline creation in general is a recursive process. See the following diagram for a better picture:

![Recursive TL Creation Process](RecursiveProcess.png)

###### 1.1 What we are essentially doing is breaking union burst execution times into waves.

###### 1.2 When we are satisfy with the current wave, we proceed to the next wave.

###### 1.3 If a previous wave has direct impact on the outcome of current wave, we go back to adjust the causing wave to make the current wave satisfactory.
In this case, it is more of an iterative process as you are going back to certain iteration which has a direct impact to subsequent iterations. We will not go into the details with the differences between iterative and recursive process, but at this point you should get the idea of what timeline creation is.
```cs
long desiredDamage = 999999;
long currentDamage = 0;
for (int i = 0; ; i++)
{
    bool needs_to_adjust_previous_iteration = false;
    int the_iteration_needs_to_be_adjusted = i;
    // set ub for each characters
    // let battle proceed until all UB set has been executed
    // if we need to adjust previous iteration, 
    // needs_to_adjust_previous_iteration = true
    // the_iteration_needs_to_be_adjusted = n

    if (needs_to_adjust_previous_iteration)
        i = the_iteration_needs_to_be_adjusted;

    if (desiredDamage > currentDamage)
        break;
}
```

##### 2. How Princess Studio Helps
Princess Studio provides graphical details of the battle, including skill starting frame, ending frame, and effective frame. Princess Studio show these details using bar graph and listbox. Another important feature Princess Studio assists in the timeline creation process is the AutoUB feature. AutoUB allows you to set union burst execution frame so the character will attempt to execute the frame you set when it is possible.