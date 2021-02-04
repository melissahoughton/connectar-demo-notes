# connectar-demo-notes


## Full Working Contoso Web Site

https://a2z6tlhwebapp.azurewebsites.net/

The following steps will guide you through the standalone web application to explore capabilities.

1. **Click** on the **factory** in **South America** and observe twin data.
1. **Click** on the **shipment** in the **Indian Ocean** to observe twin data.
1. **Press** space bar to simulate Microsoft Teams message.
1. **Click** the **Signature Tee** filter to see relevant supply lines.
1. **Click** the **store** in **California.**
1. **Click** the bottom order number **442-12448**.
1. **Click** the **shipment** in the **Atlantic Ocean** and observe historical twin data.
1. **Click** the **factory** in **Pakistan** and observe historical twin data then **View Factory**.
1. **Click** on any sensor in the factory to observe live telemetry. _Note that the green factory line storeroom has high humidity._
1. **Click** the bottom order number **442-12448** from **Latest Orders**.
1. **Click** on the storeroom and then **Time Series Insights**.
1. **Click** on **Change Y-Axis Type** to observe the historical high humidity of line 2.
1. **Click** on **VIEW IMPACT** to show the impact assessment of shutting line 2 down.
1. **Click** the **store** in **California** to analyze financial impact.
1. **Click** the factory in Pakistan and then **STOP LINE**.
1. Observe alternative supply lines fulfilling orders.

## Diagram

https://raw.githubusercontent.com/Azure-Samples/IoTDemos/master/ADT-SupplyChainDemo/images/arch.png

## Code / Functions

1. Function to receive updates from Iot devices via the event grid and then updates either the twin - we will take a look at that one in a second.

2. Function to SingleR to broadcast the stream as telemetry

3. Pushes data from the Event Hub to Time Series Inight

## Show them the code for the IoT To TWIN

- In VS Ctrl+G 91
- Talk about Az DT Client
- Show all the api calls available
- Can automate everything using this SDK
- OR connnect via a CLI to update

## Open ADT Explorer

Open up explorer to show what it looks like, explain the properties, what you can do
http://localhost:3000/

### Queries:

- Run the query `SELECT * FROM DIGITALTWINS` to view all supply chain artifacts.
- Run the query `SELECT * FROM DIGITALTWINS WHERE IS_OF_MODEL('dtmi:demo:adtga:warehouse;1')` to see all twins of type Warehouse.
- Run the query `SELECT * FROM DIGITALTWINS WHERE IS_DEFINED(Location)` to get all twins that have the Location prpoerty.

### Add new twin:

1. Click on factory (red)

2. See the relationships with conveyors

3. Add a new conveyor, see it added to the graph

4. Create a new relationship to the factory

5. See that it is updated

### Updating properties:

Usage Example:

- **Click** on a twin of type shop like "RT4465881".
- In the property explorer, changes the StockLevel value to 100.
- **Click** the **Save** icon in the navigation bar.
- Observe the value has been patched with the replace operation.


### Simulating Data coming in: 
- Start the simulator by running `start` 
- Click on the details for a factory to see the number of orders changing
