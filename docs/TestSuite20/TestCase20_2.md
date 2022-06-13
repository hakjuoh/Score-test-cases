## Test Case 20.2

> End user management of namespaces

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
The end user can create a new namespace. He becomes the owner of the namespace. The following business rules must be satisfied.

	1. URI is required and unique. This is a text field. Do not validate the URI format.
	2. Prefix is required and unique.
	3. Description is optional.
	4. Standard flag (is_std_nmsp) is False and locked.

#### Test Assertion #2
The end user who is an owner of the namespace can change details of an existing namespace. The modified details must satisfy the business rules same as those indicated in case of a new namespace.

#### Test Assertion #3
The developer and end user who does not own the namespace cannot update it.

#### Test Assertion #4
The end user who is the owner of the namespace can discard it if the namespace has no reference.

#### Test Assertion #5
Any user can see the detail of end user namespace.

#### Test Assertion #6
The owner end user of the namespace can transfer ownership only to another end user.

### Test Step Pre-condition:



### Test Step: