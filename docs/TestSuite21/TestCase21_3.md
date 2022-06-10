## Test Case 21.3

> Manage CC-Module Assignment

Pre-condition: The developer is on the CC-Module Assignment page. At least two releases are available in the database. Each release has at least two module sets assigned.

CC-Module assignment allows developers to assign CCs to the modules in a module set. CCs must be in the same release as the module set.

### Test Assertion:

1. All branches are available to select from.
2. After the developer select a release, only module sets assigned to that release can be selected.
3. After both the release and module set have been selected, CCs and Modules are listed in the “Unassigned CCs” and “Module” pane. Neither ASCC nor BCC are listed.
	1. The developer can select one CC and a module and assign the CC to that module. The assigned CC shall then be moved from the “Unassigned CCs” pane to the “CCs in Module” pane (or to “Assigned in “module_name””); the selected module shall still be highlighted.
	2. The developer can select a few CCs and a module and assign those CCs to that module. The assigned CCs shall then be moved from the “Unassigned CCs” pane to the “CCs in Module” (or to “Assigned in “module_name””) pane; the selected module shall still be highlighted.
	3. The developer selects the module used in 2.1, and the system shall show the CCs assigned in 2.1 in the “CCs in Module” pane.
	4. Similar to 2.2 but the developer can use “CC Filter by DEN” and “Module Filter” to help with the assignment.
	5. The developer cannot select multiple modules at a time.
	6. With a module selected in the Module pane, the developer can select multiple CCs in the module and unassign them. The unassigned CCs shall be moved from the “CCs in Module” pane to the “Unassigned CCs” pane.
4. The end user can view CC-Module assignment but cannot make any change.

### Test Step Pre-condition:



### Test Step: