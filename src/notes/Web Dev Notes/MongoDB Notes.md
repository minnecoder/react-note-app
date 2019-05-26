Start MongoDB (in Ubuntu) - `sudo service mongod start`

**<u>MongoDB Installation Instructions</u>**

1. Download the installer from mongodb.com (Community Server)
2. Run the installer
3. Select the Custom option
4. Change the installation directory to `c:\mongodb` (need to create the folder)
5. Use the default options for the rest of the installer - Don't need to install MongoDB Compass
6. After installation is complete -create 3 new folders (`data`, `log`, and `db` inside of `data`) 
7. Open a command prompt as Admin
8. Navigate to the bin folder of `mongodb` (`c:\mongodb\bin`)
9. Type in the command `mongod --directoryperdb --dbpath C:\mongodb\data\db --logpath c:\mongodb\log\mongo.log --logappend --install`

 

Type `net start MongoDB` to start MongoDB service

Type `mongo` while in the `c:\mongodb\bin` folder 

 

**<u>MongoDB commands</u>**

`show dbs` - shows all of the databases

`use <db name>` - creates a database with the given name and switches that database

`db` - tells you what database you are currently in



`mongod --directoryperdb --dbpath C:\mongodb\data\db`



**<u>Installing and setting up Mongo DB</u>** 

1. Download the installer
2. Inside of the installer (or before) create a new folder on the C drive that is labeled mongodb
3. Install Mongo DB
4. After the installer has finished go to the mongodb folder
5. Create the folders data, data\db, and  log
6. Go to mongodb\bin
7. Type the command `mongod --directoryperdb --dbpath C:\mongodb\data\db --logpath c:\mongodb\log\mongo.log --logappend --install`
8. Type `net start mongodb` to start mongodb (which will be running in the background)
9. Type `mongo` to start the mongodb shell

`show dbs` - shows all of the databases

`use <database name>` - will switch to the database or create it and switch to it if not created

`db` - shows the current database

`db.createCollection <collection name>;` - to create a collection (same as table in SQL)

`show collections` - shows all of the collections

`db.<collection name>.insert({<key value pairs in JSON format>});` - add item to collection

`db.<collection name>.find();` - displays all of the items in the given collection

`db.dropDatabase()` while in the database that you want to delete will delete the database