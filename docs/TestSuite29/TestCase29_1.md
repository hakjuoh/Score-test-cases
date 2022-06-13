## Test Case 29.1

> 

Pre-condition: There should exist at least two published releases. There should also be some BIEs in a non-latest release. Some of them should reuse a BIE and have an extension (UEGACC).

### Test Assertion:

#### Test Assertion #1
A BIE can be uplifted only to a newer release than the one the BIE belongs to.

#### Test Assertion #2
A user can uplift any QA or Production BIE. If he does not own the BIE, then he takes the ownership of the uplifted BIE.

#### Test Assertion #3
A user cannot uplift a WIP BIE he does not own.

#### Test Assertion #4
The assigned business contexts shall be transferred to the uplifted BIE.

#### Test Assertion #5
During the uplifting process, there should be two panels; one showing the tree of the BIE to be uplifted (source BIE) and one showing the uplifted BIE (target BIE). The actions of the system and the user can be:

	1. If all nodes between two BIEs match (i.e., there is no CC refactoring between two releases), there should be no checkbox in the source BIE and all checkboxes in the target BIE should be disabled.
	2. In case that a node does not match (i.e., because of refactoring a CC or extensions), there should be a checkbox in front of that node in the source BIE. The user can click on that node and then click on the node of the target BIE that wants to match with.  Matching is allowed only between nodes of the same type, i.e., ASBIE/ASBIEP/ABIE node with ASBIE/ASBIEP/ABIE node, BBIE node with BBIE node, and BBIE_SC node with BBIE_SC node. The details of the source node are transferred to the target node. However, its child nodes have to be matched separately in case they do not automatically match, i.e., the user has to perform this process for all unmatched nodes.
	3. If a map is performed on a descendant node on the target BIE, the ancestor nodes shall be automatically checked, but no BIE information is copied to any of those ancestor nodes.
	4. If a node of the source BIE is a reuse node and it was not automatically mapped, the user can map it to a node in the target BIE. Once mapped, the user can select a BIE to reuse in the target BIE. This reused BIE shall belong to the newer release (this might also be a previously uplifted BIE). If the user does not select a BIE to reuse, then only the ASBIE information (i.e., the association information and not the profiled details) are transferred from the source reused node to the target node.

#### Test Assertion #6
The uplifted BIE should include the nodes along with their details with the following rules.

	1. If a node was enabled, it should be also enabled in the uplifted BIE. All its details should be transferred as well.
	2. If a node is not enabled, it should not be enabled in the uplifted BIE. In addition to that, its details should not be transferred.

#### Test Assertion #7
The user can uplift a BIE without matching all nodes, i.e., he can leave some nodes unmatched. In that case, the uplifted BIE should not contain the information of the node left unmatched.

#### Test Assertion #8
The user can uplift a BIE by matching a node to another node with different term (e.g., the “Sender” to the “Document Identifier Set”). In that case, the uplifted BIE should contain only the association information (i.e., those of the “Sender”).

#### Test Assertion #9
The selected Primitive Value of a source BBIE or BBIE_SC node should:

	1. Be transferred to the target BBIE or BBIE_SC node in case of system map.
	2. Be transferred to the target BBIE or BBIE_SC node in case of manual map considering that the Primitive value is allowed in the target BBIE or BBIE_SC node.
	3. Not be transferred to the target BBIE or BBIE_SC node in case of manual map if the value is not allowed. In this case the value of the set target BBIE or BBIE_SC node is set to the default one.

#### Test Assertion #10
If a source BBIE or BBIE_SC node has a specific developer code list or agency ID list applied:

	1. It should be transferred to the target BBIE or BBIE_SC node in case of system map providing that the developer code list or agency ID is found in the target release. Otherwise, the BBIE or BBIE_SC node is set to default primitive value.
	2. It should be transferred to the target BBIE or BBIE_SC node in case of manual map providing that the developer code list or agency ID is found in the target release (using primary key) and the code list or agency ID is allowed in the target BBIE or BBIE_SC node. Otherwise, the BBIE or BBIE_SC node is set to default primitive value.

#### Test Assertion #11
If a source BBIE or BBIE_SC node has a specific end user code list or agency ID list applied:

	1. It should be transferred to the target BBIE or BBIE_SC node in case of system map providing that the end user code list or agency ID is found in the target release. Otherwise, the BBIE or BBIE_SC node is set to default primitive value.
	2. It should be transferred to the target BBIE or BBIE_SC node in case of manual map providing that the end user code list or agency ID is found in the target release and the code list or agency ID is allowed in the target BBIE or BBIE_SC node. Otherwise, the BBIE or BBIE_SC node is set to default primitive value.

#### Test Assertion #12
Paths of unmapped source nodes including the code list and agency ID list nodes shall be expressed in an uplift output/log file. If the unmapped node is a reused node, the path shall be indicated as Reused. There is no need to include paths of the descendant nodes of the reused BIE node.

### Test Step Pre-condition:



### Test Step: