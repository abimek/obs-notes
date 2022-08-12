# Dynamic Forms
#minecraft #json-ui
Date: 08-11-2022

Dynamic Forms are forms that have there behavior still correlated with server side buttons but where each individual button can be manipulated.

**External Links:**
[Json-UI Docs](https://wiki.bedrock.dev/json-ui/json-ui-documentation.html#grid)


```ad-info
the control in ```long_form_scrolling_content/wrapping_panel``` needs to be changed from anything that isn't the default one as the game still thinks its a factory even after your remove the factory within the default one.
```json
"long_form_scrolling_content/wrapping_panel": {
	"controls": [
      {
        "buttons@server_form.long_form_dynamic_buttons": {}
      }
    ]
}
```

## Examples
### Grid Implementation
```json

"long_form_dynamic_buttons": {  
  "type": "grid",  
  "size": ["100% - 4px", "100%c"],  
  "offset": [2,0],  
  "grid_dimensions": [3, 4],  
  "anchor_from": "top_middle",  
  "anchor_to": "top_middle",  
  "collection_name": "form_buttons",  
   "controls": [
      {
        "b0@server_form.dynamic_button_small": {
          "grid_position": [0, 0]
        }
      },
      {
        "b1@server_form.dynamic_button_small": {
          "grid_position": [1, 0]
        }
      },
      {
        "b2@server_form.dynamic_button_small": {
          "grid_position": [2, 0]
        }
      },
      {
        "b3@server_form.dynamic_button_small": {
          "grid_position": [0, 1]
        }
      },
      {
        "b4@server_form.dynamic_button_small": {
          "grid_position": [1, 1]
        }
      },
      {
        "b5@server_form.dynamic_button_small": {
          "grid_position": [2, 1]
        }
      },
      {
        "b6@server_form.dynamic_button_small": {
          "grid_position": [0, 2]
        }
      },
      {
        "b7@server_form.dynamic_button_small": {
          "grid_position": [1, 2]
        }
      },
      {
        "b8@server_form.dynamic_button_small": {
          "grid_position": [2, 2]
        }
      },
      {
        "b9@server_form.dynamic_button": {
          "grid_position": [0, 3]
        }
      }
    ]
  }, 
  
"dynamic_button_small@server_form.dynamic_button": {  
  "size": ["33.3333%", 32]  
},
```
### Manually Adding Buttons Instead of Using Factory
```json
{
  "long_form_scrolling_content/wrapping_panel": {
    "controls": [
      {
        "buttons@server_form.long_form_dynamic_buttons": {}
      }
    ]
  },

  "long_form_dynamic_buttons": {
    "type": "stack_panel",
    "size": ["100% - 4px", "100%c"],
    "offset": [2,0],
    "orientation": "vertical",
    "anchor_from": "top_middle",
    "anchor_to": "top_middle",
    "collection_name": "form_buttons",
    "controls": [
      {
        "bb@server_form.better_button": {
          "collection_index": 0
        }
      },
      {
        "bbb@server_form.better_button": {
          "collection_index": 1
        }
      }
    ]
  },

  "better_button": {
    "type": "stack_panel",
    "size": ["100%", 32],
    "orientation": "horizontal",
    "controls":[
      {
        "form_button@common_buttons.light_text_button": {
          "$pressed_button_name": "button.form_button_click",
          "anchor_from": "top_left",
          "anchor_to": "top_left",
          "size": [ "100%", 32 ],
          "$button_text": "#form_button_text",
          "$button_text_binding_type": "collection",
          "$button_text_grid_collection_name": "form_buttons",
          "$button_text_max_size": [ "100%", 20 ],
          "bindings": [
            {
              "binding_type": "collection_details",
              "binding_collection_name": "form_buttons"
            }
          ]
        }
      }
    ]
  }
}
```

## Collections
Collections are hard coded types that gain data from the client itself. This includes form buttons and there properties as well as Items for normal inventories.  

**collection_name**:
>  A property that holds the identifier for the collections. For forms the collection_name is **form_buttons**. This property goes within the component holding all the buttons.

**collection_index**:
> Collection index is used when manually creating buttons so that said button is associated with the proper data from the client. This tells the button which button it is exactly! This goes within a button and holds a numeric value. The indexing starts at 0.

**binding_collection_name**:
> Binding Collection Name can go into the bindings of a button to specify where the data for that button is coming from. This would also be **form_buttons** for forms.

**collection_details**:
> I have absolutely 0 clue on how this works, I believe it holds data for each specific buttion once an index has been set but that is a pure guess.

*example*
```json
"bindings": [  
  {    "binding_type": "collection_details",  
    "binding_collection_name": "form_buttons"  
  }  
]
```



## Variables/Bindings
Once a form button has been properly binded these bindings can be accessed
**#form_button_text**: Text on that specific button.
**#form_button_texture**: Texture for the form button (not completely sure how its binded)