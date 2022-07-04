public:: true

- title:: 實例化需求 (Specification by Example)/Key Process Patterns
- ![image.png](../assets/image_1656910755612_0.png)
- ## Deriving scope from goals
  團隊以客戶的業務目標開始，經由協作了解背後的價值並界定預計達成的目標範圍，產生使用者故事 (user stories) 並且能簡單舉例 (high level examples) 說明之。
- ## Specifying Collaboratively
  SbE 的重點之一，經由團隊的共同討論 (face-to-face with whiteboard) 並探索出最佳解法 (solutions)。
  ![image.png](../assets/image_1656916571952_0.png)
  Figure. Illustrating specifying collaboratively, by Gojko and Jeff Patton & Associates
- ## Determine Key Examples
  團隊成員通過工作坊的方式制定需求規格，通常來說，先用實例來描述，推測一些規律，轉成用表格表達，可能發現更準確的規律。
  Every acceptance criterion generates new examples; every example generates new scenarios. Teams should refine their specifications to merge similar examples, reject the ones that introduce noise, and choose the most meaningful or descriptive ones.
	- ![image.png](../assets/image_1656924162490_0.png) 
	  Reference: [Writing Great Specifications](https://livebook.manning.com/book/writing-great-specifications/chapter-1/point-15744-257-257-0) and [Fifty Quick Ideas To Improve Your Tests](https://gojko.net/2014/05/05/focus-on-key-examples/)
	- #+BEGIN_TIP
	  Complex specifications
	  * ==Don’t invite discussions==
	  * Technical model is misaligned with the business model
	  * Described at the wrong level of abstraction
	  * ==Usually means refining a story isn't done==
	  #+END_TIP
	- #+BEGIN_TIP
	  Key examples
	  *  A small number of relatively simple scenario
	  * ==Easy to evaluate and argue about boundary conditions==
	  * Easier to discover and resolve inconsistencies
	  * (raw examples won't provide above two advantages)
	  * Right level of abstraction to describe situation better
	  * Satisfy business needs faster
	  * Modularized software reduces future maintenance costs
	  #+END_TIP
- ## Refining the specification
  需求規格應該是精確、能被驗證、不言自明並且是跟商業規則有關係的。承上信用卡清算案例，一個明確的需求規格如下：
  ![image.png](../assets/image_1656923937867_0.png)
	- #+BEGIN_TIP
	   Good specifications
	  * Have a concise description
	  * Have a clear model
	  * Use business language
	  * Show a clear connection between inputs and outputs
	  * ==Describe (focus on) WHAT not HOW==
	  * ==Avoid GUI specifics==
	  #+END_TIP
	  ![image.png](../assets/image_1656923368787_0.png) 
	  思考點：當預付點數只剩 6.5 但票價要 7 元時，你買還是不賣這票呢？
- ## Automating validation without changing specifications
  以自動化測試驗證實作標的來確保符合商業需求，實作 executable specifications 部份，後面章節會有相關程式碼展示。所以這些可被執行的規格文檔可用來說明程式的功能 (functionality) 與行為 (behaviors)，並針對當下的程式代碼檢驗規格的完整性 (compliance)。
- ## Validating frequently
  每當有程式碼提交到版本管控系統，則觸發相關的 continuous integration pipeline 自動執行這些自動化測試，以確保系統符合業務目標。
- ## Evolving a documentation system
  藉由不斷地更新需求規格 (specifications) 來反映商業邏輯上的變化，並演化成活的說明文件系統 (Living Documentation)。如何從規格文檔產生活文件，實作部份後面章節會有相關展示。