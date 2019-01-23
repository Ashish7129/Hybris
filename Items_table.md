## Table Types 
- Item type tables : The major part of the list of hybris database tables is item type tables. 
  These tables are created automatically from *-items.xml during the system init or update process

- Localized values tables :Actually, in this process some of other tables are created or updated too.
  For example, localized values tables are created if you have at least one localized attribute.
- Generic Audit Tables : Generic audit tables are created for all item type tables automatically
- Property Tables
- System Tables


Dynamic Attributes in item table

- when the persistance type is property.In this case, Corresponding column will be created in the database and hence the values will be stored in the DB. So it’s called persistent attribute
```sh
persistent type=”property”
```
- when the persistance type is dynamic.There will be no column created in the database and hence values will not be stored in the database.So it’s called Non persistent or dynamic attribute.
```sh
persistent type=”dynamic”
```

Note : For every dynamic attribute we define, we need to mention the attribute handler otherwise Bean Id will be generated automatically and we have to use the same bean id while defining Spring bean in XML.Attribute handler is implemented using Spring.So we need to mention the spring bean id for the attribute handler.Then we need to define the class for that spring bean id which provides the custom logic for the dynamic attribute.
It is possible that one item type can have any number of dynamic attributes.
