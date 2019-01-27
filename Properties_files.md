Two essential configuration files :
- project.properties (default confgurations)
- local.properties (your own configuration)

#### Each file has a different priority and its values can override the values of another lower priority file.

### local.properties (highest priority)
  - copy of project.properties
  - use to set the properties need to configure your project.
  
### project.properties (Extension specific)
  - located in a particular extension directory
  - defines the value used for extension.
  
### project.rpoperties (global)
  - provides default settings
