## ant clean all
- It checks whether config,log,data,temp etc folders are available inside hybris folder.
- If this folder structure is not available then it creates the folder structure.
- If this folder structure is already available then do nothing.
- If there is no build, It will create a build from scratch, if there is any build exist, It will delete and recreate it.

## ant all
- It assumes folder structure is already exist.
- If there is no build, it will create a build from scratch, if there is any build exist, it will modify it rather than recreating it.

## ant initialize
- Removes all the existing data
- Drops all the existing schema and tables
- Recreates the schema and tables
- Reload the data(seed data given by hybris, we can also load our own data)
