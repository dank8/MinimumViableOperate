## NAME

`Statitical Methods` - Scratch pad of notes (Needs editing).

## DESCRIPTION

### Quartile and Interquartile 

Separate items in a set into Four equal groups. 

1. Statistics uses a method called Quartiles:
   - The intention is separate into groups called: 1st Quatile; 2nd Quatile; 3rd Quatile; 4th Quatile.  
   - This method DOES NOT use the Value. Items are only Ordered Lowest to Highest based on their value.
   - The objective is four groups each containing 25% of the *item count* (each group has same number of items).
   - Each group is identified by the hightest value within that group.
   - The intention is to be able to use the "Value" to describe how each group is different. (Needs editing)
2. Simple Numeric groups
   - The objective is four groups each containing 25% of the *linear range in value* (each group will have different number of items).
   - This is included to allow compare and constrast with the statstical method.


```
┌────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                                                                                            │
│   (by position number)                                                                                     │
│ ┌─────────┬───────────────────────┐                    ────┐                     ───┐                ───┐  │
│ │QUARTILES│                    1st│                     2nd│                    3rd │               4th │  │
│ └─────────┘                       ▼                        ▼                        ▼                   ▼  │                                                                                                       │
│            ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐ ┌──┐  │
│            │1 │ │2 │ │3 │ │4 │ │5 │ │6 │ │7 │ │8 │ │9 │ │10│ │11│ │12│ │13│ │14│ │15│ │16│ │17│ │18│ │19│  │
│    ITEMS   │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│ │--│  │
│            │12│ │14│ │17│ │22│ │26│ │28│ │28│ │29│ │29│ │30│ │30│ │30│ │30│ │30│ │31│ │31│ │31│ │31│ │32│  │
│            └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘ └──┘  │
│ ┌─────────┐            ▲     ▲         ▲                                                                ▲  │ 
│ │ LINEAR  │         1st│  2nd│      3rd│                                                             4th│  │ 
│ └─────────┴────────────┘  ───┘      ───┘                                                            ────┘  │
│   (by Linear Value)                                                                                        │
│                                                                                                            │
│                ┌────────┐                                                                                  │
│                │Position│                                                                                  │
│   ITEM LAYOUT: │   --   │                                                                                  │
│                │  Value │                                                                                  │
│                └────────┘                                                                                  │
│                                                                                                            │
└────────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

NOTE: only 19 items are used for simplicity, as it force each Quartile to have a definitive highest value.