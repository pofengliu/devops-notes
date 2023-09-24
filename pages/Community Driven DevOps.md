public:: true
type:: blogpost

- 此為 DevOpsDays Taipei 2023 - Community Driven DevOps 內容筆記
- ## DevOps Evangelist 經驗分享
	- ### About Me & LINE TW & Demo
	- ### DevOps Evangelist & Faiths
		- #### 信仰來源
			- ##### 解決身邊沒效率的問題
				- 曾經有一位 QA 過來問我，為什麼我前天在 production測了這個 hotfix 今天在 integration 測了同一個 Hotfix，下一週的 Release Testing Plan，這個 Hotfix 又要再測一次？當然我就畫了圖解釋給大家聽，在這個Hotfix進來的時候，integration Branch 跟 future Branch 的 codebase 都已經不一樣了，所以我們當然要再 verify 一次。（這些做測試計畫的技巧都是當時 PM 或 release manager 所需要具備的知識）。當時在我講完這句話後心裡就有一個念頭，如果測試這件事是這麼的 tedious 那怎麼可能 Google、微軟的那些測試大神到五、六十歲還會這麼有興致的在講這些議題？國外的軟體測試我想應該不是這樣子的。當然這位 QA 幾年後也就轉職 RD... 可見 tedious work 浪費資源而且留不住有創意的人，在 branches 間不斷地 re-testing，一般的 QA 其實根本也沒空練習與實作探索性測試。
			- ##### 解決身邊不合理的流程
				- 曾經我帶領一個QA團隊在做一個跨國的金融專案，工程師大部分都是在國外，那也因為我們的自動化測試做得很好所以一開始是 24 個人做這個案字，到最後剩 13 個人但卻可以同時做三個案子，因為自動化做完之後其實我們每次的 regression 都很快，所以有能力再接更多的案子。不過這邊的代價是，像我每天早上一到公司我就得花一到兩個小時檢查為何昨天的pipeline 會跑失敗，那當然可能的原因是 developer check-in了新的程式的代碼或者是他的代碼造成了其他的 bug 跟 side effect，當然也有可能是自動化測試的 flaky 問題。這樣其實也做了幾年直到有一天我突然想到為什麼我每天都要花時間在這些事情上面，難道這些時間不能拿來做更好的利用嗎？回頭來看這件事情是 Developer 的錯嗎？他不過就只是提交了他的代碼而已。那這件事情是AE的錯嗎，也不是呀，因為我們的 automation，如果 single thread 在跑需要跑個6 個小時左右吧，你就可以知道那個裡面有數百數千隻的 integration 測試，當然我們是把它做得很好，只要沒有新的代碼進來它不管跑幾次結果都是99%、100% ，所以我們是很有自信的，所以這也不是 AE 的錯。總歸來講就是這個 process 本身就是這麼不合理，為什麼一件事情就得拆成兩階段去完成呢？！所以這些數百支數千支的 test automations， developer 會來看嗎？就我做了這麼多的案子，從來沒有而且Developer 做自己的 unit test，AE 做自己的Integration 跟 End-to-End，這些都帶來非常多的 test coverage的重複，也因為各做各的，其實就算 pipeline 跑完了也沒有人能夠了解全部的測試內容，更不用說對於 pipeline 結果能夠帶來什麼樣的信心，在上版前還是需要搭配許多的手動測試！
				- ==當然這些不合理、沒有效率的事情在今天要講的單主幹開發裡面，它都不會發生！==當我理解了背後的原理，我就決定要去推廣所這謂 DevOps 的 Elite culture。
				- 不過現實是... 不管是 Accelerate 這本書的內容或是 DevOps Handbooks 裡面講的所謂三步工法，當你對所有 RD 講完之後，大家都是興趣缺缺，那所謂單主幹開發更是覺得這種上不了檯面的技巧怎麼會拿出來講呢？Gitflow 的 feature branch 才是王道吧!
		- #### 軟體公司的數字化轉型?
			- ##### 快速交付是種「能力」！
				- 能力跟競爭力還是有差別的！競爭力大部分能夠用錢來提升，但能力確很難培養。比如說公司為提升競爭力，可以花錢導入JIR、買 CRM 等軟體，想要做好版控提升品質，有錢的去買GitHub，經費比較少的用 GitLab，但是不管你買了哪一個，想要做到快速交付，那根本就是兩碼事，快的能力是要部門間完美的配合及磨練出來的。
				- 一般 RD 眼前幾個 sprints 就夠燒腦，誰有心情看 4  年後的事... 就算努力改變去練習上面所提到的這些能力，對於下個 sprint、年底考績、明年團隊人數的成長有幫助嗎？ 我想難有直接幫助... 如果是這樣當你所講的無法跟大家的短、中期利益有幫助，那你又期盼對方能給你什麼樣的回饋呢？！
				- 對於企業來說呢，哈佛商業評論裡面講到，過去的50年美國最大的五百家企業，S&P500，平均企業壽命已經從 60 年降到 18 年，wow 這個差距之大讓後續有更多針對這課題的討論。 DevOps 的 Enterprise Journal 裡面也提及==業務的敏捷是生存的基本，先行者優勢已經被速度快的所取代。然後商業上的大規模轉型呢得要依賴科技，基本上之後的公司大概都是軟體公司， 能夠快速交付就變成企業生存的關鍵！所以難怪說軟體的相關指標超過上百個都不為過，那為何 DORA 偏偏挑這四個，且其中三個還是跟速度、頻率有關係，可見交付速度的重要性！！==
				- 這張圖是State Report 裡面交付效率的一個分群，所以你看到 2021 年 elite 加上 high 的比例已經超過 66%，那如果大家都是高分那就沒什麼意思了，所以在 2022 年的時候他就把 elite 等級拿掉並把 high 的要求拉高。所以原本能夠做到 weekly release 就是 high 的等級，到了2022年你如果還要維持在 high 那勢必得做到 release on demand 就是所謂的 "multiple deploys per Day"。
				  所以不進則退，==但我想要講的是 release on-demand 在實作上、思維、策略跟技巧跟其它的等級都不一樣！這也是為何一直想強調 elite culture 後面的道理的！==
				- 這邊常有個誤會，舉例來說，葉問葉師傅可以一次打20個，這是一個苦練出來的能力，但不代表他每天都要出去打 20 個，難道要打到沒朋友嗎？對企業來講也是一樣，我能夠做到 multiple release a day，那我可以根據商業的需求改成 daily、weekly 或是 monthly release 都是沒問題的。但反過來說，哪天當 biz 醒過來，要求你做到更快速地交付時，你有辦法嗎？其實是很難的，因為這是要長時間培養的能力！==所以不要抱怨 planner 要求的功能做出來都沒有人用，你的 pipeline 能提供簡單、快速、低成本的 A/B testing 來讓他可以快速去驗證他的假設嗎？==
				- 這邊我們看到 SpaceX 每天可以在 production release 一萬七千多次，他們試錯成本這麼高每個火箭造價動輒上百萬美元，有時上面還坐了人呢！他們也是講 DevOps 跟 continuous testing ！另外，特斯拉也是講 SCRUM、講 Agile，可是你看人家生產線上的 sprint 可是以五個小時為單位，有些工作站的節點甚至是以三個小時為一個 sprint。所以當我在聽這些 podcast 或conference 的時候，你會發現他們談的 DevOps, Agile and Scrum 裡面的原理跟工法跟我們學的完全一模一樣，但差別在於他們把最核心的縮短 release cycle 做到一個極致！
			- ##### 具備「快」的「能力」
				- 要快，最佳、最安全的起手勢就是 Trunk-based 加上 feature toggling。這邊講最安全是因為你在網路上可以找到太多的成功案例、教材、工法與工具。單主幹開發細節在這就不多說，但一個功能開關（feature toggle）可以讓你把未完成的代碼藏起來讓你每天可以至少跟主幹合併一次做到真正的 CI。另外同一個開關可以用來讓 QA 打開來做手動測試却不會影響到 staging 環境上的 regression CI bot，還有 staged rollout  DB migration 降低風險，更不用說還能拿來做後續的 canary release 及 A/B testing。功能開關使用情境之多，能帶來效率、彈性與降低上版風險及風暴範圍，為何不用呢？
				- #+BEGIN_QUOTE
				  使用 canary release 和 observability 來替代傳統的 Alpha、Beta、Staging 等層層關卡，可以提高效率並降低上版風險。真正做到有考慮風險意識地快速假設、上版、實驗、反饋，然後依反饋提改進計畫。
				  #+END_QUOTE
		- #### 基本定義 (Definitions)
			- 持續交付書中，特別是CI、CD 的定義對於 RD 非常重要，每一個定義背後都有其存在的理由。選擇性地採納或拒絕某些做法，一般正是導致轉型失敗的主因。
			- 這些東西其實我也花了好幾年的時間才看懂，比如說 time-boxed fixing before reverting 這一點來說，如果developer fail 了 pipeline，且 10 分鐘、15 分鐘不能 fix，你就把 commit revert 掉，那過不了兩個禮拜，你可能就被踢出了團隊。書裡寫的根本窒礙難行，但如果你從 trunk-based 的角度來看，一切就變得非常合理。那為什麼一開始書裡面不就直接講這些 practices 都是從 trunk-based 的角度來寫的呢？那也是幾年之後在一個 conference 的錄影上面看到 Jez Humble 他講因為單主幹開發是他們講過的東西裡面最具有爭議性的東西（類似 TDD 的狀況），為避免爭議，所以他們就不直接把它寫明 ...
			- 隨著時間的推移和行業巨頭的認可，大家覺得單主幹開發是否還是這麼具有爭議性，還是它已經逐漸成為軟體開發的主流趨勢呢？所以當團隊找我討論，這樣做好不好，那樣做行不行的時候，我都是拿這些 definitions 來跟大家解釋。所以 resources 或 schedule 等都可以討論，但這些 essential rules 是沒有辦法妥協的，這是要跟團隊達成的共識。 這些作法很多都是反人性的，但 DevOps 這幾年的發展已經證明這跟行業別、公司大小都無關，其實都是做得到的，重點是要去了解每一項背後所代表的意義。
		- #### Automation Strategies
			- ##### 快速反饋中的測試驅動的開發
				- 測試驅動開發必須以清晰的需求為核心，不明確的需求會導致後續的 rework，影響速度。
				  在 PBR Meeting 的產出中，每個 user story 的 Acceptance Criteria (AC) 也正是 Definition of Ready (DoR) 的一部分。每個 User Story 一般只有三、五個驗收條件，相比數十隻 test cases，developer 更願意嘗試這三到五個的自動化測試。有了 AC，developer、QA 或 AE 才能針對每一個 AC 進行自動化驗收實作討論，到底要在哪一些層級去做自動化來驗收這個驗收條件是最有效率的，這樣做才能避免所謂的 test case coverage 的duplication。而絕對不是 developer 寫自己的 UT，而 AE 負責 integration 與 end-to-end testing 的自動化，互不討論。詳見 [pipelinedriven.org](pipelinedriven.org)，雖然裡面用詞與實例化需求不同，但概念是可以相通的！
				- ==所以「關鍵實例」才是自動化測試的標的，而非 raw examples！==另外 QA 也可以根據關鍵實例去擴展為多個 manual test cases，這些 test cases 並不需要全部自動化，從關鍵實例開始，如果幾次交付後如果還是沒有信心，再補就是，能少就不要多。另外，生產線的 bug，為避免再次發生，還是需要團隊討論有沒有必要做成自動化變成 regression 的一部分。
				- 最後，你把所有的 AC 彙整後，最重要的那些案例就會是從各個角色的觀點出發的 CUJs (critical user journey)， 有了明確定義好的這些 CUJ 之後，你才能有辦法去判斷什麼是 production outage 亦或只是 production bug，那這個又會影響到後面 MTTR metric 的計算。
				- 以實力化需求為核心，串連整個開發流程的上中下游，並確保工作方法的重複性和一致性 (repeatability and consistency)，這為持續改進提供了空間。
- ### Community Driven DevOps
	- #### History, Progress & What We Learned
		- ##### Unit test and dashboards
			- 社群中的前輩已經給了許多建議，例如＂一次比一次好＂和專注 new code coverage 等，但如何排除眾議確實執行它，長久堅持下去才是困難的。Evangalist 需要去 promote 及營造這樣的環境！
		- ##### Together, Go Faster
			- Cloud native adoption
			- RUM & full tracing
		- ##### DevGov
		- ##### Platform Engineering
			- 想解決跨團隊都有的問題時或許用組織 community 的方式來處理更適合！
- ### Takeaway
	- #### You created your own problems
	- #### Trunk-based or NOT
		- 對於單主幹開發的考慮並不如培養關鍵能力重要，這些能力包括解耦代碼部署與發布、分階段推出（Canary Release）和規模化 A/B 測試以降低每次實驗的成本。
		- 所以彈指間，AE 跟 QA 就少了一半了嗎，還是全消失了？ 當然沒有，反而他們更有時間在做 Explore Testing 跟優化（optimize）整個 Pipeline 的效率。所以真的那天到來的時候，你確定你能說出一套探索測試的理論亦或是你能夠清楚的察覺到當前 Pipeline 的瓶頸在哪裡？所以你才有辦法去優化，這才是我們要花時間培養及專注的地方。當趨勢已經改變，你就應該往前看，This is the way！
	- #### Community in a Digital World
	- #### For Evangelist
		- 沒有一家公司是完美的，抱怨永遠不會結束，但很多公司卻會結束。
			- 如何幫助公司、團隊，學習到更有效率的開發方式
			- 文化沒有好壞，或許 biz driven 、注重獲利、經濟下行影響較小不用減薪裁員 (good Eng culture, flexibility)
	- #### Engineering Culture
- Your Choice