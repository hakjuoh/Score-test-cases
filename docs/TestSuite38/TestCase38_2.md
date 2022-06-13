## Test Case 38.2

> Creating a brand-new DT

Pre-condition: N/A

### Test Assertion:

#### Test Assertion #1
On the CC list page where a working branch is selected, the developer can create a brand-new DT after selecting a based DT. The new DT has the following default values – Based Data Type= [DEN of Based DT] and disabled, Data Type Term = [Data Type Term of Based DT] and disabled, Representation Term = [Representation Term of Based DT] and disabled, Qualifier = [Qualifier of Based DT] (the system may tokenize qualifiers) if any, otherwise empty; DEN = [Qualifier] “ “ + [Data Type Term] + “. Type” and disabled; Six Digit Identifier= blank; Namespace = [Namespace of Based DT] if available, Definition Source=blank, Definition=blank, Content Component Definition=[Content Component Definition from Based DT], Comments = empty. There must be entries in the Value Domain that are inherited from based DT – those can’t be edited. The brand-new DT must not have any release assigned yet, i.e., it must not appear in any release branch except the working branch. It has a revision number 1. All fields are required and cannot be blank except Qualifier, Six Digit Identifier, Definition, Definition Source, Content Component Definition and Comments.

#### Test Assertion #2
The developer cannot create a brand-new developer DT when a release branch is selected.

### Test Step Pre-condition:



### Test Step: