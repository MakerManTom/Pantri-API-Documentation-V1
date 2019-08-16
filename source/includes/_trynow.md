# Try It Now

<aside class="notice">This section needs to display a quick demo of the entire API journey in several steps</aside>

##Create An Order

1. CONFIG: Configure an instruction (A JSON file)
2. USER/DEVICE SETUP: Set up the instruction - pairing a device (GUI card)
3. DEVICE ORDER: Submit the instruction via API POST (simulate the device operating via GUI)
4. ORDER PROCESSING: Simulate customer card being billed, Pantri sending order to retailer
5. ORDER FULFILMENT: Simulate order being sent to the customer from the retailer

or

## Track Inventory

1. CONFIG: Configure an instruction (A JSON file)
2. USER/DEVICE SETUP: Set up the instruction - pairing a device with a product - including trigger level (GUI card)
3. CONSUMPTION: Submit the instruction via API POST (simulate the device operating via GUI) - repeat several times
4. LOW LEVEL TRIGGER & ORDER: Simulate Pantri counting down inventory and the order being triggered
4. ORDER PROCESSING: Simulate customer card being billed, Pantri sending order to retailer
5. ORDER FULFILMENT: Simulate order being sent to the customer from the retailer
