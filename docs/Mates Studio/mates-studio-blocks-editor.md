---
tags:
  - Builder
---

# Mates Studio Blocks Editor


## Introduction

Mates Studio's Builder environment features a graphical programming interface, Blocks Editor, allowing both beginners and seasoned developers to control the flow of their application by simply visually connecting blocks.

![Block Editor Interface](img/block/editor-interface.png)

The image shows a newly started Builder project. Boxed are the parts of the Block Editor, the toolbox and the workspace.

1. **Toolbox**: This contains the available blocks that can be added to the workspace. Blocks are grouped into several categories to easily search for the desired features.
2. **Workspace**: As the name suggests, this is the main work area during development. This allows you to design the application's workflow.


Blocks are the fundamental elements of the Builder environment. These can be connected to each other in the workspace using their input and output connectors. 


### Block Input Types

Input connectors can either be value or statement input. These connectors are present in the right side of each block or internally in the case of value inputs. A block can have multiple input connectors.

Value Input Connector

:   ![Value Input Connector](img/block/connector-value-input.png)
:   This connector accepts a single value block

Statement Input Connector

:   ![Statement Input Connector](img/block/connector-statement-input.png)
:   This connector accepts multiple statement blocks

Blocks can also include internal inputs. Internal inputs provides fixed rules or items for the block. These can either be an integer input, a text input, a color input or a dropdown input.

Integer Input

:   ![Integer Input](img/block/integer-input.png)
:   A simple number input which automatically corrects the value to the nearest integer which falls under a preset allowable range

Text Input

:   ![Text Input](img/block/text-input.png)
:   A simple text input allowing to specify names or text value for the block

Color Input

:   ![Color Input](img/block/color-input.png)
:   A color input that provides a simple preset color selector

Dropdown Input

:   ![Dropdown Input](img/block/dropdown-input.png)
:   A dropdown selector which provided acceptable values that the block accepts
   

### Block Output Types

Output connectors are always present in either the left side, top side or top and bottom side of the block. These connectors can either be a value output or a statement output. A block can only have either a value or statement outputs, but not both types.

Value Output Connector

:   ![Value Output Connector](img/block/connector-value-output.png)
:   This connector can connect to blocks with a value input connector

Statement Output Top and Bottom Connector

:   ![Statement Output Top and Bottom Connector](img/block/connector-statement-output-top-bottom.png)
:   This connector can connect to statement blocks with a top connector effectively joining the group of statement blocks. With the bottom connector, it allows more statement blocks to join the group.

Statement Output Top Connector

:   ![Statement Output Top Connector](img/block/connector-statement-output-top-only.png)
:   This connector can connect to statement blocks with the bottom connector effectively joining the group of statement blocks. Having no bottom connector, it is not possible to connect another block below this signifying the end of actions performed by the group.


### Blocks Classification

These blocks can be classified depending on their [output type](#block-output-types).

In terms of output, blocks can be classified as a function block, a value block or a statement block.

Function Block

:   These are blocks with no output connector. This type of blocks helps organize the workspace by simplifying repeated multi-block actions.

Value Block

:   These blocks provides a left output connector. This type of blocks provides a value to a parent block that will be used to perform the desired action.

Statement Block

:   These blocks provides the top connector and, optionally, the bottom output. This type if blocks can be connected together to group actions to be performed by a parent block with a statement input connector.


## Mates Blocks

The Mates category includes blocks that directly interact and control the screen. This include backlight, page, widget and touch related blocks.


### Main Application


:   ![Main Application Block](img/block/main_application.png)
:   All Builder project starts with the main application block. It provides two statement inputs named setup and loop.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | setup     | statement | allows developers to perform tasks at the beginning of the program which is during boot or immediately after a reset |
    | loop      | statement | allows developers to perform tasks indefinitely after performing the necessary setup |


### Graphics Blocks

This group contains blocks used for backlight, page and widget control and query.


#### Set Backlight Level

:   ![Set Backlight Level](img/block/set_brightness.png)
:   This block sets the backlight level of the display module.
:   | Input | Type      | Description                                      |
    |:-----:|:---------:|:------------------------------------------------ |
    | level | value     | intensity of backlight, must be between 0 and 15 |
:   !!! example 
        === "Set Backlight to Integer Value"

            ![Set Backlight to Integer Value](img/block/set_brightness.png){: class="custom-img-center" }

        === "Set Backlight to Variable Value"

            ![Set Backlight to Variable Value](img/block/set_brightness_variable.png){: class="custom-img-center" }


#### Set Page

:   ![Set Page](img/block/set_page.png)
:   This block changes the project to the selected page. The page dropdown input lists all pages included in the project.
:   | Input | Type      | Description                                      |
    |:-----:|:---------:|:------------------------------------------------ |
    | page  | value     | target page to change into                       |
:   !!! example 
        === "Set Page to Existing Page"

            ![Set Page to Existing Page](img/block/set_page.png){: class="custom-img-center" }

        === "Set Page to Variable Value"

            ![Set Page to Variable Value](img/block/set_page_variable.png){: class="custom-img-center" }


#### Get Page Index

:   ![Get Page Index](img/block/get_page.png)
:   This block can be used to query the current page of the running project.
:   !!! info "Return"

        Selected page


#### Get Current Page

:   ![Get Page](img/block/get_page.png)
:   This block can be used to query the current page of the running project.
:   !!! info "Return"

        Active page

:   !!! example "Example: Evaluate Page"

        ![Evaluate Page](img/block/evaluate_page.png){: class="custom-img-center" }


#### Get Number of Pages

:   ![Get Number of Pages](img/block/get_number_of_pages.png)
:   This block can be used to check the number of pages included in the project.
:   !!! info "Return"

        Number of pages in project

:   !!! example "Example: Increment Page and Loop to Page0"

        ![Increment Page and Loop to Page0](img/block/increment_page_loop.png){: class="custom-img-center" }

#### Set Widget Value

:   ![Set Widget Value](img/block/set_widget_value.png)
:   This block changes the value of the selected widget. The widget dropdown input lists all applicable widgets.
:   | Input  | Type      | Description                                      |
    |:------:|:---------:|:------------------------------------------------ |
    | widget | dropdown  | the target widget                                |
    | value  | value     | the value the target widget will be set to       |
:   !!! example 
        === "Set Gauge to Integer Value"

            ![Set Gauge to Integer Value](img/block/set_gauge_value.png){: class="custom-img-center" }

        === "Set Gauge to Variable Value"

            ![Set Gauge to Variable Value](img/block/set_gauge_value_variable.png){: class="custom-img-center" }

        === "Set Gauge to Slider Value"

            ![Set Gauge to Slider Value](img/block/set_gauge_value_slider.png){: class="custom-img-center" }

            !!! note

                It is recommended to simply link values of widgets by setting their properties as discussed [here](mates-studio-graphics-editor.md#linking-widgets).


#### Get Widget Value

:   ![Get Widget Value](img/block/get_widget_value.png)
:   This block queries the value of the selected widget. The widget dropdown input lists all applicable widgets.
:   | Input  | Type      | Description                                      |
    |:------:|:---------:|:------------------------------------------------ |
    | widget | dropdown  | the target widget                                |
:   !!! info "Return"

        Value of the target widget

:   !!! example 
        === "Store Slider Value"

            ![Store Slider Value](img/block/store_slider_value.png){: class="custom-img-center" }

        === "Set Gauge to Slider Value"

            ![Set Gauge to Slider Value](img/block/set_gauge_value_slider.png){: class="custom-img-center" }

            !!! note

                It is recommended to simply link values of widgets by setting their properties as discussed [here](mates-studio-graphics-editor.md#linking-widgets).


#### Set Spectrum Column Value

:   ![Set Spectrum Column Value](img/block/set_spectrum_column_value.png)
:   This block changes the value of the selected column of the target spectrum. The spectrum dropdown input lists all Spectrum widgets in the project.
:   | Input    | Type      | Description                                      |
    |:--------:|:---------:|:------------------------------------------------ |
    | column   | value     | the target column index, must be less than number of columns of the target spectrum |
    | Spectrum | dropdown  | the target Spectrum widget                       |
    | value    | value     | the value the target column will be set to       |


#### Update TextArea

:   ![Update TextArea](img/block/update_textarea.png)
:   This block updates the target TextArea. The TextArea dropdown input lists all TextArea widgets in the project.
:   | Input    | Type      | Description                                      |
    |:--------:|:---------:|:------------------------------------------------ |
    | TextArea | dropdown  | the target TextArea widget                       |
    | format   | dropdown  | the formatting to use when writing the value     |
    | value    | value     | the value to update the DotMatrix with           |


#### Update DotMatrix

:   ![Update DotMatrix](img/block/update_dotmatrix.png)
:   This block updates the target DotMatrix. The DotMatrix dropdown input lists all DotMatrix widgets in the project.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | DotMatrix | dropdown  | the target DotMatrix widget                      |
    | format    | dropdown  | the formatting to use when writing the value     |
    | value     | value     | the value to update the DotMatrix with           |


#### Clear PrintArea

:   ![Clear PrintArea](img/block/clear_printarea.png)
:   This block clears the target PrintArea. The PrintArea dropdown input lists all PrintArea widgets in the project.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | PrintArea | dropdown  | the target PrintArea widget                      |


#### Set PrintArea Color

:   ![Set PrintArea Color](img/block/set_printarea_color.png)
:   This block sets a new color for the target PrintArea to use. The PrintArea dropdown input lists all PrintArea widgets in the project.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | PrintArea | dropdown  | the target PrintArea widget                      |
    | color     | value     | the new color value to use when appending to the target PrintArea |


#### Append to PrintArea

:   ![Append to PrintArea](img/block/append_to_printarea.png)
:   This block appends the specified value to the target PrintArea. The PrintArea dropdown input lists all ASCII type PrintArea widgets in the project.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | format    | dropdown  | the formatting to use when writing the value     |
    | value     | value     | the value to update the PrintArea with           |
    | PrintArea | dropdown  | the target PrintArea widget                      |


#### Append Bytes to PrintArea

:   ![Append Bytes to PrintArea](img/block/append_bytes_to_printarea.png)
:   This block appends the specified array to the target PrintArea. The PrintArea dropdown input lists all HEX type PrintArea widgets in the project while the array dropdown lists all variables in the project.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | count     | integer   | the number of bytes to write from the array      |
    | array     | dropdown  | a variable with an array of values to update the PrintArea with |
    | PrintArea | dropdown  | the target PrintArea widget                      |
:   !!! note

        1. A variable _array_ is automatically created if it doesn't exist.
        2. Ensure that the variable selected is initialized as an array using the [Create Array](#create-array) block.


#### Append Values to Scope

:   ![Append Values to Scope](img/block/append_to_scope.png)
:   This block appends the specified array to the target Scope. The Scope dropdown input lists all Scope widgets in the project while the array dropdown lists all variables in the project.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | count     | integer   | the number of values to write from the array     |
    | array     | dropdown  | a variable with an array of values to update the Scope with |
    | Scope     | dropdown  | the target Scope widget                          |
:   !!! note

        1. A variable _array_ is automatically created if it doesn't exist.
        2. Ensure that the variable selected is initialized as an array using the [Create Array](#create-array) block.


### Touch Input Blocks

Touch input blocks are only available for BBM modules with a touchscreen interface.


#### Get Event Button ID

:   ![Get Event Button ID](img/block/get_event_button_id.png)
:   This block provides a selection of all buttons recording an event. This is useful when evaluating the recorded button events. The button dropdown input lists all Momentary and Grouped button widgets in the project.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | button    | dropdown  | the momentary or grouped button                  |
:   !!! info "Return"

        ID of the selected button


#### Get Number of Recorded Button Events

:   ![Get Number of Recorded Button Events](img/block/get_number_of_button_events.png)
:   This block can be used to query the number of unread recorded button events.
:   !!! info "Return"

        Number of unread button events


#### Get Next Button Event

:   ![Get Next Button Event](img/block/get_next_button_event.png)
:   This block can be used to read/query the source of the next recorded button event.
:   !!! info "Return"

        ID of the source button


#### Get Number of Recorded Swipe Events

:   ![Get Number of Recorded Swipe Events](img/block/get_number_of_swipe_events.png)
:   This block can be used to query the number of unread recorded swipe events.
:   !!! info "Return"

        Number of unread swipe events


#### Get Next Swipe Event

:   ![Get Next Swipe Event](img/block/get_next_swipe_event.png)
:   This block can be used to read the value of the next recorded swipe event.
:   !!! info "Return"

        Value of the swipe event

:   !!! note

        This value needs to be stored in a [variable](#variables) and evaluated using [Evaluate Horizontal Swipe](#evaluate-horizontal-swipe) or [Evaluate Vertical Swipe](#evaluate-vertical-swipe) blocks.


## Utility Blocks

This group provides useful blocks for designing program flow (conditions, loops, etc.), basic computation and value assignments.


### Logic Blocks


#### Logical Comparison

:   ![Logical Comparison](img/block/logic_compare.png)
:   This allows developers to create comparisons which is typically used as test conditions that can be evaluated by other blocks.
:   ![Logical Comparison Options](img/block/logic_compare_dropdown.png)
:   Available comparisons are as shown.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | a         | value     | left side value for the comparison               |
    | operator  | dropdown  | equality operators for testing the two values    |
    | b         | value     | right side value for the comparison              |
:   !!! info "Return"

        Result of the comparison, true or false

:   !!! example 
        === "Evaluate Value of Variable"

            ![Evaluate Variable Value](img/block/logic_compare_variable.png){: class="custom-img-center" }

        === "Compare Two Variables"

            ![Compare Two Variables](img/block/logic_compare_variables.png){: class="custom-img-center" }

        === "Store Result"

            ![Store Result](img/block/logic_compare_store.png){: class="custom-img-center" }


#### Logical Operations

:   ![Logical Operation](img/block/logic_operation.png)
:   This allows developers to combine multiple [Logical Comparisons](#logical-comparison). This can be nested as multiple Logical Operation blocks. This is also typically used as test conditions that can be evaluated by other blocks.
:   ![Logical Operation Options](img/block/logic_operation_dropdown.png)
:   Available operations are as shown.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | a         | value     | left side value for the operation                |
    | operator  | dropdown  | logical operators for joining the two values     |
    | b         | value     | right side value for the operation               |
:   !!! info "Return"

        Result of the operation, true or false

:   !!! example
        === "Check if Both are True"

            ![Check if Both are True](img/block/logic_operation_and.png){: class="custom-img-center" }

        === "Check if Any is True"

            ![Check if Any is True](img/block/logic_operation_or.png){: class="custom-img-center" }

        === "Store Result"

            ![Store Result](img/block/logic_operation_store.png){: class="custom-img-center" }


#### Logical Negate

:   ![Logical Not Operation](img/block/logic_not.png)
:   This allows developers to invert the output of [Logical Comparisons](#logical-comparison) and [Logical Operations](#logical-operations) and is also typically used as test conditions that can be evaluated by other blocks.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | condition | value     | the condition to evaluate and negate             |
:   !!! info "Return"

        Negated value of the test condition

:   !!! example
        === "Negate Variable"

            ![Negate Variable](img/block/logic_negate_variable.png){: class="custom-img-center" }

        === "Negate Logical Comparison"

            ![Negate Logical Comparison](img/block/logic_negate_comparison.png){: class="custom-img-center" }

        === "Store Result"

            ![Store Result](img/block/logic_negate_store.png){: class="custom-img-center" }


#### Logical Ternary Operation

:   ![Logical Ternary Operation](img/block/logic_test.png)
:   This allows developers to evaluate the output of [Logical Comparisons](#logical-comparison) and [Logical Operations](#logical-operations) and return a value depending on the truthfulness of the test condition.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | test      | value     | the condition to evaluate                        |
    | true      | value     | the return value if condition is true            |
    | false     | value     | the return value if condition is false           |
:   !!! info "Return"

        The evaluated return value

:   !!! example
        === "Test Variable"

            ![Test Variable](img/block/logic_test_variable.png){: class="custom-img-center" }

        === "Test Logical Comparison"

            ![Test Logical Comparison](img/block/logic_test_comparison.png){: class="custom-img-center" }

        === "Store Result"

            ![Store Result](img/block/logic_test_store.png){: class="custom-img-center" }


#### Conditional If-Else

:   ![If-Else Block](img/block/if_else.png)
:   This allows developers to evaluate test conditions that will be evaluated to select which group of tasks to perform. Test conditions are usually created using the [Logical Comparison](#logical-comparison) block.
:   ![If-Else Configuration](img/block/if_else_configuration.png)
:   The block can be configured to add multiple test conditions (_else if_) and a default (_else_) condition which is triggered when none of the specified test conditions are met.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | condition | value     | condition to evaluate before performing tasks    |
    | do        | statement | all the tasks to perform if condition is true    |
:   !!! note

        Number of _condition_ and _do_ inputs increases depending on configuration
    

#### Evaluate Horizontal Swipe

:   ![Evaluate Horizontal Swipe](img/block/evaluate_horizontal_swipe.png)
:   This block evaluates the selected variable for the horizontal direction of swipe. The variable must be previously set to the [Get Next Swipe Event](#get-next-swipe-event) block. Developers can use this to perform different tasks depending on whether the screen is swiped going left or right.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | variable  | dropdown  | the variable to evaluate for the swipe direction |
    | right     | statement | all the tasks to perform if the swipe event is from left to right |
    | left      | statement | all the  tasks to perform if the swipe event is from right to left |
:   !!! note

        1. This block is only available for BBM modules with a touchscreen interface.
        2. A variable _swipe_ is created automatically if it doesn't exist.


#### Evaluate Vertical Swipe

:   ![Evaluate Vertical Swipe](img/block/evaluate_vertical_swipe.png)
:   This block evaluates the selected variable for the horizontal direction of swipe. The variable must be previously set to the [Get Next Swipe Event](#get-next-swipe-event) block. Developers can use this to perform different tasks depending on whether the screen is swiped going up or down.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | variable  | dropdown  | the variable to evaluate for the swipe direction |
    | up        | statement | all the tasks to perform if the swipe event is upwards |
    | down      | statement | all the  tasks to perform if the swipe event is downwards |
:   !!! note

        1. This block is only available for BBM modules with a touchscreen interface.
        2. A variable _swipe_ is created automatically if it doesn't exist.
        

### Loops Blocks


#### Repeat Count

:   ![Repeat Count](img/block/loop_repeat_count.png)


#### Repeat While or Until

:   ![Repeat While](img/block/loop_repeat_while.png)
:   ![Repeat Options](img/block/loop_repeat_options.png)
:   ![Repeat Until](img/block/loop_repeat_until.png)


#### Count with Variable

:   ![Count with Variable](img/block/loop_count_variable.png)
:   !!! note

        A variable _i_ is created automatically if it doesn't exist.


#### Break or Continue

:   ![Break Loop](img/block/break_and_continue.png)
:   ![Continue Next Iteration](img/block/continue_next_iteration.png)



### Math Blocks


### Text Blocks


### Arrays Blocks


#### Create Array


### Color Blocks


## System Blocks

This group provides useful blocks allowing developers to utilize additional hardware features available for the BBM module.


### GPIO Blocks


### Timers Blocks


### Serial Blocks


### I2C Blocks


### 1-Wire Blocks


## Dynamic Blocks

Dynamic blocks can be created multiple times. These can be used to further expand and provide more freedom in project development.


### Variables

Variables are key components in text programming. The builder environment allows creation of global variables. Once a variable is created, setter, getter and change blocks are generated.

A setter block allows the variable to be set while a getter block queries the value of the variable. A variable change block can be used to increase or decrease the value of the variable.

All of these blocks provides a dropdown selector listing the available variables. From the dropdown selector, several actions can be performed including selection, renaming and deletion of the variables.

A variable can be created by going to the Variables category and clicking the Create variable button.

![Create Variable](img/block/create-variable.png)

This will open a prompt requesting a new variable name.

![New Variable Prompt](img/block/new-variable-prompt.png)

Alternatively, some blocks generate variables it requires. Create Function blocks generate their inputs as new variables if these don't exist. Other blocks that behave this way are blocks with variable dropdown which defaults to a specific variable name, in case the variable doesn't exist yet.


#### Set Variable

:   ![Set Variable](img/block/get_variable.png)
:   This blocks allows developers to set the value of the selected variable.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | variable  | dropdown  | the target variable to set                       |
    | value     | value     | the value to set the variable to                 |


#### Get Variable

:   ![Get Variable](img/block/get_variable.png)
:   This blocks allows developers to query the current value of the selected variable.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | variable  | dropdown  | the target variable to query                     |
:   !!! info "Return"

        Value of the variable


#### Change Variable by Value

:   ![Change Variable](img/block/change_variable.png)
:   This blocks allows developers to change the value of the selected variable by the value specified.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | variable  | dropdown  | the target variable to change                    |
    | value     | value     | the value to change the variable by              |


### Functions

Functions are another useful feature from text-based programming. Like in text programming, the builder environment provided block functions allowing developers to simplify repeated actions by grouping the blocks together and allowing these group of actions to be called and performed using a single block.


#### Create Function without Return Input

:   ![Create Function without Return Input](img/block/create_function.png)
:   This allows developers to group blocks to perform every time the function is called.
:   ![Create Function without Return Input and with Value Inputs](img/block/function_inputs.png)
:   Functions can be configured to take one or more value inputs by clicking the gear icon of the block to edit the configuration. The configure function inputs are also added as global variables.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | name      | text      | unique name to identify the function             |
    | actions   | statement | all the actions to be performed by the function when called |


#### Create Function with Return Input

:   ![Create Function with Return Input](img/block/create_function_with_return.png)
:   This allows developers to group blocks to perform every time the function is called. It also provides a return value input. This is useful when performing reads or computations.
:   ![Create Function with Return Input and Value Inputs](img/block/function_return_and_inputs.png)
:   Functions can be configured to take one or more value inputs by clicking the gear icon of the block to edit the configuration. The configure function inputs are also added as global variables.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | name      | text      | unique name to identify the function             |
    | actions   | statement | all the tasks to be performed by the function when called |
    | return    | value     | the output value of the function after executing all tasks |


#### Function Return

:   ![Function Return Block](img/block/return.png)
:   This block can be used to exit a function if a certain condition is met. Depending on the type of function, with or without return input, this block will automatically transform as required
:   ![Function without Return Input and with Return Block](img/block/function_with_return_block.png)
:   If used in a function with no return input, this block transforms to suitable block as shown. Notice that the value input is removed.
:   ![Function with Return Input and Return Block](img/block/function_with_return_and_return_block.png)
:   If used in a function with a return input, this block reverts to its original state. Notice that the value input is added.
:   | Input     | Type      | Description                                      |
    |:---------:|:---------:|:------------------------------------------------ |
    | condition | value     | the condition to check for evaluating returns    |
    | return    | value     | the output value of the function (if applicable) |


#### Call Function

:   ![Call Function](img/block/call_function.png)
:   This block calls the function of the same name. This is available after a [function with no return input](#create-function-without-return-input) is created.
:   ![Call Function with Inputs](img/block/call_function_with_inputs.png)
:   This may have one or more value inputs depending on the configuration of the function.


#### Call Function and Return Value

:   ![Call Function and Return Value](img/block/call_function_with_return.png)
:   This block calls the function of the same name and returns the output value. This is available after a [function with return input](#create-function-without-return-input) is created.
:   ![Call Function with Inputs and Return Value](img/block/call_function_with_inputs_and_return_value.png)
:   This may have one or more value inputs depending on the configuration of the function.
:   !!! info "Return"

        Output of the function

