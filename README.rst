daybed-tracking
===============

The idea of daybed tracking is dead simple.

You add some point for a specific thing A to a specific ride B.

For instance:

  A: Your mobile phone
  B: Your last race

  A: Your car
  B: Your last trip

  A: Your truck
  B: Delivery ride


The definition
--------------

.. code-block:: json

  {"definition":
    {
      "title": "Daybed Tracking",
      "description": "A list of rides point.",
      "fields": [
        {
		  "label": "Mobile ID",
          "name": "mobile",
          "type": "string",
          "hint": "The mobile id (car, truck, smartphone)"
        },
        {
		  "label": "Ride ID",
          "name": "ride",
          "type": "string",
          "hint": "The ride uniq id (all point for the same ride have got the same id)"
        },
        {
		  "label": "Timestamp",
          "name": "timestamp",
          "type": "datetime",
          "hint": "The date the point was added.",
          "autonow": true
        },
        {
		  "label": "Position",
          "name": "position",
          "type": "point",
          "hint": "The point the mobile was at the given time. (in 3d, 4d or 5d)",
          "gps": true
        }
      ]
    },
    "permissions": { 
      "Authenticated": [
        "create_record", 
        "delete_own_records", 
        "read_own_records", 
        "update_own_records"
      ], 
      "Everyone": [
        "read_definition", 
        "read_permissions"
      ]
    }
  }


The app
-------

The goal of this HTML5 app, is to let you choose a mobile, then
choose a ride and show on a map what happen.

Also a little table can show you the distance, the average speed for
the ride and in between two points.

In case your point contains a z attribute we can also show a graph
with the altitude over the time.
