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
#### Command to update the DB
```sh
ant updatesystem
```
#### rename + move one file to other file with following data 
```sh
move %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\essentialdata-bands.impex %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\concerttours-bands.impex & move %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\projectdata-yBandTour.impex %HYBRIS_HOME_DIR%\hybris\bin\custom\concerttours\resources\impex\concerttours-yBandTour.impex
```
