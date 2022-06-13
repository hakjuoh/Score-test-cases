## Test Case 20.1

> Developer management of namespaces

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
The developer can create a new namespace. He becomes the owner of the namespace. The following business rules must be satisfied.

	1. URI is required and unique. The system should not validate the URI syntax to be a valid URI, i.e., this is actually a text field.
	2. Prefix is optional.
	3. Description is optional.
	4. Standard flag (is_std_nmsp) is True and locked.

#### Test Assertion #2
The developer who is an owner of the namespace can change details of an existing namespace. The modified details must satisfy the business rules same as those indicated in case of a new namespace.

#### Test Assertion #3
The developer and end user who does not own the namespace cannot update it.

#### Test Assertion #4
The developer who is the owner of the namespace can discard it if the namespace has no reference.

#### Test Assertion #5
Any user can see the detail of developer namespace.

#### Test Assertion #6
The owner developer of the namespace can transfer ownership only to another developer.

### Test Step Pre-condition:



### Test Step: