## Test Case 21.4

> Manage module dependency

Pre-condition: N/A

This functionality allows the developer to add/discard dependencies between modules about, e.g., include or import.
The assumption is that the module dependency does not change for a module set used in different releases.

### Test Assertion:

1. The developer can access module dependency management from the Module Set List page. Once the Module Dependency page is opened. The module set from which the function is invoked is selected.
2. The developer can access module dependency management from the application menu. In this case, the newest module set is selected by default.
3. On the Module Dependency page, the developer can select another module set to retrieve module dependencies for the module set.
4. When there is no module dependency information for the module set, the Module Dependency Tree simply lists all the modules in the set.
5. The developer can drag one or more modules over another module to create dependencies. If both modules have namespaces and the namespaces are the same then the dependency type shall be ‘include’; otherwise ‘import’. If one both modules don’t have namespaces, assign the ‘Default Dependency Type’ specified on the UI.
6. The developer can discard one or more dependencies at a time.
7. The developer cannot add a duplicate dependency to the same module.
8. The developer can Derive Dependencies. This allows the dependencies to be derived based on CC-Module Assignment. A dialog shall pop up for the developer to a CC-Module assignment by selecting a release and one of the assigned module sets. The system has to cluster CCs into modules and create a module dependency graph based on CC dependencies. The derived dependencies shall be added to existing dependencies ignoring the duplicated ones that already exist. The same rules about dependency types specified in TA 5 are applied.
9. The developer can Copy Dependencies. This allows the developer to select a module set. Then for modules common across the current and selected module set, the system copies the dependencies of each module into this module set, ignoring the dependencies pointing to a module absence from the current module set.
10. The developer can check for cyclical dependencies in the module set. A cyclical dependency exist b/w two modules A & B if A depends on B and B also depends on A. The dialog box shall list the pairs of modules that have a cyclical dependency where the developer can discard some dependencies.
11. The end user can view module dependency but cannot make any change.

### Test Step Pre-condition:



### Test Step: