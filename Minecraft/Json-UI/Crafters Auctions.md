# Crafters Auctions
#tags
Date: 09-03-2022

The crafters auctions UI is a custom ui designed by CraftersMC. It looks something similar to
![[Pasted image 20220903221242.png]]

**External Links:**

## Possible Improvements
I believe that a lot of the json-ui crafters uses can be ommited as they manually create each component. What can instead be done is creating a component that inherts from the default one their trying to override after which they can then change the specific piece they want to change and not have extra json-ui laying around. This will save quite a bit of resource pack data.

## Background
The craftes team designs custom backgrounds for each UI. An example of a backgroudn will be listed showed at the end of this section.

how they do this is by creating a "bg_image" control within their large chest panel

Below is an example json of how the background was done. I've removed most of everything and just left the background. They replace bg image thats usually within "common_panel@common"
### Json
```json
{
"large_chest_panel": {
        "type": "panel",
        "controls": [
            {
                "root_panel_auction@common.root_panel": {
                    "$ctitle": "$container_title",
                    "visible": "(not (($ctitle - '§n§a') = $ctitle))",
                    "size": [
                        224,
                        220
                    ],
                    "layer": 1,
                    "controls": [
                        {
                            "crafters_auction_panel": {
                                "controls": [
                                    {
                                        "bg_image": {
                                            "type": "image",
                                            "texture": "textures/ui/crafters_auctions",
                                            "layer": 1
                                        }
                                    },
                                ]
                            }
                        },
                    ]
                }
            }
        ]
    }
}
```
### Image / Examples
![[Pasted image 20220903221502.png]]
## Offset and Layout
To creat ethe offset and layout the created their own large_chest_panel_top_half. Here instead of letting the individual ui slots get generated manually with even spacing, they used 'collection_index' alongside some padding to indivdually move every single slot to where they want them to be.

### Json
```json
{
	"crafters_auction_large_chest_panel_top_half": {
    "type": "panel",
    "size": [
        "100%",
        132
    ],
    "offset": [
        0,
        11
    ],
    "anchor_to": "top_left",
    "anchor_from": "top_left",
    "controls": [
        {
            "chest_label@chest.chest_label": {
                "offset": [
                    31,
                    -5
                ]
            }
        },
        {
            "categories": {
                "type": "stack_panel",
                "size": [
                    162,
                    18
                ],
                "orientation": "horizontal",
                "anchor_from": "top_left",
                "anchor_to": "top_left",
                "collection_name": "container_items",
                "offset": [
                    31,
                    10
                ],
                "controls": [
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                10,
                                18
                            ]
                        }
                    },
                    {
                        "0@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 0,
                            "$noHover": true
                        }
                    },
                    {
                        "1@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 1,
                            "$noHover": true
                        }
                    },
                    {
                        "2@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 2,
                            "$noHover": true
                        }
                    },
                    {
                        "3@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 3,
                            "$noHover": true
                        }
                    },
                    {
                        "4@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 4,
                            "$noHover": true
                        }
                    },
                    {
                        "5@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 5,
                            "$noHover": true
                        }
                    },
                    {
                        "6@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 6,
                            "$noHover": true
                        }
                    },
                    {
                        "7@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 7,
                            "$noHover": true
                        }
                    }
                ]
            }
        },
        {
            "items1": {
                "type": "stack_panel",
                "size": [
                    162,
                    18
                ],
                "orientation": "horizontal",
                "anchor_from": "top_left",
                "anchor_to": "top_left",
                "collection_name": "container_items",
                "offset": [
                    31,
                    36
                ],
                "controls": [
                    {
                        "0@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 8
                        }
                    },
                    {
                        "1@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 9
                        }
                    },
                    {
                        "2@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 10
                        }
                    },
                    {
                        "3@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 11
                        }
                    },
                    {
                        "4@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 12
                        }
                    },
                    {
                        "5@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 13
                        }
                    },
                    {
                        "6@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 14
                        }
                    },
                    {
                        "7@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 15
                        }
                    },
                    {
                        "8@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 16
                        }
                    }
                ]
            }
        },
        {
            "items2": {
                "type": "stack_panel",
                "size": [
                    162,
                    18
                ],
                "orientation": "horizontal",
                "anchor_from": "top_left",
                "anchor_to": "top_left",
                "collection_name": "container_items",
                "offset": [
                    31,
                    54
                ],
                "controls": [
                    {
                        "0@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 17
                        }
                    },
                    {
                        "1@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 18
                        }
                    },
                    {
                        "2@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 19
                        }
                    },
                    {
                        "3@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 20
                        }
                    },
                    {
                        "4@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 21
                        }
                    },
                    {
                        "5@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 22
                        }
                    },
                    {
                        "6@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 23
                        }
                    },
                    {
                        "7@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 24
                        }
                    },
                    {
                        "8@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 25
                        }
                    }
                ]
            }
        },
        {
            "items3": {
                "type": "stack_panel",
                "size": [
                    162,
                    18
                ],
                "orientation": "horizontal",
                "anchor_from": "top_left",
                "anchor_to": "top_left",
                "collection_name": "container_items",
                "offset": [
                    31,
                    72
                ],
                "controls": [
                    {
                        "0@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 26
                        }
                    },
                    {
                        "1@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 27
                        }
                    },
                    {
                        "2@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 28
                        }
                    },
                    {
                        "3@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 29
                        }
                    },
                    {
                        "4@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 30
                        }
                    },
                    {
                        "5@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 31
                        }
                    },
                    {
                        "6@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 32
                        }
                    },
                    {
                        "7@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 33
                        }
                    },
                    {
                        "8@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 34
                        }
                    }
                ]
            }
        },
        {
            "control_items": {
                "type": "stack_panel",
                "size": [
                    162,
                    18
                ],
                "orientation": "horizontal",
                "anchor_from": "top_left",
                "anchor_to": "top_left",
                "collection_name": "container_items",
                "offset": [
                    31,
                    98
                ],
                "controls": [
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                18,
                                18
                            ]
                        }
                    },
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                2,
                                18
                            ]
                        }
                    },
                    {
                        "1@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 35
                        }
                    },
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                8,
                                18
                            ]
                        }
                    },
                    {
                        "2@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 36
                        }
                    },
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                8,
                                18
                            ]
                        }
                    },
                    {
                        "3@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 37
                        }
                    },
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                8,
                                18
                            ]
                        }
                    },
                    {
                        "4@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 38
                        }
                    },
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                8,
                                18
                            ]
                        }
                    },
                    {
                        "5@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 39
                        }
                    }
                ]
            }
        },
        {
            "page_controls": {
                "type": "stack_panel",
                "size": [
                    162,
                    18
                ],
                "orientation": "horizontal",
                "anchor_from": "top_left",
                "anchor_to": "top_left",
                "collection_name": "container_items",
                "offset": [
                    6,
                    54
                ],
                "controls": [
                    {
                        "0@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 40
                        }
                    },
                    {
                        "padding@common.empty_panel": {
                            "size": [
                                176,
                                18
                            ]
                        }
                    },
                    {
                        "1@chest.crafters_chest_grid_item": {
                            "anchor_from": "top_left",
                            "anchor_to": "top_left",
                            "collection_index": 41
                        }
                    }
                ]
            }
        }
    ]
}
```