## Three levels of test isolation
	- #### TestContainers (mocks, stubs)
	- #### TestContext & default objects
		- To demo three levels of test isolation for parallel auto testing and pipeline stability: [test-isolation-demo](https://github.com/pofengliu/test-isolation-demo)
- ## Other practices
	- Tests should be useful:  integrated and AC first
	- Tests should be maintainable: tests are written to be refactorable in the future
		- TestContext for maintainabilities
		- ESlint - to make sure there are no lint errors
	- Tests should be reliable: test isolation, run 20 times in a row before accepting PR
		- Leverage PullRequest checks
		  ![dry_run_PRchecks.png](../assets/dry_run_PRchecks_1672647081538_0.png)
		-
	- Tests should be fast: mocking is a necessary. 80% uses mocking data, 20% e2e integration
		- Parallelism is a must as features grow faster than you think