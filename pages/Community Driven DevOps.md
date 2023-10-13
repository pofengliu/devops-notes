public:: true
type:: blogpost

- DevOpsDays Taipei 2023 - Community Driven DevOps 內容筆記
- ## DevOps Evangelist 經驗分享
	- ### About Me & LINE TW & Demo
	- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_2.jpg)
	- ### DevOps Evangelist & Faiths
		- #### 信仰來源
			- ##### 解決身邊沒效率的問題
				- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_6.jpg)
				- 曾經有一位 QA 過來問我，為什麼我前天在 production測了這個 hotfix 今天在 integration 測了同一個 Hotfix，下一週的 Release Testing Plan，這個 Hotfix 又要再測一次？當然我就畫了圖解釋給大家聽，在這個Hotfix進來的時候，integration Branch 跟 future Branch 的 codebase 都已經不一樣了，所以我們當然要再 verify 一次。（這些做測試計畫的技巧都是當時 PM 或 release manager 所需要具備的知識）。當時在我講完這句話後心裡就有一個念頭，如果測試這件事是這麼的 tedious 那怎麼可能 Google、微軟的那些測試大神到五、六十歲還會這麼有興致的在講這些議題？國外的軟體測試我想應該不是這樣子的。當然這位 QA 幾年後也就轉職 RD... 可見 tedious work 浪費資源而且留不住有創意的人，在 branches 間不斷地 re-testing，一般的 QA 其實根本也沒空練習與實作探索性測試。
			- ##### 解決身邊不合理的流程
				- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_7.jpg)
				- 曾經我帶領一個QA團隊在做一個跨國的金融專案，工程師大部分都是在國外，那也因為我們的自動化測試做得很好所以一開始是 24 個人做這個案字，到最後剩 13 個人但卻可以同時做三個案子，因為自動化做完之後其實我們每次的 regression 都很快，所以有能力再接更多的案子。不過這邊的代價是，像我每天早上一到公司我就得花一到兩個小時檢查為何昨天的pipeline 會跑失敗，那當然可能的原因是 developer check-in了新的程式的代碼或者是他的代碼造成了其他的 bug 跟 side effect，當然也有可能是自動化測試的 flaky 問題。這樣其實也做了幾年直到有一天我突然想到為什麼我每天都要花時間在這些事情上面，難道這些時間不能拿來做更好的利用嗎？回頭來看這件事情是 Developer 的錯嗎？他不過就只是提交了他的代碼而已。那這件事情是AE的錯嗎，也不是呀，因為我們的 automation，如果 single thread 在跑需要跑個6 個小時左右吧，你就可以知道那個裡面有數百數千隻的 integration 測試，當然我們是把它做得很好，只要沒有新的代碼進來它不管跑幾次結果都是99%、100% ，所以我們是很有自信的，所以這也不是 AE 的錯。總歸來講就是這個 process 本身就是這麼不合理，為什麼一件事情就得拆成兩階段去完成呢？！所以這些數百支數千支的 test automations， developer 會來看嗎？就我做了這麼多的案子，從來沒有而且Developer 做自己的 unit test，AE 做自己的Integration 跟 End-to-End，這些都帶來非常多的 test coverage 的重複，也因為各做各的，其實就算 pipeline 跑完了也沒有人能夠了解全部的測試內容，更不用說對於 pipeline 結果能夠帶來什麼樣的信心，在上版前還是需要搭配許多的手動測試！
			- ==當然這些不合理、沒有效率的事情在今天要講的單主幹開發裡面，它幾乎不存在！==當我理解了背後的原理，我就決定要去推廣所這謂 DevOps 的 Elite culture。
			- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_8.jpg)
			  ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_9.jpg)
			- 不過現實是... 不管是 Accelerate 這本書的內容或是 DevOps Handbooks 裡面講的所謂三步工法，當你對所有 RD 講完之後，大家都是毫無反應。之於那所謂單主幹開發更是覺得這種上不了檯面的雕蟲小技怎麼會拿出來講呢？Gitflow 的 feature branch 才是王道吧!
		- #### 軟體公司的數字化轉型?
			- ##### 快速交付是種「能力」！
				- 能力跟競爭力還是有差別的！==競爭力大部分能夠用錢來提升，但能力確很難培養。==比如說公司為提升競爭力，可以花錢導入JIR、買 CRM 等軟體，想要做好版控提升品質，有錢的去買GitHub，經費比較少的用 GitLab，但是不管你買了哪一個，想要做到快速交付，那根本就是兩碼事，快的能力是要部門間完美的配合及磨練出來的。
				- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_11.jpg)一般 RD 眼前幾個 sprints 就夠燒腦，誰有心情看 4  年後的事... 就算努力改變去練習上面所提到的這些能力，對於下個 sprint、年底考績、明年團隊人數的成長有幫助嗎？ 我想難有直接幫助... 如果是這樣當下你所講的無法跟大家的短、中期利益都沒法對齊，那你又期盼對方能給你什麼樣的回饋呢？！
				- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_12.jpg){:height 378, :width 657}
				  ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_13.jpg)對於企業來說呢，哈佛商業評論裡面講到，過去的50年美國最大的五百家企業，S&P500，平均企業壽命已經從 60 年降到 18 年，wow 這個差距之大讓後續有更多針對這課題的討論。DevOps 的 Enterprise Journal 裡面也提及==業務的敏捷是生存的基本，先行者優勢已經被速度快的所取代。然後商業上的大規模轉型呢得要依賴科技，基本上之後的公司大概都是軟體公司， 能夠快速交付就變成企業生存的關鍵！所以難怪說軟體的相關指標超過上百個都不為過，那為何 DORA 偏偏挑這四個，且其中三個還是跟速度、頻率有關係，可見交付速度的重要性！！==
				- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_14.jpg)這張圖是State Report 裡面交付效率的一個分群，所以你看到 2021 年 elite 加上 high 的比例已經超過 66%，那如果大家都是高分那就沒什麼意思了，所以在 2022 年的時候他就把 elite 等級拿掉並把 high 的要求拉高。所以原本能夠做到 weekly release 就是 high 的等級，到了2022年你如果還要維持在 high 那勢必得做到 release on demand 就是所謂的 "multiple deploys per Day"。
				  所以不進則退，==但我想要講的是 release on-demand 在實作上、思維、策略跟技巧跟其它的等級都不一樣！這也是為何一直想強調 elite culture 後面的道理的！==
				- ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_15.jpg)
				  #+BEGIN_QUOTE
				  Sally realized that it wasn’t necessary for the software to be perfect and bug free at the moment that it was released to the readers. “The risk of not getting software to our users is greater”  [ref: what-really-happens-when-you-deliver-software-quickly](video https://www.youtube.com/watch?v=L-WOJmCcA9g)
				  #+END_QUOTE 
				  ![](https://speakerd.s3.amazonaws.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_16.jpg)這邊常會有誤會，舉例來說，葉問葉師傅可以一次打 20 個，這是一個苦練出來的能力，但不代表他每天都要出去打 20 個，難道要打到沒朋友？對企業來講也是一樣，我能夠做到 multiple release a day，那我可以根據商業的需求改成 daily、weekly 或是 monthly release 都是沒問題的。但反過來說，哪天當 biz 醒過來，要求你做到更快速地交付時，你有辦法嗎？其實是很難的，因為這是要長時間培養的能力！==所以不要抱怨 planner 要求的功能做出來都沒有人用，你的 pipeline 能提供簡單、快速、低成本的 A/B testing 來讓他可以快速去驗證他的假設嗎？==
				- 這邊我們看到 SpaceX 每天可以在 production release 一萬七千多次，他們試錯成本這麼高每個火箭造價動輒上百萬美元，有時上面還坐了人呢！他們講 DevOps 跟 continuous testing ！另外，特斯拉也是用 SCRUM、講 Agile，可是你看人家生產線上的 sprint 可是以五個小時為單位，有些工作站的節點甚至是以三個小時為一個 sprint。所以當我在聽這些 podcast 或conference 的時候，==你會發現他們談的 DevOps, Agile 跟 Scrum 裡面的核心原理跟做法與我們學到的完全一模一樣，但差別在於他們能夠將這些原理極致化，強調極短的 release cycle！==
				- 能縮短 cycle time 代表去除了中間不必要的浪費！
			- ##### 具備「快」的「能力」
				- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_17.jpg)
				  ==想要快，最好、最安全的起手勢就是 Trunk-based 加上 feature toggling。這邊講最安全是因為你在網路上可以找到太多的成功案例、教材、工法與工具==。單主幹開發細節在這就不多說，但一個功能開關（feature toggle）可以讓你把未完成的代碼藏起來讓你每天可以至少跟主幹合併一次做到真正的 CI。另外同一個開關可以讓 QA 打開來做手動測試却不會影響到同一個環境上的 regression CI bot，還能 staged rollout  DB migration 確認沒有效能問題，更不用說拿來做後續的 canary release 及 A/B testing。功能開關使用情境之多，能帶來效率、彈性與降低上版風險及風暴範圍，為何不用呢？
				  對了，==圖上面的 DORA tags，說的是這些 toggling practices 能為四項的 DORA metrics 帶來哪些改善！（所導入的任何做法最終還是要能反應到這些效率指標，對吧！ ）==
				- #+BEGIN_QUOTE
				  使用 canary release 和 observability 所建構出的安全網來替代傳統的 Alpha、Beta、Staging 等層層關卡，可提高效率並降低上版風險。真正做到有考慮風險意識地快速假設、上版、實驗、反饋，然後依反饋提改進計畫。
				  #+END_QUOTE
		- #### 基本定義 (Definitions)
			- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_18.jpg)
			- 持續交付書中，特別是CI、CD 的定義對於 RD 非常重要，每一個定義背後都有其存在的理由。選擇性地採納或拒絕某些做法，一般正是導致轉型失敗的主因。所以當團隊找我討論，這樣做好不好，那樣做行不行的時候，我都是拿這些 definitions 來跟大家解釋。因此 resources 或 schedule 等因素都有空間可以討論，但這些 essential rules 是沒有辦法妥協的，這是要跟團隊達成的共識。 這些作法很多都是反人性的，但 DevOps 這幾年的發展已經證明這跟行業別、公司大小都無關，其實都是做得到的，重點是要去了解每一項背後所代表的意義。
			- 這些東西其實我也花了好幾年的時間才看懂，比如說 time-boxed fixing before reverting 這一點來說，如果developer fail 了 pipeline，且 10 分鐘、15 分鐘不能 fix，你就把 commit revert 掉，那過不了兩個禮拜，你可能就被踢出了團隊。書裡寫的根本窒礙難行，但如果你從 trunk-based 的角度來看，一切就變得非常合理。那為什麼一開始書裡面不就直接講這些 practices 都是從 trunk-based 的角度來寫的呢？那也是幾年之後在一個 conference 的錄影上面看到 Jez Humble 他講因為單主幹開發是他們講過的東西裡面最具有爭議性的東西（類似 TDD 的狀況），為避免爭議，所以他們就不直接把它寫明 ...
			- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_19.jpg)
			  隨著時間的推移和行業巨頭的認可，大家覺得單主幹開發是否還是這麼具有爭議性，還是它已經逐漸成為軟體開發的主流趨勢呢？
		- #### Automation Strategies
			- ##### 快速反饋中的測試驅動的開發
				- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_20.jpg)
					-
				- ==測試驅動開發必須以清晰的需求為核心，不明確的需求會導致後續的 rework，影響速度。==
				  在 PBR Meeting 的產出中，每個 user story 的 Acceptance Criteria (AC) 也正是 Definition of Ready (DoR) 的一部分。每個 User Story 一般只有三、五個驗收條件，相比數十隻 test cases，developer 更願意嘗試這三到五個的自動化測試。有了 AC，developer、QA 或 AE 才能針對每一個 AC 進行自動化驗收實作討論，到底要在哪一些層級去做自動化來驗收這個驗收條件是最有效率的，這樣做才能避免所謂的 test coverage 的 duplication。而絕對不是 developer 寫自己的 UT，而 AE 負責 integration 與 end-to-end testing 的自動化，互不討論。詳見 [pipelinedriven.org](pipelinedriven.org)，雖然裡面用詞與實例化需求不同，但概念是可以相通的！
				- ==所以「關鍵實例」才是自動化測試的標的，而非 raw examples！==另外 QA 也可以根據關鍵實例去擴展為多個 manual test cases，這些 test cases 並不需要全部自動化，從關鍵實例開始，如果幾次交付後如果還是沒有信心，再補就是，能少就不要多。另外，生產線的 bug，為避免再次發生，還是需要團隊討論有沒有必要做成自動化變成 regression 的一部分。
				- 最後，你把所有的 AC 彙整後，最重要的那些案例就會是從各個角色的觀點出發的 CUJs (critical user journey)， 有了明確定義好的這些 CUJ 之後，你才能有辦法去判斷什麼是 production outage 亦或只是 production bug，那這個又會影響到後面 MTTR metric 的計算。
				- 以實力化需求為核心，串連整個開發流程的上中下游，並確保工作方法的重複性和一致性 (repeatability and consistency)，這為持續改進提供了空間。詳見：[[實例化需求 (Specification by Example)]]
				- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_21.jpg)
				  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_22.jpg)
				  這邊想要強調的是基於兩週交付一次，二週內讓所有 regression tests 變成綠色的，跟每次的 commit 都要在 PR check 內跑完大部份的 regressions 而且一天要跑 25次、50次，還要跑超快（因為要 reduce cycle-time）且 non-flaky，所用的心態、策略、工具與作法完全不一樣。更多詳見[[什麼是自動化測試的標的？]]
				  * 在 PR 內跑完大部份 regression：Test isolations, Mock, Stub, TestContainers
				  * 要能 non-flaky 且能平行跑：TestContext
				  * Test in MicroServices: Consumer Driven Contract Testing
				  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_23.jpg)
				  在中庸等級上所做的練習對 elite culture 完全沒幫助，且都要幾年後才會發現，這些已經習慣的作法，反而會變成轉變時心裡的負擔！例如心態上難以跨越的門檻：以前要跑完幾千隻的 automation 才有信心上版，現在 auto 只跑 CUJ?
- ### Community Driven DevOps
	- #### History, Progress & What We Learned
		- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_24.jpg)
		  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_25.jpg)
		- ##### Unit test and dashboards
			- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_26.jpg)
			  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_27.jpg)
			  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_28.jpg)
			  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_29.jpg)
			  這個是現在跟8個月前，所有 projects coverage screenshots 的圖，我把兩張疊在一起。每個圓圈包含這 project 內所有的 repositories，其中一些 bot, utils, backend CMS 等那些你不會花太多時間寫測試的 repo，所以平均下來 coverage 會比較低，大部份重要商業邏輯的元件，coverage rate 大於80、90 以上的非常多。但是所要關注的是在沒有要求及格分數的狀況下且經過了幾年之後，大家還是能自動自發做到持續改善，這是相當不容易的，也代表 [自主團隊文化] autonomous team culture 的成型~~
			- 社群中的前輩已經給了許多的建議，例如＂一次比一次好＂和專注 new code coverage 等，但如何排除眾議確實執行它，長久堅持下去才是困難的。Evangalist 需要去 promote 及營造這樣的環境！
		- ##### Together, Go Faster
			- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_30.jpg)
			- DevOps + SRE + Development team play will together, but communication, mindset changes and prepare workshops took a lot of time!!
			- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_31.jpg)
			- DevOps state report 裡面也提到只有 10% 的團隊能夠完整實踐 SRE 相關的指導方案。這裡面的原因不外乎 SRE 只用了 infra team 的思維而缺乏持續溝通來改變工程團隊的想法進而加強改變的意願。導入可觀測性就是一個明顯的例子，大部份 RD 想要的只是能方便查詢 log 來推斷問題原因，但 DevOps 想的是如何用可觀測性來降低 MTTR 進而減少生產線救火及爆炸範圍進而降低 unplanned work 比例等。
		- ##### DevGov
			- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_32.jpg)
			  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_33.jpg)
		- ##### Platform Engineering
			- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_34.jpg)
			  ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_35.jpg)
- ### Takeaway
	- #### You created your own problems
		- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_37.jpg)
	- #### Trunk-based or NOT
		- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_38.jpg)
		  現在的我覺得對於是否實施單主幹開發與否的考量並不如培養關鍵能力重要，這些能力包括解耦代碼部署與發布、分階段推出（Canary Release）和規模化 A/B 測試以降低每次實驗的成本。但是這些方法論中的基本定義却還是非常重要，能避免大家走錯路或把路走歪了！
		- 只要能夠熟練這些關鍵能力，那是不是主幹開發也只不過是彈指之間的距離罷了。那彈指之間，AE 跟 QA 就少了一半了嗎，還是全消失了？ 當然沒有，反而他們更有時間在做 Explore Testing 跟優化（optimize）整個 Pipeline 的效率。所以真的那天到來的時候，你確定你能說出一套探索測試的理論亦或是你能夠清楚地察覺到當前 Pipeline 的瓶頸在哪裡，所以你才有辦法去優化它嗎？這才是我們要花時間培養及專注的地方。當趨勢已經改變，你就應該往前看，This is the way！
	- #### Community in a Digital World
		- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_39.jpg)
	- #### For Evangelist
		- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_40.jpg)
		  沒有一家公司是完美的，抱怨永遠不會結束，但很多公司卻會結束。
			- 如何幫助公司、團隊，學習到更有效率的開發方式。
			- Amazon 跟 Netflix 兩家公司文化差異這麼大，但 DevOps 都做得超棒。
	- #### Engineering Culture
		- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_41.jpg)
		- Merging hell, defect retesting, alpha, beta 等等都是不斷在消耗團隊的各種 resources …
- Your Choice
	- ![](https://files.speakerdeck.com/presentations/8e24732701ff45af870421e9abd29e4a/slide_42.jpg)
	- 上世紀的畫講馬太福音的故事：自古以來成功之路就是崎嶇、困難與無聊的，中庸之路通常是寬廣、平坦、歡樂的！再讓我選擇一次，希望時間不是花在那些 branch merging, hotfix retesting 上面。這世代的 talent 值得花在更有創意的地方！
	- 對於 DevOps evangelist，從單元測試到可觀測性、或是自動化縮短 lead-time 到組織效率都是你的守備範圍，如果操這麼多心只是想要做到中庸等級，那不如就當個 RD 就好！簡報重點是希望大家能把精力轉移到 DevOps elite culture 所擘劃的那樣一個情境，慢慢地花時間在「快 」所需要的基礎打好上面，例如單元測試、需求探索方法等等。