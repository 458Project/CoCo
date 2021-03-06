# Team CoCo - CISC/CMPE 458 Programming Language Processors - Phase 4 Submission
Phase 4 of the CISC/CMPE 458 project outlines changes to the code generator of the PT Pascal compiler to allow for it to be adapted to the new Quby language. Specifications of the Quby language can be found on the CISC/CMPE 458 course website. The changes made to the code generation components of the compiler are described throughout the documentation provided.

## Documentation
### Main documentation file:
./ddocumentation.txt
### A documentation file can also be found for each test case in the corresponding test suite directories. The files have been listed below for convenience.
testStuite/repStmt/repStatementTestCaseDocumentation.txt
testStuite/profExamples/profExamplesTestCaseDocumentation.txt
testStuite/modules/modulesTestCaseDocumentation.txt
testStuite/selStmt/selStatementTestCaseDocumentation.txt
testStuite/strings/stringsTestCaseDocumentation.txt

## Directory structure
* phase4
   * ptsrc/ (complete source code including code generator, semantic phase, parser, and scanner/screener changes)
   * README.MD (this file)
   * ddocumentation.txt (main documentation file)
   * testSuite/
		* coder (Automated test suite for testing Quby semantic phase)
			* modules/ (test suite for Quby's new 'mod' block)
			* profExamples/ (test suite with full Quby programs for testing)
			* repStmt/ (test suite for Quby's new 'rep' block)
			* selStmt/ (test suite for Quby's new 'sel' block)
			* strings/ (test suite for Quby's string declarations/assignments/operations)
			* TestAll (Script used to run and verify all code generator related tests)
		* semantic (Regression test suite for testing Quby semantic phase)
			* declarations/ (test suite for declaration changes)
			* ifStatement/ (test suite for 'if'/'elif'/'else' statement related changes)
			* inputOutput/ (test suite for input/output related changes)
			* modules/ (test suite for Quby's new 'mod' block)
			* profExamples/ (test suite with full Quby programs for testing)
			* repStmt/ (test suite for Quby's new 'rep' block)
			* routines/ (test suite for routine and procedure related changes)
			* selStatement/ (test suite for Quby's new 'sel' block)
			* strings/ (test suite for Quby's string declarations/assignments/operations)
			* TestAll (Script used to run and verify all semantic related tests)
		* parser (Regression test suite for testing Quby parser)
			* assignmentStatement/ (test suite for all assignment operator changes)
			* conditionals/ (test suite for all conditional operator changes)
			* declarations/ (test suite for declaration changes)
			* ifStatement/ (test suite for 'if' statement related changes)
			* iterativeAssignments/ (test suite for Quby's new iterative assignments)
			* modules/ (test suite for Quby's new 'mod' block)
			* program/ (test suite for program syntax changes)
			* repStatement/ (test suite for Quby's new 'rep' block)
			* routines/ (test suite for routine and procedure related changes)
			* selStatement/ (test suite for Quby's new 'sel' block)
			* strings/ (test suite for Quby's string operations)
			* TestAll (Script used to run and verify all parser related tests)
		* scannerScreener (Regression test suite to ensure no scanner functionality has been affected)
			* characterClasses/ (test suite for character class changes)
			* comments/ (test suite for comment related changes)
			* keywords/ (test suite for keyword related changes)
			* stringLiterals/ (test suite for string literal changes)
			* syntaxTokens/ (test suite for syntax token changes)
			* TestAll (Script used to run and verify all scanner/screener related tests)

## How to run tests
### Code Generator Automated Test Suite
To run all of the code generator related test cases (encompassing the 5 test suites seen above), simply run the bash script provided in the coder testSuite directory (**testSuite/coder/TestAll**). This script will both **run** all of the tests using the input files provided (testSuite/coder/\*/inputFiles) and place the outputs into "testSuite/coder/\*/outputFiles" and also **verify** the output files against the expected output in "testSuite/coder/\*/expectedOutputFiles.
An output file containing the console output (print statements) as well as .compile and .error files are created for each test and compared to the exprected output. The .compile test has the stdout of the compiler, and .error contains the error stream provided by the compiler. In this was even error cases can be tested using the test suites.
### Semantic Phase Automated Regression Test Suite
To run all of the semantic related test cases (encompassing the 9 test suites seen above), simply run the bash script provided in the semantic testSuite directory (**testSuite/semantic/TestAll**). This script will both **run** all of the tests using the input files provided (testSuite/semantic/\*/inputFiles) and place the outputs into "testSuite/semantic/\*/outputFiles" and also **verify** the output files against the expected output in "testSuite/semantic/\*/expectedOutputFiles.
Ssltrace was used with the "-e" output token mode to show the t-code outputted by the parser in a condensed human readable form.
The output file for each test contains the ssltrace output as well as any error messages provided by the compiler (by appending output of "ptc -L ../lib/pt filename.pt").
### Parser Automated Regression Test Suite
To run all of the parser related test cases (encompassing the 11 test suites seen above), simply run the bash script provided in the parser testSuite directory (**testSuite/parser/TestAll**). This script will both **run** all of the tests using the input files provided (testSuite/parser/\*/inputFiles) and place the outputs into "testSuite/parser/\*/outputFiles" and also **verify** the output files against the expected output in "testSuite/parser/\*/expectedOutputFiles.
Ssltrace was used with the "-e" output token mode to show the semantic tokens outputted by the parser in a condensed human readable form.
The output file for each test contains the ssltrace output as well as any error messages provided by the compiler (by appending output of "ptc -L ../lib/pt file").
The regression test suite ensures that all functionality implemented in phase 2 has not regressed (changed).
### Scanner/Screener Automated Regression Test Suite
To run all of the test cases related to the scanner/screen portion of the compiler, simply run the bash script provided in the scannerScreener testSuite directory (**testSuite/scannerScreener/TestAll**). This script will both **run** all of the tests using the input files provided (testSuite/scannerScreener/\*/inputFiles) and place the outputs into "testSuite/scannerScreener/\*/outputFiles" and also **verify** the output files against the expected output in "testSuite/scannerScreener/\*/expectedOutputFiles.
The regression test suite ensures that all functionality implemented in phase 1 has not regressed (changed). In general regression testing is a quick and simple check to ensure your new changes aren't affecting old functionality.

## Authors
* Group: cisc458n
   * Parv Mital
   * Mitchell Waite
   * Clara Fu
   * Johan Cornelissen

