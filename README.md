# Hybris
## Tutorial 1 
### Set up things 
#### Command to open HSQL DB
```sh
cd %HYBRIS_HOME_DIR%\hybris & start /B java -cp .\bin\platform\lib\dbdriver\* org.hsqldb.util.DatabaseManager --url jdbc:hsqldb:file:.\data\hsqldb\mydb
```
#### Command to kill the DB
taskkill /FI "WINDOWTITLE eq HSQL*" 

#### Command to run/stop Hybris server

hybrisserver.bat start/stop
(or)
ctrl + C to stop server

#### Command to create recipe

inside installer,
install.bat -r [recipe_name] setup
install.bat -r [recipe_name] initialize
install.bat -r [recipe_name] start

#### Command to update the DB

ant updatesystem

