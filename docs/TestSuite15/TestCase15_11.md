## Test Case 15.11

> Editing a brand-new end user ASCCP

Pre-condition: N/A



### Test Assertion:

1. The end user can change the properties of the ASCCP and save the changes with the following business rules.
	1. The fields “Property Term”, “Reusable”, “Definition”, “Definition Source”, “Namespace”, and “Nillable” can be changed.
	2. Deprecated field is locked at the value false.
	3. The field “DEN” is automatically changed based on the changes of the “Property Term” field and the “Object Class Term” of the ACC.
	4. A warning should be given when the Definition is empty.
	5. The fields “GUID” and “DEN” cannot be changed.
	6. The fields of the Associated ACC and its children nodes cannot be changed.
	7. The developer can choose a new ACC in the same release for the ASCCP. ASCCP DEN shall be automatically updated.
	8. Only non-standard namespace shall be allowed for the “Namespace”.
	9. “Property Term”, “Reusable”, “Namespace”, and “Nillable” are required. [Note that Namespace is required for ASCCP, so the User Extension Group ASCCP perhaps should have a namespace too. In this case, once the user assign a namespace to the UEGACC, the system shall assign that namespace to the UEGASCCP too.]
2. The end user can transfer the ownership of an ASCCP, which is in WIP states and he owns, to another end user but not developer.
3. If Object Class Term of the ACC used by the ASCCP changes, DEN of the ASCCP shall get updated. This should occur only when both the ASCCP and ACC have revision #1.
4. When the ASCCP DEN changes, all ASCCs which uses the ASCCP and whose revision numbers are 1 shall have their DEN updated accordingly.
5. The end user can Exclude SCs or not from the Searching Field by checking or unchecking the “Exclude SCs” checkbox accordingly.
	1. If the “Exclude SCs” checkbox is enabled (i.e., checked) the SCs are excluding from the searching field
	2. If the “Exclude SCs” checkbox is disabled (i.e., unchecked) the SCs are excluding from the searching field

### Test Step Pre-condition:



### Test Step: