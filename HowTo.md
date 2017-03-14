# Fuel Reduction Data Workflow

This work flow outlines how to:
  1. Export Google Spreadsheet data to join to the Master Fuel Reduction Database.
  2. Download Project Polygon Data from Cal Topo and add it to the Master Fuel Reduction Database.
  3. Join the Google Spreadsheet and Project Polygon data. 
  4. Export this Updated Data.
  5. Push updates to the Server.
  


Extra how to:
  1. Import project Polygon Data into CalTopo.


####Project Initiation####

Copy over the project folder to your local:

<b>X:\_projects\FuelReductionData</b>  --> This is your workspace. Place all working MXDs and intermitent data here including SHPs, KMLs, or Tables that you may create. The GDB that exists here will be the source for all products we make concerning this data. This is the GDB that you will be making permanent edits to and this is the GDB that must be updated to the server so the most recent data can be shared with others.

###Downloading Google Spreadsheet for joining in Arc###

  1. Export the Fuels Reduction Database from Google Spreadsheets by:
    File > Download As > Comma-separated Values (.csv, current sheet)
  2. Save that file to the project folder:
    Y:\_projects\FuelReductionData\FuelReductionDataWoring\project_data\tables
    DO NOT CHANGE THE FILE NAME
  3. Add the current date to the end of the file name of the previous table that was located at the path above and click and drag the old table to the Archive Folder. 
  

###Downloading Project Polygon Data from Cal Topo and adding to Master GDB###

  1. Navigate to https://caltopo.com/m/JMHF
  2. Hover over the 'Export' option at the top left of the page to activate its options. 
  3. Select 'Download KML File' and save it:
  Y:\_projects\FuelReductionData\FuelReductionDataWoring\project_data\KML\CalTopoExports  --> save the data with today's date.
  4. Use Xtools in Arc to convert the KML into a SHP; save it here:
  Y:\_projects\FuelReductionData\FuelReductionDataWoring\project_data\SHP  --> save the data with today's date.
  5. Start an Edit session on the 'ProjectPolygons' layer; using the edit cursor click to highlight the data in the shapefile you just
  created to be added; right click copy; deselect the data; right click paste; select the 'ProjectPolygons' layer; the only field in the
  attribute table that HAS to be entered is the 'AltID' since that is the field that we are joining this data on; save edits; stop
  editing.

###Joining the Google Spreadsheet data to the Project Polygon data in Master Fuel Reduction GDB###
  
  1. Open the Fuel Reduction Working mxd:
    Y:\_projects\FuelReductionData\projects
    <i>The working MXD that exists here currently is just the one I have already started. If you want to create your own working map, go
    ahead and do so. Feel free to save it here. </i>
  2. Since we kept the integrity of the table name that we downloaded from Google Spreadsheet, the path to the previous join is still
  intact with the data. If the link to the table appears to be broken, repair the data source, and re-create the join. The
  ProjectPolygon data and the exported Google Spread sheet doc are joined on the <u>Alt-ID</u> field. 
   
   <b><u> Remember</u>: 
   This join is composed of the table you just downloaded from Google Spreadsheet now located (using the 'Alt-ID' field):
    Y:\_projects\FuelReductionData\FuelReductionDataWoring\project_data\tables\CalMapperDatabase - SLU_ProjectPolygons_Export.csv
    And the 'ProjectPolygons' layer located:
    Y:\_projects\FuelReductionData\FuelReductionDataWoring\project_data\GDB\FuelReductionMaster.gdb\Projects\ProjectPolygons</b>
  
  3. Confirm that the join was successful. Select all records in the Project Polygon layer and export this data to the 'Joined Data'
  Feature Dataset in the project GDB:
  Y:\_projects\FuelReductionData\project_data\GDB\FuelReductionMaster.gdb\JoinedData
  <b> Make sure you date this exported data with today's date. This ensures everyone using the data that it is indeed the most recent
  </b>
 
 
 ^^This Exported data with today's date is your final project^^
  4. FYI: If this data needs to be shared with anyone or submitted create a zip shapefile of this data in the 'Data Sent'
  folder:
  Y:\_projects\FuelReductionData\project_data\Data_Sent
  
###Pushing Edits to Server###
Once you have completed any edits to the Master Fuel reduction GDB it is imperitive that you push your edits to the server. You have not
completed this process until you have pushed you edits to the X://.



###Updating the CartoDB Map###
Give me a shout out if you update the GDB. We will pull the most recent data created and update the Fuel Reduction Map. Also, feel free
to share the link below. If you have any suggestions for improvement with this map please send your ideas my way and we will
incorporate! 


https://slu.carto.com/viz/e14adad6-d1fe-11e6-b215-0e3a376473ab/public_map

Photos can be incorporated into the project 'pop-up'. Upload your photos to the SLUGIS Flickr account to be imported into cartodb.
Create a brand new album for the project photos you are importing so it is easy to tell which photos go to each project. Flickr has an
app available for download on your mobile device that makes this import process easy. Please let me know if you have any questions as to
how to download/logon on to gain access.


https://www.flickr.com/photos/slugis3400/albums

________________________________________________________________________________________________________________________
###Adding Project Polygon to CalTopo###
  We will be pulling the project polygons that are in the CAL TOPO Fuel Reduction Map to add to the ProjecPolygon layer. 
  https://caltopo.com/m/JMHF
  
  1. Select the 'Map is read-only' link on the left side of the caltopo page. Enter in the appropriate password.
  2. Import your project polygon using the Import button at the top left of the screen. Import GPX, KML, or KMZ. 
     Or, add the polygon using the '+Add' feature at the top left of the of the screen. 
  3. Make sure all data is entered in according to the 'CAL TOPO Fuel Reduction Map' email instructions.


________________________________________________________________________________________________________________________

If you have questions as you work through this process, simply create an issue thru GitHub or email me!
