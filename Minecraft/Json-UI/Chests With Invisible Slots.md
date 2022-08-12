# Chests With Invisible Slots
#tags
Date: 08-11-2022

Chests with invisible slots allow for dynamic and changing chest UI's to easily be created. One that looks like this especially.
![[Pasted image 20220811204114.png]]

**External Links:**

## Uninteractable UI
The trick here is to set the UI to be inviisble when a specific item is in the slot to make it server customizable. This is done within the *container_item* component in *ui_common.json*.


```json
{
	"container_item": {
	  "bindings": [
        {
          "binding_name": "#item_id_aux",
          "binding_type": "collection",
          "binding_collection_name": "$item_collection_name",
          "binding_condition": "none"
        },
        {
          "binding_type": "view",
          "source_property_name": "(not (#item_id_aux = 164102144))",
          "target_property_name": "#visible"
        }
      ]
	}
}
```
This sets that specific item slot to be inviisble if that item at that location does not have 
*# item_id_aux = 164102144* The server can then set any item within a slot to be that associated item and it will not be interactable

## Interactable UI With No Background
To create an interactable item slot with no background, you can condtionall render it with multiple *# item_id_aux =* statements and condtionally render a specific type of item within the **controls** field of **container_item**. After which if it is one of those items, you render it so that it has no background by removing 
```json
{  
  "$background_image_control_name@$background_images": {  
    "layer": 1  
  }  
}
```
from that specific component / item_cell.

## Example
```json
{
  "namespace": "common",
  "crafters_container_item": {
    "type": "panel",
    "size": [
      18,
      18
    ],
    "controls": [
      {
        "item": {
          "type": "input_panel",
          "size": [
            18,
            18
          ],
          "layer": 1,
          "$cell_image_size|default": [
            18,
            18
          ],
          "$cell_overlay_ref|default": "common.cell_overlay",
          "$button_ref|default": "common.container_slot_button_prototype",
          "$stack_count_required|default": true,
          "$durability_bar_required|default": true,
          "$item_renderer|default": "common.item_renderer",
          "$item_renderer_panel_size|default": [
            18,
            18
          ],
          "$item_renderer_size|default": [
            16,
            16
          ],
          "$item_renderer_offset|default": [
            0,
            0
          ],
          "$background_images|default": "common.cell_image",
          "$background_image_control_name|default": "bg",
          "$focus_id|default": "",
          "$focus_override_down|default": "",
          "$focus_override_up|default": "",
          "$focus_override_left|default": "",
          "$focus_override_right|default": "",
          "focus_identifier": "$focus_id",
          "focus_change_down": "$focus_override_down",
          "focus_change_up": "$focus_override_up",
          "focus_change_left": "$focus_override_left",
          "focus_change_right": "$focus_override_right",
          "focus_enabled": true,
          "focus_wrap_enabled": false,
          "focus_magnet_enabled": true,
          "bindings": [
            {
              "binding_name": "#item_id_aux",
              "binding_type": "collection",
              "binding_collection_name": "$item_collection_name",
              "binding_condition": "none"
            },
            {
              "binding_type": "view",
              "source_property_name": "(not (#item_id_aux = 164102144))",
              "target_property_name": "#visible"
            }
          ],
          "controls": [
            {
              "item_cell_only_image": {
                "type": "panel",
                "size": "$cell_image_size",
                "layer": 0,
                "bindings": [
                  {
                    "binding_name": "#item_id_aux",
                    "binding_type": "collection",
                    "binding_collection_name": "$item_collection_name",
                    "binding_condition": "none"
                  },
                  {
                    "binding_type": "view",
                    "source_property_name": "(#item_id_aux = 164102144 or #item_id_aux = 164167680 or #item_id_aux = 164233216 or #item_id_aux = 164298752 or #item_id_aux = 164364288 or #item_id_aux = 164429824 or #item_id_aux = 164495360 or #item_id_aux = 164560896 or #item_id_aux = 164626432 or #item_id_aux = 164757504 or #item_id_aux = 164888576 or #item_id_aux = 164954112 or #item_id_aux = 165019648 or #item_id_aux = 165216256 or #item_id_aux = 165412864)",
                    "target_property_name": "#visible"
                  }
                ],
                "controls": [
                  {
                    "item": {
                      "type": "panel",
                      "size": "$item_renderer_panel_size",
                      "layer": 0,
                      "controls": [
                        {
                          "stack_count_label@common.stack_count_label": {
                            "layer": 9
                          }
                        },
                        {
                          "$item_renderer@$item_renderer": {
                            "size": "$item_renderer_size",
                            "offset": "$item_renderer_offset",
                            "anchor_to": "center",
                            "anchor_from": "center",
                            "layer": 7
                          }
                        }
                      ]
                    }
                  }
                ]
              }
            },
            {
              "item_cell": {
                "type": "panel",
                "size": "$cell_image_size",
                "layer": 0,
                "bindings": [
                  {
                    "binding_name": "#item_id_aux",
                    "binding_type": "collection",
                    "binding_collection_name": "$item_collection_name",
                    "binding_condition": "none"
                  },
                  {
                    "binding_type": "view",
                    "source_property_name": "(not (#item_id_aux = 164102144 or #item_id_aux = 164167680 or #item_id_aux = 164233216 or #item_id_aux = 164298752 or #item_id_aux = 164364288 or #item_id_aux = 164429824 or #item_id_aux = 164495360 or #item_id_aux = 164560896 or #item_id_aux = 164626432 or #item_id_aux = 164757504 or #item_id_aux = 164888576 or #item_id_aux = 164954112 or #item_id_aux = 165019648 or #item_id_aux = 165216256 or #item_id_aux = 165412864))",
                    "target_property_name": "#visible"
                  }
                ],
                "controls": [
                  {
                    "$background_image_control_name@$background_images": {
                      "layer": 1
                    }
                  },
                  {
                    "item": {
                      "type": "panel",
                      "size": "$item_renderer_panel_size",
                      "layer": 0,
                      "controls": [
                        {
                          "stack_count_label@common.stack_count_label": {
                            "layer": 9
                          }
                        },
                        {
                          "$item_renderer@$item_renderer": {
                            "size": "$item_renderer_size",
                            "offset": "$item_renderer_offset",
                            "anchor_to": "center",
                            "anchor_from": "center",
                            "layer": 7
                          }
                        }
                      ]
                    }
                  },
                  {
                    "durability_bar@common.durability_bar": {
                      "layer": 8
                    }
                  }
                ]
              }
            },
            {
              "item_cell_overlay_ref@$cell_overlay_ref": {
                "layer": 3
              }
            },
            {
              "item_selected_image@common.slot_selected": {
                "layer": 4
              }
            },
            {
              "item_button_ref@$button_ref": {
                "tts_ignore_count": true,
                "tts_skip_message": true,
                "tts_inherit_siblings": true,
                "layer": 5
              }
            },
            {
              "container_item_lock_overlay@common.container_item_lock_overlay": {
                "size": "$item_renderer_size",
                "offset": [
                  1,
                  1
                ],
                "anchor_to": "top_left",
                "anchor_from": "top_left",
                "layer": 6
              }
            },
            {
              "item_lock_cell_image@common.item_lock_cell_image": {
                "layer": 2
              }
            },
            {
              "item_container_transfer_mode_overlay@common.item_container_transfer_mode_overlay": {
                "size": "$item_renderer_size",
                "offset": [
                  1,
                  1
                ],
                "anchor_to": "top_left",
                "anchor_from": "top_left",
                "layer": 10
              }
            }
          ]
        }
      }
    ]
  }
}