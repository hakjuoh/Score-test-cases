## Test Case 21.1

> Manage Module Set

Pre-condition: N/A

This functionality allows the developer to create and assign modules to a module set.

### Test Assertion:

1. From the Module Set list page, the developer can invoke “Create a Module Set”.
2. At least Name is required (i.e., the Definition field is optional).
	1. The developer can also create a corresponding Module Set Release based on the Module set. In this case, the developer should define the “Release” as well as the assignments to copy from (i.e., Copy CC assignments from existing ones)
3. The developer can edit the details of an existing Module Set. In particular, the developer can edit the Name and  Description fields.
4. The developer has a few ways to add modules to the selected module set.
	1. The developer can create a new module file and add it to the set. For the detail of the module file, only the Name is required (the UI should indicate to the user that backslash is used, maybe by giving an example). Namespace and Version Number are optional. The developer cannot create a new module file without the name.
	2. The developer can change the details of a module (e.g., using a dialog “View/Edit a Module”. The Name of the module is unique in a directory. Namespace and Version Number are optional.
	3. The developer can create a new module directory and add it to the set. For the detail of the module directory, only the Name is required.
	4. The developer can modify the name of a module directory, it cannot be left empty though. The name of the module directory must be unique inside its parent module directory (i.e., there should not be exist two directories with the same name under the same parent module directory; in other words the combination of the name and path of directory must be unique).
	5. The developer can copy a module directory from another Module Set. The developer should also have the option to copy all its module subdirectories and module files as well. The selected module directory, subdirectories and files are then copied (by reference) to the current module set (these modules are sorted alphabetically by the module path). Copy function must be idempotent, i.e., the developer can copy the same set module directory multiple times and only module directories and files not already exist in the current module set shall be added.
	6. The developer can select a module to copy from another Module Set rather than a directory. In that case, only the selected module is copied. This copy function must be also idempotent.
5. The developer can discard a module directory or file currently included in the Module Set.
	1. In case of a module directory that is not empty, the system should ask the developer to confirm that he wants to discard all its module subdirectories and their module files.
	2. If a module file is used in a Module Release Set, the system should ask the developer to confirm that the corresponding assignments to CCs will be also discarded
	3. If a module directory contains a module file is used in a Module Release Set, the system should ask the developer to confirm that the corresponding assignments to CCs will be also discarded. Check also the case of discarding a module directory that contains a module directory which contains a module file.
6. The developer can discard a module set when it has not been assigned to any release.
7. The developer cannot discard a module set that has been assigned to a release (in the Release Module Set).
8. The end user can view module sets but cannot make any change or add a new one.
9. The developer can view any existing module set. He can also edit its details (i.e., there is no ownership).

### Test Step Pre-condition:



### Test Step: