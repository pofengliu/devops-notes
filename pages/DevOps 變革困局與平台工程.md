public:: true
type:: blogpost

- ## Our Platform Team
	- ### 簡介 Intro
		- #+BEGIN_QUOTE
		  "A foundation of self-service APls, tools, services, ==knowledge and support== which are arranged as a compelling internal product. Autonomous delivery teams can make use of the platform to ==deliver product features at a higher pace==, with reduced co-ordination" by Evan Bottcher 
		  #+END_QUOTE
		  #+BEGIN_QUOTE
		  "A ==curated experience for engineers== (the customers of the platform)" by Matthew Skelton (Team Topologies) 
		  #+END_QUOTE
		  #+BEGIN_QUOTE
		  An Internal Developer Platform (IDP) is built by a platform team to ==build golden paths== and enable developer self-service. An IDP consists of many different techs and tools, glued together in a way that ==lowers cognitive load on developers without abstracting away context and underlying technologies.== Following best practices, platform teams treat their platform as a product and build it based on user research, maintain and continuously improve it.  (source: internaldeveloperplatform.org)
		  內部開發人員平台 （IDP） 由平台團隊構建，用於構建黃金路徑並實現開發人員自助服務。IDP 由許多不同的技術和工具組成，它們以一種降低開發人員認知負荷的方式粘合在一起，但開發者仍然能夠理解和掌握底層系統的細節，不會因為平台的簡化而對系統失去掌控。然後遵循最佳實踐，平台團隊將他們的平台視為產品，並根據使用者研究構建、維護和持續改進它。
		  #+END_QUOTE
		  從上面敘述，大家應該了解，==平台工程包含技術面與非技術面向的變革推動！==技術部分，就像平台工程，某種程度上也就是用大量自動化的方式在做標準化使用及鋪平道路，但這篇內容會著重在非技術部份。
		- #### Principles of platform engineering
		  * Clear mission and role
		  * Treat your platform as a product
		  * Focus on common problems
		  * Glue is valuable
		  * Don’t reinvent the wheel
		  Source [platformengineering.org](https://platformengineering.org/blog/what-is-platform-engineering)
			- 只是個通用原則但如何做、怎麼做和做什麼，每家公司都不一樣且差異很大。這些都是幾家走在前沿的公司，根據自身的經驗、需求為了更有效率解決某些問題而推導出來的一些守則 (disciplines)。然後經由某些書籍、研討會議做出更具體的結論與推廣而更廣為人知。平台工程並非全新，它是一種新興模式，旨在不僅==簡化開發人員的生活==，還通過一套精心挑選的黃金標準工具來達成這些目的。
			- DevOps, SRE 跟 Platform Engineering 這三個角色、定義與權責劃分一直是社群討論的話題！企業了解這三個領域的重疊和不重疊之處，將有助於組織在準備好時利用機會並發展，企業權責區分清楚、成立這些組織的確很好，但並不是所有企業一開始都有辦法這樣做。了解這三種角色的使命，讓角色重疊來完成任務，及早提出問題、解決問題，從失敗中學習經驗做到持續改善，才是學習這些守則的主要目的！
		- #### Higher Purposes of platform engineering
		  * Increase organization-wide efficiency and effectiveness
		  * Intentionally strive to optimize time-to-market
		  * Reduce costs across the enterprise
		  * Enable efficient governance and compliance
		  * Other cross-cutting requirements
		- 有時候，應該從更高視角來看平台工程，意思是它更需要專注在組織效率與業務價值，而非只是滿足客戶 (developer) 的需求，這點後面也會再討論。
	- ### 工作模式 Working Model
		-
		- 從目前合作模式來看，SRE 與平台工程人員交互合作機會非常多，其實很多會議兩邊人員都會互相參與。也有想過成立另一個部門包含 SRE 與 platform engineers，因為兩者都有需求打造內部平台，策略方向最好要有一定的討論與共識。
	- ### 組織與價值 Org and It's Value
		- 熟悉這些角色間差異的目的：
		          * DevOps 模型通過高質量與快速交付顯著提高了業務價值和反應能力。
		          * 平台工程和 SRE 的出現進一步增強了 DevOps 流程，解決了特定挑戰。
		          * 識別並建立對這些角色如何互補的認識，為組織在 DevOps 領域未來發展做好準備。
		- #+BEGIN_QUOTE
		  “At its core, an effective internal developer platform compartmentalizes complexity. Each person has their own little area of complexity that they are expert at dealing with, and that everyone else can safely ignore,” ~ Chris Stephenson, CTO at Humanitec “
		  一個有效的內部開發者平台的關鍵點在於能夠把複雜的問題劃分好。每個人都有自己擅長處理的部分複雜問題，而其他人則完全可以忽略這些問題。” 
		  #+END_QUOTE
- ## 平台破除 DevOps 變革困局
	- ### 平台源起
		- 從 2022 年2Q 開始，公司讓大家用不超過 20% 的時間來參與所謂的 side-project，這一改變讓整個 DevOps 的導入有了大幅度的躍進。以 Platform Engineering 的名義成立了兩個 task-forces 分別為 OnePipeline TF 與 Engineering Operations TF，前者專注於 release cycle time 的改善，後者則是對整個開發週期的透明度與開發者體驗的加強！
		- 2023 年，OnePipeline 團隊打造了 feature toggle 的內部平台與相對應的 OpenFeature SDKs，另外和還協助所有專案團隊從 Drone.io 過渡到 GH Actions。除了 pipeline 相關工具外，團隊也花了許多時間在整合許多後端的開發策略與實踐做法，避免過度地發散 (fragmentation) 影響力跨團隊支持的意願與效率。
		- 另一邊的 Engineering Operations TF 也上線了 Faros BI 內部平台，讓所有團隊都有端到端的儀表板 (dashboards) 可觀測整個開發週期的相關指標與整體開發效率的 DORA metrics！後續也加入了 SonarQube quality metrics 以及以服務 CUJ (Critical User Journey) 為主的 SLO 看板。
		- 這些內部平台其實都是花了許多時間與專案團隊坐下來對焦，想清楚如何制訂大家都能接受的指標定義以及如何無痛注入在現有的開發流程中。
		- 最後，2023 年中又成立了另一個 Backstage side-project，目的是為了解決內部知識共享與技術文件撰寫與查找的效率問題。這些問題一直都在且日趨嚴重，光是在 wiki 上面搜尋日常要遵守的開發守則與規範就令人沮喪不已。在 2023 4Q，以 Backstage 為主的解決方案也在內部的 DevOpsDays 中展示 PoC 的結果，並收到超過 95 % 開發人員的支持。但其實背後仰賴的是大家從 wiki 為主體的知識管理系統轉向以 "Documents as Code" 的思維轉變，但用了十幾年的 wiki 要轉向以 Markdown 為主的書寫習慣，談何容易？！週邊的配套措施與流程自動化工具等的開發工作也是如火如荼的在進行中。
	- ### 從改變思維進入到執行期
		- 從 2018 年開始就一直在倡導這些 DevOps Elite Culture 跟單主幹開發， 但是苦於缺乏這些 Feature toggle 的平台，還有可以監控改善效率的工具，所以變革的進展遲遲無法大步跨越，只能專注在單元測試習慣培養、自動化測試效益改善與 pipeline 穩定度等基層改變做起。直到這些所謂的 side projects 的成立， 並開發出來了這些內部開發平台才看到專案團隊顯著地開始採用這些新的開發方式，正式進入了變革執行期。
- ## 平台談產品思維
	- ### 客戶要的不一定是對的
		- 前言：產品思維談需求講求反饋，但跟一般產品一樣，客戶不見得知道自己想要的是什麼，而且內部團隊對於平台或是技術桟常常也是意見分歧。經驗是不管推出什麼樣的平台與產品，不管結果有多成功，初期總是有反對的聲音。
		- 2019年，台灣這邊決定將所有的服務搬上雲端， 那時候我建議要搬上雲端沒有問題，但是配套的observability 一定要開始一起做。所以當初就介紹了Grafana 的 Loki 讓大家開始試著用。但是幾周時間過去了，不少開發人員就反應這個  Loki 不好用，所以想回去用原本的 Elasticsearch 跟 Kibana。前期當然有介紹也溝通過了，你==想解決的是雲端可觀測性的不易，但開發人員心裡想的只如何能方便查找 log 解決眼前問題==。在當時 Grafana stacks 還有許多項目在 beta 階段，但整體方向就是往實現 O11y 在走，比起 ELK stacks 在 community 的版本並看不到這樣清楚的政策方向！如果當初不堅持，在今天我們也絕對沒有能力實踐端到端 tracing 的能力。
	- ### 專注在有需要的團隊
		- 在有人的地方總會存在一些 outlier，總會有人不同意或是各種理由跟不上轉變。平台一開始就是約定大家同意的最大公約數，設定這些規範、守則與工具鏈起初就要針對最有需求的團隊，對於那些無法馬上做到的團隊給予多一些彈性與時間，但對於新成立的專案就一定得遵守了，原因會在規範性價值章節再細談。開始一件事總是不容易，但原則還是在你能夠影響的範圍內先做出影響力。
		- ![flexible_schedule.webp](../assets/flexible_schedule_1719996020045_0.webp)
		  [source: medium.com/@ZaradarTR](https://medium.com/@ZaradarTR/internal-developer-platforms-team-topologies-and-the-journey-beyond-one-size-fits-all-solutions-7fa18de1394a)
	- ### 解決問題上而非擴張
		- 既然開發了平台，當然會想要推廣到全公司。但在初期整合度及 DevEX 不夠好情況下，貿然要求大規模採用，很容易就耗盡使用者的耐心。專注解決問題及其它配套措施都是可以優先考慮的，目的是能讓==問題在客戶所花成本最少、對現有流程影響最小的情況下得到解決==。Airbnb 的 CEO Brian Chesky 說的「Do things that don’t scale.」（做那些不具規模化的事情），就是這個意思，初期應該專注在**重視用戶體驗**並與之**建立深度連接**。
- ## 文化信仰才是平台需求的根源！
	- ### 它改變平台的全貌 (Landscape)
		- 這些平台或 side-projects 不是突然被雷打中就有的靈感，一樣是來自為了實踐 DevOps 的 [[CAPABILITIES TO DRIVE IMPROVEMENT]] 。很重要的是，當你==腦中看不見，眼睛也看不見==。所以心中想做的平台、工具程式的選用等等其實都被腦中想完成的目標無形地影響著！從上面 O11y 的堅持，到下面要講的 Docs As Code 的文化以及管理面視覺化其實都是其來有自。
		- #+BEGIN_QUOTE
		  不懂為何而戰，改變將難以持久!
		  #+END_QUOTE
		- 大圖
	- ### 改變才是平台的終點
		- 前言：這些非 CI/CD 類的平台，最終目的就是加速或完成文化（行為）的變革。
		- #### Docs As Code (Knowledge sharing)
		- #### DevOps Elite Culture
			- 這邊就不再重複了，請看 [[Community Driven DevOps]]。
		- #### Engineering Operations BI for Agile
			- Agile and value driven development 以及 SRE 談的 SLO & Error budget 來決定開發應該專注穩定性還是應該要衝刺新功能，或是 DORA 要求的 elite culture，這些沒有一個有效且公開的觀測系統，那將會是難以推動的改變。一個能觀看整個 SDLC 的 BI 系統，將為組織帶來開放及有效的管理風格。
			- #+BEGIN_QUOTE
			  “If you can't measure it, you can't manage it.” - Peter Drucker
			  #+END_QUOTE
		- 所有 IDP 都是有意為之，都是為了追求 DevOps, Agile 所闡述原則的實踐。例如當我們在規劃這些 dashboards 時，心裡想的不是 KPI 而是如何觀察 fast feedback loop & quality. 另外平台的客戶是開發人員，不去深入了解 Agile, DevOps 也是說不過去的事 ...
- ## 規範性價值 (Canonicity is Enabler)
	- ### 不是有問題才需要改變
		- 前言：在主持 DevOps TF 期間就一直努力敦促各 domain 下面成立各自的 community，希望透過社群來制定這些所謂的規範性的事項來避免技術桟的碎片化以增加跨團隊合作的效率。
		- DevEx 並不會自己變好，所有改變都是刻意為之，比如成立公會組織，標準化流程工具、減低碎片化，降低認知負荷增加跨團隊支援的意願。又比如推行單主幹開發，減低分支模式與環境複雜度，讓 CI/CD 自動化減少人為干預。又比如 Docs As Code ...一切為了 DevEx 的改變都是有意為之，困難且緩慢。困難原因因為這些行為都是違反人性的，也是所要熵減的過程。
	- ### 熵增定律與公會組織
		- 熵增定律的形成條件及負熵想法：
		  * 封閉系統：開放內部系統，以跨組織的集體智慧加速規範決策與執行
		  * 無外力量做功：設置管道引入新技術與工法，維持正能量流動
		- 不光是熵增，帕金森定律 (Parkinson's Law) 也說明了在封閉組織中最後都會頃向約迂腐與沒效率，所以想在公司內成立社群來推動改變，以集體意識的方式去規範標準化及限縮技術棧的碎片化。==Guild 為一個開放的組織但共同制訂規範限縮無序發展就是用來對抗熵增的策略，而平台工程的規範性價值也正說明了這件事。所以也可以說平台工程也正是工程組織在減熵的過程中所找到的一種最佳實踐方式。==
		-
- ## Who is the Boss
	- ### 改變需要槓桿
		- IDP & DevEx 看似服務 developers，但是==人都不喜歡改變更不喜歡被改變==。只有你的老闆（付你薪水、打你考績）的人，才有槓桿可以撬動這塊轉變的大石頭。如何說服上層可視化是重點，因為大家都知道無法觀測的東西是難以管理的！要有意識地推動持續改善，需管理層支持，並將目標量化納入OKR，可視化是關鍵。老闆了解持續改善和提升效率的重要性，也知道變革伴隨風險，如果無法有效觀察和量化項目，草率納入組織目標，也難以獲得大多數人的認同。
	- ### 可視化是支撐點 (Visualization is Leverage)
		- DORA dashboard 20+ 個  --> 業界標準  -> Faros --> middleware, oss plugins --> e2e lifecycle
		  Ticket 切小, not just frontend, backend, class, features but MVP -> Beta, production, Dog fooding, beta user testing
		  WIP 不只是 Kanban board 上停留在 DOING
		- 可視化的好處
		  * 看到改變與數字，體現與計算價值
		  * 無法管理無法衡量事務，缺乏槓桿
		  * 找出洞見及改善方向
	- ### 用洞見來提出改善計劃 (Insights & Improvement Plan)
		- 一個易用的 BI 系統，不但能讓你往下追到更深層次的肇因，也能從過程中產生洞見。最近的例子：
		- 現況：交付頻率已經開始改善
		- 題目：Copilot 已經導入超過半年，如何明確指出它對工程效率帶來多少貢獻？
		- 想法：Copilot 對加速程式撰寫體感可說是非常明顯的！但是當可運用時間變多，人反而越會拖延，效率愈低 (Parkinson's Law)。無法排除心裡因素造成的影響，這些數字很難完全體現在每兩週能完成的 sprint points 或是 DORA metrics 上面。另外如果一開始便設定好交付週期，人就頃向於拖延！那是不是改為 Kanban 的 pull-based model 加上 DevOps elite 的 release on-demand，才是能夠排除拖延症帶來的影響呢？如果是，那接下來應該可以怎麼做？！
- ## 心態調適與轉變 (Survive, Strive & Thrive)
	- ### Platform is like the poem
		- 記得讓客戶所花成本最少的情況下解決問題搭配週邊的配套措施，太過強勢與急躁反而可能帶來更多抗拒。
	- ### Maturity model
		- 一開始都是從自願發起參與，然後專注在解決問題而擴展。期間想想如何找到外在推動與內部拉力（胡蘿蔔與棍子），最後雖然平台價值才是重點，但也別忘了使用槓桿！
- ## 平台工具發展趨勢
	- No code / low code / XaC (everything as code)
		- Ex: Faros, n8n
	- Open-sources, especially plugins ecosystem
		- Ex: Backstage
	- One-stop portal
	- Orchestrate and application modeling
- ## 總結與心得 Summary
	- 我覺得 DevOps 這些事情，其實你都不做，你還是可以兩週交付一次。 但是你的產品的質量、效率與穩定度就比較難以控制。 所以不管是DevOps、SRE、還是Platform Engineer ，它都是以專職的角度來提高企業價值和反應能力。
	- 最後給平台團隊的一句話：
	  #+BEGIN_QUOTE
	  帶著團隊去做那些你不做就不會發生的事，而不是做那些其它團隊都在做的事，這才是參與重要工作的最佳機會！
	  #+END_QUOTE
-