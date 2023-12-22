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