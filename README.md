# test_reflective_loader

Support for discovering tests and test suites using reflection.

It follows the xUnit style where each class is a test suite, and each method
with the name prefix "test_" is a single text.

Methods with names starting with "test_" are are run using test() function with
the corresponding name. If the class defines methods setUp() or tearDown(),
they are executed before / after each test correspondingly, even the test fails.

Methods with names starting with "solo_test_" are run using solo_test() function.

Methods with names starting with "fail_" are expected to fail.

Methods with names starting with "solo_fail_" are run using solo_test() function
and expected to fail.

Method returning Future class instances are asynchronous, so tearDown() is
executed after the returned Future completes.

## Features and bugs

Please file feature requests and bugs at the [issue tracker][tracker].

[tracker]: https://github.com/dart-lang/test_reflective_loader/issues
