# sfdc-superbadge-advanced-apex-specialist
Step 1

make sure you create the Custom metadata records with the exact same names given (that matches the product families)
in the constants apex class, declare all the properties as public static


Step 2

OrderTrigger needs to handle only after update event
OrderTrigger should use the Orderhelper internally for the rollup
Don’t forget to remove the “with sharing” from the orderHelper class



Step 3

Override the Add and New button under Product object to use the visualforce page
Product2New visualforce page
in the pageblock table columns, use the field labels as headers using $ObjectType
update the column values to use the productRecord fields inside the productwrapper
use apex:chart to display the horizantal bar chart in a separate pageblock above the table
reRender the required components from the Save and Add buttons
Product2Extension apex class
Make the Controller class “Without Sharing”
add the inner class ProductWrapper
replace the list of products with list of productwrapper
use Savepoint in the Save method
iterate thru the productWrapper and extract the products and pricebookentries and insert them separately
use try catch block and do a rollback if there are any errors
ChartHelper apex class
Make the ContChartHelperroller class “Without Sharing“
move the chart data initialisation logic to Chart Helper class
make the GetInventory method @AuraEnabled


Step 4

This is probably the simplest of all the steps.. update theTestDataFactory class to handle the key requirements given..

Make sure all the methods in the TestDataFactory class are Public Static and the class is marked “with sharing”
all the construct methods should create the mentioned objects with the required fields and unique names and return the records without inserting them
use the Insert method to call all the construct methods and then insert the records returned from those methods.



Step 5

Update the VerifyQuantityOrdered method in TestDataFactory with a System.Assert to compare the Quantity Ordered between the Updated product and the original product plus the incoming quantity
run both OrderTests and Product2Extension_UnitTest and make sure both the test classes are passing  and the classes they are intended to cover has more than 75% coverage



Step 6

Don’t forget to create the chatter group “Inventory Announcements” .. mark it public and tick the disable auto archive checkbox and use the description text given
update the product trigger to handle only after update and use the product helper class to handle the after update logic
update the product helper class AfterUpdate method to use the postAlerts method which in turn will be using the AnnouncementQueueable class to process the chatter group notification
AnnouncementQueueable is a Queueable class and uses ConnectApi to post the announcement




Step 7

Override the New and Edit buttons under the Order object to use the OrderEdit visualforce page





Step 8

 

This was my last superbadge and by completing this Advanced Apex Specialist Superbadge , I’m now eligible for Platform Developer II certificate provided I clear the multiple choice exam..  🙂

Good luck to you all if you are working on this superbadge or preparing for the Salesforce Platform Developer II certification.

 
