## Test Case 41.2

> Creating a brand-new DT

Pre-condition: N/A



### Test Assertion:

1. On the CC list page where a release branch is selected, the end user can create a brand-new DT after selecting a base DT. The new DT has the following default values – Based Data Type= [DEN of Base DT] and disabled, Data Type Term = [Data Type Term of Base DT] and disabled, Qualifier = [Qualifier of Base DT]; DEN = [Qualifier] + [Data Type Term] + “. Type” and disabled; Six Digit Identifier= blank; Namespace = null, Definition Source=blank, Definition=blank, Content Component Definition=blank, Comments = empty, Primitive=[Base DT Primitive], Primitive XML Expression=[ Base DT Primitive XML Expression]. The brand-new DT belong to a specific release, i.e., it must not appear in the working branch. It has a revision number 1. All fields are required and cannot be blank except Qualifier, Six Digit Identifier, Definition, Definition Source, Content Component Definition and Comments.
2. The end user cannot create a brand-new end user DT when the working branch is selected.

### Test Step Pre-condition:



### Test Step: