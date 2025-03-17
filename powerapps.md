---
title: PowerApps
nav_order: 4
layout: home
---

### Create a new collection
```
ClearCollect(
    col_ProgressBar,
    {
        Id: 1,
        Status: true,
        Label: "Page 1"
    },
    {
        Id: 2,
        Status: false,
        Label: "Page 2"
    },{
        Id: 3,
        Status: false,
        Label: "Page 3"
    }
)
```

### Add a running row number to a collection

```
ClearCollect(
    col_Titles,
    ForAll(
        Sequence(CountRows(col_Titles)) As Seq,
        Patch(
            Last(
                FirstN(
                    col_Titles,
                    Seq.Value
                )
            ),
            {Id: Seq.Value}
        )
    )
)
```
