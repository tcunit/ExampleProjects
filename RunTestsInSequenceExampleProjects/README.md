# RunTestsInSequenceExampleProjects

This folder holds several example projects of how to run TcUnit tests in a sequence.  

The following example projects are available:

- [**SequentialTestSuitesAndTests**](https://github.com/tcunit/ExampleProjects/tree/master/RunTestsInSequenceExampleProjects/SequentialTestSuitesAndTests)  
This example shows how to run both:

  - Test suites in a sequence
  - Individual tests in a certain order  

  The program executes the test suites one after the other, with a delay of `T#0MS` between each other (that is, as soon as one test suite has finished executing, the next one starts to execute immediately after). This delay is defined in the call to `RUN_IN_SEQUENCE(T#0MS)`. Within each test suite, the program also executes each test one after the other, which is achieved by calling the `TEST_ORDERED()` for every test. The test-order is defined by the order of which the tests are being called.

- [**SequentialTestsWithStateMachines**](https://github.com/tcunit/ExampleProjects/tree/master/RunTestsInSequenceExampleProjects/SequentialTestsWithStateMachines)  
    This example executes the test suites one after the other, with a delay of `T#5S` between each other (that is, as soon as one test suite has finished executing, the next one starts to execute 5s later). This delay is defined in the call to `RUN_IN_SEQUENCE(T#5S)`. Within each test suite, the program executes each test in sequence one after the other, which is achieved by calling the `TEST_ORDERED()` for every test. The test-order is defined by the order of which the tests are being called. The tests include tests for function blocks which need several cycles to complete, as the function blocks under tests use both state machines and times to complete and to reach their correct output state.

- [**MixedSequentialAndParallelTests**](https://github.com/tcunit/ExampleProjects/tree/master/RunTestsInSequenceExampleProjects/MixedSequentialAndParallelTests)  
    This example executes four tests in a sequence, and on top of this there is also one test that runs in parallel with the other four tests. The execution of tests in a sequence is achieved by calling the `TEST_ORDERED()` for the four tests, and `TEST()` for the test that runs in parallel with the other. The test-order of the sequential tests is defined by the order of which the tests are being called. The tests include tests for function blocks which need several cycles to complete, as the function blocks under tests use both state machines and times to complete and to reach their correct output state.

For more information see the [following FAQ](https://tcunit.org/#/faq?id=_7-is-it-possible-to-run-test-suites-andor-tests-in-a-sequence) on the TcUnit FAQ.  
**Note that version 1.2** (or later) of TcUnit is required to run test suites and tests in a sequence.
