# ceedling-example
An example using ceedling (http://www.throwtheswitch.org/ceedling) to test a simple project.

This project was created by:
 * Installing ceedling as described below.
 * Creating the project using `ceedling new ceedling-example`
 * Copying the .c and .h files from the [unity-example](https://github.com/cu-ecen-5013/unity-example) project into the src directory.
 * Copying the test file from the [unity-example test directory](https://github.com/cu-ecen-5013/unity-example/tree/master/test) into the test subfolder, renaming to match the pattern test_*filename*.c

# Running
To run from your ubuntu VM:
```
sudo snap install ruby
sudo gem install ceedling
```
Then run ceedling by setting up your PATH to include the gem directory
```
PATH="${PATH}:~/.gem/bin/"
ceedling test:all
```
You should see an output like this:
```
--------------------
IGNORED TEST SUMMARY
--------------------
[test_file1.c]
  Test: test_FindFunction_WhichIsBroken_ShouldReturnTheIndexForItemsInList_WhichWillFailBecauseOurFunctionUnderTestIsBroken
  At line (35): "Ignoring this test since we expect it to fail"

  Test: test_FunctionWhichReturnsLocalVariable_ShouldReturnCurrentCounter_ButFailsBecauseThisTestIsActuallyFlawed
  At line (63): "Ignoring this test since we expect it to fail"

--------------------
OVERALL TEST SUMMARY
--------------------
TESTED:  5
PASSED:  3
FAILED:  0
IGNORED: 2
```
