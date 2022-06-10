## Test Case 21.2

> Manage Release Module Set

Pre-condition: N/A

Release module set is an entity that refers to module set the developer would like to use for a release.

### Test Assertion:

1. The developer can create a Release Module Set. The fields “Module Set” and “Release” are mandatories. The former is a drop-down list containing the existing Module Sets and the latter contains all Releases including the Working Branch and a Draft Release Branch.
	1. The developer can select this Release Module set to be the default one for the specific selected Branch.
2. After working on assignment to another release, the developer selects a release previously worked on. The system shall be able to display the module sets already assigned previously.
3. A Release Module Set can be edited by any other developer (i.e., there is no ownership). The fields “Module Set” and “Release” are mandatories.
4. The developer can Export a Module Set Release while viewing the details of a Module Set Release.
5. The end user can view the release module set but cannot make any change.
6. The developer can create a Release Module Set and assign a Draft release.
	1. The developer can move the Draft release back to Initialized state. In this case, the assignments to CCs are not kept (I.e., they are discarded)
	2. The developer cannot discard a Release if it is used in a Module Set Release.
	3. The developer can move the Release to Draft state again. In this case, the Release Module set is updated accordingly so that to contain the CCs of the Draft Release.

### Test Step Pre-condition:



### Test Step: