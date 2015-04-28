## Getting Started ##

### Before you Start ###

Before you begin creating your component, you will first need to determine if a similar component already exists for ESAPI, and if so - can you extend that component to address the solution or is a new component required?

### Design ###

It is important to remember to design your component for extension. The key of ESAPI Components is that they should be based on configuration as much as possible for the situation you are addressing. Even if you feel that the component you would like to contribute is so specific that there couldn't possible be any extension points that people would want to extend from - it is impossible to foresee the needs of every codebase and you never know what situation may arise where a user needs to slightly alter the execution flow of a particular part of your component. The most important thing is to leverage the work of the community by adapting from the work that others have already contributed. For instance, if you are contributing a custom encoding component for Velocity to be used in a Struts webapp - you may be able to bridge existing packages (say an ESAPI-Struts adaptor and an ESAPI-Velocity adapter) to create your component with minimal effort.