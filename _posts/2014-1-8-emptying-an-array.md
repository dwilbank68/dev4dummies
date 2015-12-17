---
title:  "How To Wipe An Array Clean"
date:   2014-1-8 12:26:20 -0800
categories: ruby arrays
permalink: emptying-arrays
image: 
comments: true

---
You have

    arr = [2,6,34,7,3,4,5,6,7,4,45]

and now you want to wipe arr so you can start over.

    arr = []

There. It’s clean.

Except it’s a different array now.

The proof:

    arr = [2,6,34,7,3,4,5,6,7,4,45]
    p arr.object_id
    arr = []
    p arr.object_id

The arrays have different object_ids. You just created a new, empty array with the same name.

No sir.

Use arr.clear instead.