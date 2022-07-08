---
tags:
  - Commander
  - Architect
---

# Mates Controller Command Protocol


## Mates Commands

The table below lists the available commands to control the display module

| Command                     | Value  |
|:--------------------------- |:------:|
| MATES_CMD_SET_PAGE          | 0x0000 |
| MATES_CMD_GET_PAGE          | 0x0001 |
| MATES_CMD_SET_WIDGET_VALUE  | 0x0002 |
| MATES_CMD_GET_WIDGET_VALUE  | 0x0003 |
| MATES_CMD_SET_WIDGET_PARAM  | 0x0004 |
| MATES_CMD_GET_WIDGET_PARAM  | 0x0005 |
| MATES_CMD_SET_BACKLIGHT     | 0x0006 |
| MATES_CMD_CLR_PRINT_AREA    | 0x0007 |
| MATES_CMD_SET_PRINT_COLOR   | 0x0008 |
| MATES_CMD_SYSTEM_RESET      | 0x0009 |
| MATES_CMD_PIN_MODE          | 0x000A |
| MATES_CMD_DIGITAL_WRITE     | 0x000B |
| MATES_CMD_DIGITAL_READ      | 0x000C |
| MATES_CMD_BTN_EVENT_COUNT   | 0x000D |
| MATES_CMD_NEXT_BTN_EVENT    | 0x000E |
| MATES_CMD_SWP_EVENT_COUNT   | 0x000F |
| MATES_CMD_NEXT_SWP_EVENT    | 0x0010 |
| MATES_CMD_UPDATE_TEXT_AREA  | 0xFFFF |
| MATES_CMD_APPEND_PRINT_AREA | 0xFFFE |
| MATES_CMD_SET_WIDGET_32VAL  | 0xFFFC |
| MATES_CMD_APPEND_SCOPE_DATA | 0xFFFB |
| MATES_CMD_UPDATE_DOT_MATRIX | 0xFFFA |


## Swipe Event Constants

The table below lists the possible swipe flags that can be used for swipe handling.

| Event             | Value  | Check if swipe is             | Usage                                              |
|:-----------------:|:------:| ----------------------------- | -------------------------------------------------- |
| MATES_SWIPE_NORTH | 0b0001 | From bottom to top            | `(event & MATES_SWIPE_NORTH) == MATES_SWIPE_NORTH` |
| MATES_SWIPE_SOUTH | 0b0010 | From top to bottom            | `(event & MATES_SWIPE_SOUTH) == MATES_SWIPE_SOUTH` |
| MATES_SWIPE_EAST  | 0b0100 | From left to right            | `(event & MATES_SWIPE_EAST) == MATES_SWIPE_EAST`   |
| MATES_SWIPE_WEST  | 0b1000 | From right to left            | `(event & MATES_SWIPE_WEST) == MATES_SWIPE_WEST`   |
| MATES_SWIPE_VERT  | 0b0011 | only done vertically          | `(event & MATES_SWIPE_VERT) != 0`                  |
| MATES_SWIPE_HORZ  | 0b1100 | only done horizontally        | `(event & MATES_SWIPE_HORZ) != 0`                  |
| MATES_SWIPE_TLBR  | 0b0110 | From top left to bottom right | `(event & MATES_SWIPE_TLBR) == MATES_SWIPE_TLBR`   |
| MATES_SWIPE_TRBL  | 0b1010 | From top right to bottom left | `(event & MATES_SWIPE_TRBL) == MATES_SWIPE_TRBL`   |
| MATES_SWIPE_BLTR  | 0b0101 | From bottom left to top right | `(event & MATES_SWIPE_BLTR) == MATES_SWIPE_BLTR`   |
| MATES_SWIPE_BRTL  | 0b1001 | From bottom right to top left | `(event & MATES_SWIPE_BRTL) == MATES_SWIPE_BRTL`   |