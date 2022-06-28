- ## Process Overview:
  ![SeB & Acceptance Test.jpg](../assets/SeB_&_Acceptance_Test_1650361331009_0.jpg)
- ## 實例化需求 (Specification By Example)
  實例化需求 (SBE) 是一種協作的軟體開發方式，使用具體的案例與自動化驗收測試來展示業務需求的一種模式，實例化需求能讓我們用以==正確的方向建置產品 (Build the right product)==。而釐清需求的 Product backlog refinement meeting (PBR) 正好位在開發流程==中央的位置==，上承 product backlogs (planning) 下接 implementation and verification (development)。團隊能如實討論及產出 PBR 的交付項目，a.k.a "Acceptance Criteria"，才能有效確認開發上下游對產品需求的一致性!
  ![image.png](../assets/image_1656336814628_0.png)
- ## 實例化需求對我們帶來的幫助
	- ### SbE 的好處：
	  * 達成開發團隊內部對產品需求產生一致性的共識
	  * 減少溝通需求所花費的時間與成本 (communicate efficiently)
	  * 明確訂定需求範圍 (reduce waste)
	  * 減少Production defect (upfront-design, shift-left testing)
	  * 能快速修改反映需求上的變化 (living-document)
	- ### SbE 十年後的驗證
	  [Specification by Example, 10 years later](https://gojko.net/2020/03/17/sbe-10-years.html)，內有說明 ==SbE 書籍相關論述==十年後社群調查的結果！
	- ### 對 CI Pipeline 的信心
	  What we see sometimes is, folks are very focused on automation and speeding things up, but not like, am I actually getting what I want from it? So for example, again, back to the automated testing example, often regression tests, there’s a lot of focus on==automating everything==, but sometimes the output, the test results, are too difficult for a team to actually understand that they disregard the test.Tim Cochran, Technical director at ThoughtWorks,
- ## 執行細節
  For full content, see "Hierarchy" section below