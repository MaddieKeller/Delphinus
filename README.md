# Delphinus
Access Database Work Order and Inventory Management System

This is an access database I built back in 2012 using mainly VBA and a small amount of SQL. It has two main functions - to keep track of inventory by lot numbers and to track work orders.

The INVENTORY side is done by lot number. Goods are recorded by the shipping/receiving dock as they come in and are assigned a lot. Lots are recorded by genus, species, and form (ex. Genus salmon, species sockeye, form H&G), and by weights including pallet/bag weight, glaze weight, and fish weight. Lots can then be immediatly shipped out or processed via the work order side.

The WORK ORDER side is done by assigned work order numbers. Multiple lots can be processed by a single work order, and the finished product can be output to multiple lots. 

Fish can be tracked through the system in two ways - via lot number or via work order number. There are a variety of built in reports to view history of lots and work orders from start to finish. A seperate report can calculate current inventory by outputing a report of only lots that have weight remaining.

#MENU BREAKDOWN

Users will first have to log on in order to access the database. Changes to the database are tracked by user login ID, and any change can be tracked back to the user id that created it via the Audit Log table.

Receiving Log Menu - Used by the dock to process incoming receipts of product and assigning it a lot number.
Work Order Menu - Used by the cutting floor manager to keep track of work orders and create new work orders.
Shipping Log Menu - Used by the dock to process outgoing shipments of product.
Inventory Reports and Lot History - Used by the office to view various reports on in process work orders, inventory, and shipments.
Product List and New Product Setup - Maintenance area for adding new products, new vendors, new users, ect.
Queries and Reports - Ad-hoc reports and queries are added here as needed.
Quit Delphinus - closes the program

#RECEIVING LOG MENU
Entry Form - This is used to initially receive inventory into the system and assign it to a lot number. Regulations require ANY incoming product be logged, not just fish, so this allows receipt of non-seafood inventory. Non-seafood inventory is not tracked and not assigned a lot number.

Spreadsheet - A List of ALL receipts done with the entry form.

Edit BOL Detail - Used to change a detail done on the entry form if a mistake is made. Only certain users can access this.

View BOL Detail(read only) - Allows users a read only view of any receipt done with the entry form via a drop down.

#WORK ORDER MENU
Add New Work Order - Adds a new work order to the system. User puts in order details and products ordered at this stage.

Pick Lot by Work Order - Work Order Step 2: Inventory Lots that are to be processed are picked here. Users can pull in the entire lot or only a portion of it, as needed. Multiple lots can be pulled out of inventory and added to a work order. Once a lot is added to a work order it no longer shows up in inventory. Only open work orders can be edited or changed on this sheet.

Relot Post Process - Work Order Step 3: Finished work order goods are added back to inventory and assigned lot numbers here. Work orders can also be closed here via a checkbox. Finished goods can be added to inventory without closing the work order, although you are encouraged to close work orders once you have a processed the finished goods and not leave the work order open.

Edit Information - Can be used to reopen a closed work order or to edit a still open work order's details.

View History - a Read Only view of a completed work order.

#SHIPPING LOG MENU
Create New BOL Out and Assign Lots - Product Shipped out of the warehouse is processed via this form. The BOL number is generated from an outside system and put into this form. Lots to be shipped are picked here. Both processed and unprocessed lots can be shipped.

Spreadsheet - A list of all shipments by date, minimal detail

View Shipped BOL Detail - A detailed list of a finished shipment, picked via dropdown menu.

#INVENTORY REPORTS AND LOT HISTORY MENU
Lots with Problems - Shows a list of all lots with a negative inventory. A button on this page will take you to the Lot History of the clicked lot.

Current Inventory Report - Shows a list of all lots with weight remaining as of the current day. A button on this page will take you to the Lot History of the clicked lot.

Inventory As Of Report - Shows a list of all lots with weight remaining as of the selected day. Used to get a historical inventory number.

Lost History (Read Only) - A Read Only view of any lot's history. Buttons in the history will take you to the entry BOL, the Work Order, or Shipment if clicked.

#PRODUCT LIST AND NEW PRODUCT SETUP
This is a single form, not a menu. Allows you to add a new product to the database. Will not allow you to add a duplicate of an existing product.

