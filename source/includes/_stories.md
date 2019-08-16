# Typical App/Device Stories

Our API and the way you interact with it can be generally boiled down into 2 use cases:

1. You want to trigger the re-ordering of a specific item

2. You want to alter the inventory level of a specific item that you are tracking the use of, relying on a low level trigger point that the user sets to re-order the specific item.

Below, we have explained how each use-case would interact with the API.

## 1. Re-ordering A Specific Item

>For an app or device where the user can login through the Pantri ID server:

```shell
# POST from a user
curl "https://api.pantri.net/???"
  -H "Device_Key: device_id"
  -H "Instruction_Ref: 679866150"

#POST from a app
curl "https://api.pantri.net/???"
  -H "User_Auth: user_token_from_id_server"
  -H "Instruction_Ref: 147478858"
```

>Returns the following:

```json

[
  // Success
  {
    "CommandRef" : 739546323,
    "ID": 201,
    "Status" : "Done"
  }
  // Error
  {
    "CommandRef" : 816844099,
    "ID": 400,
    "Status" : "Didn't do - reason"
  }
]
```

This is the simplest use-case.  The device or app simply needs to place an order on demand.  Here are some example use-cases:

- An IoT button, where a press needs to action the re-ordering of an item.

- A detergent doser in a dishwasher or washing machine that has a low level sensor which when triggered needs to re-order a pre-defined item.

The application or device needs to perform a simple action to complete this process:

### Setup

During the setup of the instruction between device or application with the pantri user account, the **quantity to re-order of a specific product from a specific retailer** is defined.

![NOT LOADED - Fig. 1](Fig1.png)

Once paired, the device or app can call the API to trigger the function.

[See another section to learn how to set up these device/app order triggers.](#)

### Post Setup Trigger

Each time the device or app wants to place an order, the following flow takes place:

![NOT LOADED - Fig. 2](Fig2.png)

##2. Altering The Inventory Level Of A Specific Item

Adding more complexity - we often use items incrementally.  Lots of these items need to be re-ordered before we completely run out.  Some example use-cases:

- A storage jar that can read the stored quantity for the item that it stores.  The user defines at what level they want the item to be re-ordered.

- A dishwasher that runs a cycle, each time using a dishwasher tablet and therefore removing it from a known quantity of inventory.  Again, the user defines at what level they want the system to re-order a pre-defined item.

If you're like us, you like the occasional cookie.  You don't eat the whole pack in one go (or at least not that often)!  So, if you are using a smart cookie jar, you want it to keep track of how many cookies you have left.  Re-ordering some more when you drop down to the last 5... or maybe you need to place that order when theres 10 left!

### Setup

Setting up inventory tracking is similar to [re-ordering a specific item](?shell#1-re-ordering-a-specific-item) above.

![NOT LOADED - Fig. 3](Fig3.png)

![NOT LOADED - Fig. 4](Fig4.png)
