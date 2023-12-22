- Now and then, code quality becomes an issue in a team and everyone starts to talk about how we can improve unit test and code coverage, but not for long. Eventually, it's not a hot topic anymore as people get busy. But then, you will experience déjà vu probably within a year, because the same idea comes back the next year.
- ## Unit test and code review
	- Peer code review is part of LINE's engineer culture, as our CTO explained to us during OJT. Facebook states the most three important things in development as code review, code review *and* code review. Yes, the only way to address unit test and improve code quality is to make unit test part of our engineer culture, and code review is here to help.
	- ![](https://cdn-images-1.medium.com/max/1600/1*ku5a8sk61smgtNYbfU7SLw.jpeg)
	  Boy scout rule for coding, from [{codemotion}](https://codemotionworld.com/)
	- Follow this boy scout rule which recommends reviewers to check if unit tests supplement new code and bug fixes during a review, and by continuously doing this, code coverage should expand or at least remain the same. For example, if code coverage drops, a reviewee should explain to the team the difficulties he/she is having and the reasons for not adding more tests. If all agree upon the explanation and has no issues, he/she can proceed. Otherwise, the reviewee shall fix it!
- ## Tips for effective code review
	- The most efficient way to do code review is through pair programming, but using PRs (Pull Request) on Github is okay, if this suits your team better. To get code review done, I mean *really* done, we should first try to increase the efficiency of code review processes; the idea is to treat reviewer as a rare resource, because none of our major responsibility is code reviewing, right?!
	  And here are some tips for effective and efficient code review:
	  * [Keep changes small]
	  * [Review often and shorten sessions]
	  * [Send pull request for review as early as possible]
	  * [Provide enough context for creating meaningful pull request]
	  * [Linting and code style check]
- ### Keep changes small
	- A study by a Cisco System programming team has shown that 60 to 90 minute long review over 200 to 400 LoC (Line of Code) yields 70–90% defect discovery. Treat each PR as a releasable unit (feature, bug fix) or a cohesive idea which is meaningful to the PR. To learn why a large pull request hurts and what the optimal size for pull requests is, check [here](https://smallbusinessprogramming.com/optimal-pull-request-size/)([https://smallbusinessprogramming.com/optimal-pull-request-size/](https://smallbusinessprogramming.com/optimal-pull-request-size/)).
	- pic
	  pic
		- Code reviews, from [@iamdeveloper](https://twitter.com/iamdevloper) on Twitter & Defect density vs LoC, from [Cisco study case](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/)
- ### Review often and shorten sessions
	- Code reviews in reasonable quantity, at a slower pace, for a limited amount of time result in the most effective code review. Beyond 400 LoC, the ability to find defects diminishes. Inspection rates under 300 LoC/hr is the best.
	- pic
		- Defect density vs inspection rate, from [Cisco study case](https://smartbear.com/learn/code-review/best-practices-for-peer-code-review/)
- ### Send pull request to review as early as possible
	- To get a valuable code review, start a discussion before implementing details and try not to send big chunks of diffs. Separate different ideas into different PRs and assign different reviewers if needed, by dividing large problems into smaller problems and solving the small problems one at a time.
	- pic: codereview_4.png
		- How workaround gets applied, if architectural/design problems found in the last minute PR during code review, from [@isoiphone on Twitter](https://twitter.com/isoiphone/status/824771226585296896)
- ### Provide enough context for creating meaningful pull request
	- >***Reviewer resource is very limited, treat it wisely!***
	- To help a reviewer get into the context quickly, providing sufficient information is important, such as why and how the change is being made, as well as any risks or concerns observed. Such information is a good catalyst for generating good discussions later. As an added benefit, the author will often find additional errors before the review even begins. Though not every PR is worthy writing such detail, but you can briefly annotate what's been done and tested or which part should a reviewer pay more attention to!
	- [Github issue and pull request templates](https://blog.github.com/2016-02-17-issue-and-pull-request-templates/) might do some help. Also, attaching a screenshot to describe what you are up to is a good idea! Here are a couple of examples on using PR templates to provide meaningful context for code review and further QA verification.
	- pic image2018-10-11_19-27-47.png
	  pic image2018-9-28_18-0-11.png
		- Examples of using Github PR template
- ### Linting and Code Style Check
	- Leave static code analysis and coding style check to machines with tools like [SonarQube](https://www.sonarqube.org/)([https://www.sonarqube.org/](https://www.sonarqube.org/)) and [ESLint](https://eslint.org/)([https://eslint.org/](https://eslint.org/)), and spare human eyes for important parts like business logics and algorithms. These code scanning tools, type checking tools and linting tools can report bugs, [code smells](https://en.wikipedia.org/wiki/Code_smell) and vulnerabilities, along with a good test suite can certainly increase the confidence level.
	- ![](https://engineering.linecorp.com/wp-content/uploads/2018/10/24/1540351983588.png)
		- Detect issues in SonarQube from [SonarQube website](https://www.sonarqube.org/)
-