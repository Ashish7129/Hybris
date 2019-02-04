# Hybris
## Tutorial 1 
### Set up things 
#### Command to open HSQL DB
```sh
cd %HYBRIS_HOME_DIR%\hybris & start /B java -cp .\bin\platform\lib\dbdriver\* org.hsqldb.util.DatabaseManager --url jdbc:hsqldb:file:.\data\hsqldb\mydb
```
#### Command to kill the DB
```sh
taskkill /FI "WINDOWTITLE eq HSQL*" 
```

#### Configure custom DB
By default, Hybris uses HSQL DB and it's configures in global **project.properties** file.
   ##### Custom MySQL DB configuration (define it in local.properties)
```sh
db.url=jdbc:mysql://localhost/<dbname>?useConfigs=maxPerformance&characterEncoding=utf8
db.driver=com.mysql.jdbc.Driver
db.username=<username>
db.password=<password>
db.tableprefix=
```

#### Command to run/stop Hybris server
```sh
hybrisserver.bat start/stop
(or)
ctrl + C to stop server
```
#### Command to create recipe
```sh
inside installer,
install.bat -r [recipe_name] setup
install.bat -r [recipe_name] initialize
install.bat -r [recipe_name] start
```
#### command to create MODULE
```sh
ant modulegen -Dinput.module=accelerator -Dinput.name=training -Dinput.package=com.hybris.training -Dinput.template=develop
```
##### Description
 - **Module** : it specifies module-template (eg accelerator, b2baccelerator etc). we have specified module as accelerator which means we are developing B2C module. 
 - **name** : we can specify any name to the module, we have given training for the same.
 - **package** : We can also specify the java class package prefix, we have given as com.hybris.training.
 - **template** : Template specifies whether configuration is for development or production.
 
#### command to create EXTENSION
```sh
ant extgen
```
While running this command, specify the extension template,name of the extension and package name. <br />
**Extension template** : any of the existing extension templates (eg yempty, yaddon etc)

#### how to make custom extenstion as extension template
```sh
meta key="extgen-template-extension" value="true"
```
define it in its **extensioninfo.xml**

#### Command to update the DB
```sh
ant updatesystem
```
#### rename + move one file to other file with following data 
```sh
move %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\essentialdata-bands.impex %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\concerttours-bands.impex & move %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\projectdata-yBandTour.impex %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\concerttours-yBandTour.impex
```

#### command to create AddOns
inside platform folder,
```sh
ant extgen -Dinput.template=yaddon -Dinput.name=myaddon -Dinput.package=com.myapp
```
Now, add your Addon (myaddon) to localextensions.info
```sh
<extension name="myaddon" />
```
Then, ```sh ant clean all ```
