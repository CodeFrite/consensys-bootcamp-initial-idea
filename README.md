# blockchain-developer-bootcamp-final-project
Smart Contract Audit Platform &amp; Audited Coin Offering (ACO)
 
## Problematic
 
Investing in a crypto project in an early stage or even more before its commercial launch can turn out to be a risky decision.
 
As stated in Wikipedia,
> "Due to the lack of regulation and enforcement of securities law, ICOs have been the vehicle for scams and fraud. Fewer than half of all ICOs survive four months after the offering,[8] while almost half of ICOs sold in 2017 failed by February 2018" (https://en.wikipedia.org/wiki/Initial_coin_offering).
 
To mitigate the risks, many approaches exist: reading the project white paper, making sure to understand the problematic that it solves, checking the project team curriculum, checking the project roadmap, making sure that they delivered on time previously announced milestones and many more.
 
One of the first lines of defense would be to *simply* review the smart contract code. Indeed, numerous projects have turned out to be complete scams, not allowing the investors to sell their coins, granting the contract owner special powers like pausing the contract, changing the transaction fees, or other critical parameters. These intentional forgeries can quite easily be spotted by reading the contract. Unfortunately, this is not in the reach of everyone, even more today with projects presenting a complex tokenometric.
 
For this reason, being able to rely on the expertise of qualified reviewers would allow an investor to more safely invest in projects which use case is appealing to him. One will argue that such audit companies already exist. Indeed, we could for example name Diligence, Certik, Open Zeppelin, and many more.
 
The first value proposition here would be to allow the project team to work in close collaboration with the certification company in an earlier stage, ideally throughout the development process of the contract. This would allow:
- The project team to get guidance and early feedback from the certification company and integrate it ASAP to lessen the rework
- The certification company to assess more easily that the code presented to them, and delivered in an atomic fashion, is only solving the announced problematic
- To show the dedication and the seriousness of the project team, as well as its capacity of delivering quality code throughout the development of the project
 
This process could happen for small projects even before any ICO has been launched. This could be an enormous opportunity for the public to adhere to the project very early in the project life and catalyze its interest in it.
 
The second value proposition would be to allow the public to support the project by participating in the audit fees. In counterpart, they would secure a fair amount of tokens even before any ICO is launched. This would once again tend to prove the seriousness of the team: while offering some of their coins, they would only be able to get support for launching their projects. No free money up to this point.
 
To make it riskless to the public, the audit company would observe the following workflow.
 
## WorkFlow
 
The crypto project team would:
- Create a profile on the auditor website using Metamask
- Submit a project and give some information about it: one technical description for the audit company and another commercial description for the potential investors
- Chose an audit plan among: continuous cooperation, continuous guidance, final dynamic review, final static review, final dynamic and static review
- Ask for a pricing offer (estimated by the smart contract for a very low gas cost)
- Accept or not the pricing offer and pay it via Metamask
 
The auditor will then:
- Accept or reject the project to prefilter non-serious initiative (manual review)
- If the project is rejected, the contract will automatically return the funds to the payer account, minus the transaction gas fees
 
If the project is accepted by the auditor, the smart contract will then:
- Create an entry for the project (save the data in the smart contract state / Filecoin)
 
The front-end could then list the project on the website as an ongoing project.
 
Depending on the selected audit plan, the project team will submit the address of its smart contract once finished or will collaborate with the auditor and commit a few times the address of its contract for the auditor to review the code.
 
Each time the code has been audited, the auditor will publish on the blockchain the problems that need to be addressed.
 
At this point, the project team will then either:
- Fix the major issues by a due date
- Or accept the audit results ASIS
 
If all the major issues have been fixed, the auditor will set the project in a particular state that will allow the project team to launch its ACO = Audited Coin Offering.
 
At this point, the public will be able to support the project team by investing in the audit fees.
 
When the project is finally deployed to the main net, the auditor will perform a last check to ensure that the code corresponds exactly to the one audited:
- If it is not the case, the funds invested will be returned to the investors
- The same will occur if the project team is unable to deliver its project to the main net before an agreed date
 
On the contrary, if the project team respects its commitment:
- The audit fees will be reimbursed to the project team up to the level invested by the investors
- The project tokens will be delivered to the investors
- The auditor will keep the money from the investors
 
## Features & User Stories

The following user stories will be used to derive a series of test cases written in js and solidity. These tests cases will be used as part of the Test Driven Development approach: Every time I want to develop a new feature, I begin by writing the corresponding test case, then I code the solution and I stop as soon as the test case passes. Then, if an undesirable behaviour is observed, it means that either the test case and/or the user story itself is incorrect.

### 👪 Unregistered User

A user is considered as unregistered if his MetaMask addresses are not linked to any role in one of the contracts (Roles: contract owner / auditor / team / investor).

📁 `F-UU-00: Unregistered User: General Layout`
+ CONTEXT: *As an unregistered user, When I navigate to the Home Page (/), ...*
    + 📝 US-00: *... Then I should always see the header on top (10%) and the page content below (90%) [front-end|mvp]*
    + 📝 US-01: *... And I scroll the page content, Then the header should remain fixed, always on top and visible [front-end|mvp]*
    + 📝 US-02: *... And I am not connected to a wallet (no web3 injected), Then I should see in the header the button 'Connect Wallet' [front-end|mvp]*
    + 📝 US-03: *... And I am connected to a wallet (no web3 injected), Then I should see in the content the buttons 'Register a Team' and 'Become an investor' [front-end|mvp]*

📁 `F-UU-01: Unregistered User: Navigation`
+ 📝 US-00: *As an unregistered user, When I am not connected to a wallet (no web3 injected) And I navigate to any Route other than Home Page (/), Then I should be redirected to the Home Page (/) [front-end|mvp]*

### 👔 Contract Owner

📁 `F-CO-02: Contract Owner: Contracts Migration` [[Link: Sequence Diagram]](https://sequencediagram.org/index.html#initialData=C4S2BsFMAIDEFoDCB5eAGATALmog9gHbABOAhgMbDTIDuBkxOAsiAOZmiEBQXARnsGB4AtgAdSxUORDiiAZy7jJIabODs8AV1HQAxODYALdcUgBPaACpL0ACrFNAM0dQuFIcWp0GXSAQAmihJSMqREGtp6BqzG7JB+VpYAQuB45ADWiIakIATWQcqqYVQAosCGDJCawr4BPLT0xPDwAHxlFabVOP6QoqlmDAB0PX14ZgAUtpCkwnIANNCk-v6mcnIAlG6UIABupMAw7ZXVXA0MzW3lx8Ldvf1DI-3jAArEeABWkJTzi8urG6dvE1WkdOjdoI8xg87mNxgBBTT+MA-JYrSBrTZnYGXDpVcGQgbEYYwiYASQIO3RHhRf3RAKxF1BeNuo0JxNZ8IAIsgaWiMVweu5dvtDlcwVx1kA)
+ CONTEXT: *As a contract owner, When I migrate the contracts on the blockchain, Then I should be the owner of ...*
    + 📝 US-00: *... the contract "Teams" [smart-contract|mvp]*
    + 📝 US-01: *... the contract "Projects" [smart-contract|mvp]*
    + 📝 US-02: *... the contract "Audits" [smart-contract|mvp]*
    + 📝 US-03: *... the contract "ADOs" [smart-contract|optional]*

📁 `F-CO-03: Contract Owner: Contracts Ownership` [[Link: Sequence Diagram]](https://sequencediagram.org/index.html#initialData=C4S2BsFMAIDEFoDCB5eAGAzALmog9gHbABOAhgMbDTIDuBkxO+RZlAztXQ2wBYgAOAKABGeYMDwBbfqWKhyA0kTaDBMuSAUyiAc2J4Arv2gBicCB09geyAE9oAKgdx9ReAFECAE0EUJxTnpiQUhvNVl5RV19I1NzS2tiSFDHBwAhcDxyAGtEHlIQAidwjS0lKgAVSFJJFXVI7SoABX0AK0h2Eoby6ABBAy8wOojNKKpegBFkFVCvaFVaIPh4AD4qmrYcNkhgRYYAClIvLyS2NgBKX0oQADdSYBh12sEntlXX6BwQNj3iQ+PThcXtVassVr8cElgAZiAQOP8TpAzpcvNVrncHtBXgsuMQwS08O12Fsdr8EYDLn5bvcYASicAVHSOgzVkz2J9oN8yUdEcjBGyWasIdAoTC4dByUigaiqRjaW1mSpBL8wf1BgySbtcZK+bKaX0BkNBGqhqsTRrOT9tTyKcbDYLwbjITsxfCbVKUWjQHKDeqlSqzVNNtBtlqgjqgXrMZNpsag4Hpl8reH3XyY28hU6RS7YW6AR7BDL0fr00A)
+ CONTEXT: *As a contract owner, I should be the only one able to ...*
    + 📝 US-00: *... set the contract owner of the contract 'Teams' to a new address [smart-contract|mvp]*
    + 📝 US-01: *... set the contract owner of the contract 'Projects' to a new address [smart-contract|mvp]*
    + 📝 US-02: *... set the contract owner of the contract 'Audits' to a new address [smart-contract|mvp]*
    + 📝 US-03: *... set the contract owner of the contract 'ADOs' to a new address [smart-contract|optional]*

📁 `F-CO-04: Contract Owner: Authenticate & Revoke Auditors` [[Link: Sequence Diagram]](https://sequencediagram.org/index.html#initialData=C4S2BsFMAIDEFoDCB5eAGALALmog9gHbABOAhgMbDTIDuBkxOAggK7AAWkRI5pwMAMmgAlSADc8AaxisAJmDzEAzgCgARnmDA8AWwAOpYqHIgDRVQaM9TpIgHNieFnugBicCDvtgDyAE9oACpAuEciFQptYmo6BhUuWRVLYxt7R2c3Dy8fYkguIMCAIXA8cklEdlIQAmCkwxSzKjkwC3rrRugAUQ4GSBYdeIJElQB6EehWDkUQAC8YehpoUhZ5KKXZWVylVVp6Ynh4AD5m4CUcZaniWcgTxQAKUg2tpQBKCMoQMT4ZFZaVE6URwBOBASl2DDuOiUdgAdI9NpBtm8AUDfqcQUpbsQHk9Ea9-mjAYdDt1OLl+jhIDowBM2OxpnMsTiEdsADTw57IwkHQ7gxjQXLAFjEAhKZnPdm4tkaPDgN6ySCRT7fWmrVSjcaiCTSJZoxTrFk7WL7VFqnC5bU3PXYjl4t5Kr78VV-FHHQkYvmQ6FwqX413A6Cgpm2pEEtVHEk9ck6SnUqhaqRW1b3ENKSWGrnho5882QIUisWp9OclQKh0qgFAA)
+ CONTEXT: *As a contract owner, I should be the only one able to ...*
    + 📝 US-01: *... authenticate a new auditor address [smart-contract|mvp]*
    + 📝 US-02: *... revoke an existing auditor address [smart-contract|mvp]*

📁 `F-CO-05: Contract Owner: Auditors Privileges` [[Link: Sequence Diagram]](https://sequencediagram.org/index.html#initialData=C4S2BsFMAIDEFoDCB5eAGArALmog9gHbABOAhgMbDTIDuBkxOAggK4AmYexAztAArEQANxBQA5pG4AoKQCM8wYHgC2AB1LFQ5EOqLT1mkNt3AxxPC1XQAxOBBiAFqeKQAntABUHuOaJSKSsTUdAxSkARsUgZaOqREZhZWtvZOZpDhnh4AQuB45ADWiA6kIAReURoxJtCsHMD6lUaxRNAAosAODJAsymERMgD0A9DKpK4A6oLAkMiy3AxCpKCEUrT0xPDwAHy1YNw4oxNTM3MLSyCEABSkbGwu3NwANPJ44ACU-pTCSzC79VJ-bjbQE4EDcNYMS7KbhiAB0Nzukm4H0BwPYe1B3D+XChMPht3uyKkj2gYOxxGuBKRKPR9W2W3anRcPRwkGUYFwxQIEgAsmNJmATvNiItlgRKYiHo8EYTHq82I96DQaXUgdsIYxoC5gCxiARuBLZfLFZBlVI2JAAt9pjVadIpEMRmMmORyJBVMB8MQXF8VhrNjs7Qdna73Z6uD6xYakc88K8PlbRb87QC7WjVZiNbi4TLqanVemMaSsbScdCc1SHiq9vTGV0WdA2RyinFeSG3R6vZGLuLc1K+09jUrq3T1SFNdrdfro1Kh6aPhbEz9barBsNDgAlH5-VbjgMgp2uLfTP4zp4vd6fUBJld7fM1wMZ4tZ8v4yVE1GPotk0sU18DkcgS2BkOnrZRWXZKgW25SA+SPbdaTPaVK0HcAFWHe9Ry2DUcEnPUDQHOU0JNM1Fy+G9ATXQ8AGVgEqJgUF3dZ9yDGi6M0BjkCQi8E3I5dKM-A8wRfPEAMwoChJLOoy1ElDANrUDmXAxtIM5VtYLGWj6JQJDCLnM1UTHdZcMgHV8KQ-SF0tPibUoh11zGDdICgUh5k4gAVPB8nCaR-ULepgyPZzLTclBPO86dCJ4q9rWTVdBNY4Tx2zN9CXkr8AuLckUrEz8QKZbplKbKCuTbIKXNC5Bwp83SUKI9D53EgMcK1UypwIurLPNazr34u0gA)
+ CONTEXT: *As a contract owner, I should be the only one able to modify ...*
    + 📝 US-00: *... an auditor "mayWriteObservation" flag [smart-contract|mvp]*
    + 📝 US-01: *... an auditor "mayAcceptCorrection" flag [smart-contract|mvp]*
    + 📝 US-02: *... an auditor "mayRateAudit" flag [smart-contract|mvp]*
    + 📝 US-03: *... an auditor "mayStartACO" flag [smart-contract|optional]*
    + 📝 US-04: *... an auditor "mayReleaseACOTokens" flag [smart-contract|optional]*
    + 📝 US-05: *... an auditor "mayCloseACO" flag [smart-contract|optional]*

📁 `F-CO-06: Contract Owner: Registration Fees` [[Link: Sequence Diagram]](https://sequencediagram.org/index.html#initialData=C4S2BsFMAIHkHcB2kBO0Bc0DKljQGKSQDOAUKQA4CGKoAxiNYsAOYoD2ArhdAMTggWAC1YpIAT2gAqKQQ7MAtAFFEAE1JU6wdmgTIUpSGso16jKszZce-QSLZFE0qQCFw7OgGsAwkKohEGRNaEAYmPAAVSCoAWzJqELCLPAAFDgArSC1401DzZmgAQU5VMBzE-LwASUQANxJtFHKzcOgAEULYZrzWpWAhVEhOGMNjUj1UBQUAPijY4kxiXDmY7zEqUHZEQhIACk4A4ABKDS0QWo2YFbJrmevMEGIJlF2qVVUxYmIT2+npvoGYmGmEgMTA0F8FhYkBWa2im22RGIr3en2IABp2OBVOjkPAftE4lNps9MGJgJwUIhkVicXiTqpomcLsAroSyAAjdjAbQxBItZJkcZISYzNLsTLZRa4cWS4BwjYgLY7ZEHZgnTSgFkwWVZYBkXXZMUZPULaCPZ4oj4kb6kQ36mb-fqDYHQUHgyGIaH2hUIlVWtGY7G4yD4u0mo0zUnQcmU6m7WkhsOMzXnS7Qe1C57E4qlfXS4C5sC+pWIvZq46nLXpov60i14gzBsPJ4il5va1fE4Nx0Al0xEFgvCe6G1kvKpEBm1Bumh7slMrE6Oxqk04P00gp5k1hd14X6Yk1erERpmpbAI8NHTjsuqw4a7es6CXk86Mgv08zD9vluWjtok5vyaXtnSBAc3SHCE-C9SAgJvf1-2nRMNyAxsozbMlcDjNdZ2TJlqyfVDyGzGYOi6AsyPgycKwfAiYDIsgGNIzozQtNspy7UgmL+PswMHD1oOhSj1j9SdEK+GckxOJj0P0TCKVXBN1znTd8LTJ8GKAA)
+ CONTEXT: *As a contract owner, I should be the only one able to modify ...*
    + 📝 US-00: *... the team registration fees [smart-contract|mvp]*
    + 📝 US-01: *... the project registration fees [smart-contract|mvp]*
    + 📝 US-02: *... the audit registration fees [smart-contract|mvp]*
    + 📝 US-03: *... the aco registration fees [smart-contract|optional]*
    + 📝 US-04: *... the investor registration fees [smart-contract|mvp]*

📁 `F-CO-07: Contract Owner: Login`
+ 📝 US-00: *As a contract owner, When I am not already logged (no web3 provider) And I click on "Connect Wallet", Then I should see in the header my profile set to "Contract Owner" [front-end|mvp]*

### 👷 Audit Team

📁 `F-AT-00: Audit Team: Login [mvp]`
+ CONTEXT: *As an auditor, When I am not already logged in (no web3 provider), And I click on the "Connect Wallet" button, ...*
    + 📝 US-00: *... Then I should be redirected to the auditor DashBoard (/AuditorDashboard) [front-end|mvp]*
    + 📝 US-01: *... Then I should not see in the content the buttons "Register a Team" and "Become an investor" [front-end|mvp]*

📁 `F-AT-01: Audit Team: Dashboard - Header [mvp]`
+ CONTEXT: *As an auditor, When I am in my Dashboard (/AuditDashboard), ...*
    + 📝 US-01: *... Then I should see in the header my profile set as auditor*
    + 📝 US-02: *... Then I should see in the header my wallet address*
    + 📝 US-03: *... Then I should see in the header all my auditor privileges*
    + 📝 US-04: *... Then I should see in the content all the active audits*

📁 `F-AT-01: Audit Team: Dashboard - Audits [mvp]`
📁 `F-AT-01: Audit Team: Dashboard - ACO [mvp]`

+ F-AT-01-US-01: As an **admin**, when I navigate to the admin DashBoard (/AdminDashBoard), I want to **have a view on all the registered teams** [front-end|mvp]
+ F-AT-01-US-02: As an **admin**, when I click on a team, I want to **all their related projects and related audits** [front-end|mvp]
+ F-AT-01-US-03: As an **admin**, I want to **have a view on all teams** so that I can **browse their projects and related audits** [front-end|mvp]

+ Feature F-AT-02: 
    + F-AT-02-As an **admin**, I want to **have a view on all projects** so that I can **interact with them** [mvp]
    + 

+ Feature F-AT-03: As an **admin**, I want to **have a view on all audit submissions** so that i can **interact with them** [mvp]
+ Feature F-AT-04: As an **admin**, I want to **have a view on all ACOs** so that I can **manage their lifecycle** [optional]
+ Feature F-AT-05: As an **admin**, I want to **be able to publish mart contract audit results** [mvp]
+ Review ACO and accept / refuse [optional]
+ Evaluate launched projects [optional]
+ Release coins to the investors addresses [optional]
+ Return coins to the investors addresses [optional]
 
### 🔧 Project Team
[Sequence Diagram](https://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUCcD2ArSBjY0AqkCGBbaALmgGF49gZds98AoegeiegEENF4BnegYmgAxJADtgAWgCiIgCb0ADrnig0IRWIDmSAK7zofcCA0ALYFsgBPaACprQ0ROkyb1+rk7xaBBCnTB6kLKMAgBC7gDWUkGKyiCq6mY6egZGpgBG4NowttAh4Iho4aTGuCAiLgpKKmq4YtAAsogiGogAIiEBQfy5+YXFpSKVsfG1iYi6+oYmiZCBLj0FRSVlFTHVCV74vGtxNXWSwMaQFNoMgXLd5JQwOATQK6RNwPDu-rf4PqgY4uIAfO-cEhoCi4KjvAAUaQsVG4AGYAEzQErcYwASmgigsuAykDcGBAADdQTc6LwAX8ASRMZAZNJxiZwVsNAA6ImZSCogA0924ACVIBoQNwqBQZIzuCzuOdjpzkWj6OTfr8DkcTvgSJB8GAyCCwXRwbgZDIKNxuNyoTCEUjcCjUQrST9-nRPn4SBRgNp4CJuODtGVMFQCABJGR2mR4fFEqibXjdADKuAJJLuZQAZoh7uVGs02h13i7vr9sy12iRuInIO9WpBgKVwD67cXcxTnUgvsA3TXPeVwcL4GUNNAKGguDIQ6igA)
- AS A Project Team, WHEN I navigate to my  dashboard "/" [mvp]
- Project submission [mvp]
- Audit review [mvp]
- Submit code fixes/new contract address on testnet [mvp]
- Accept audit results ASIS [mvp]
- Create InterCO [optional]
 
### 📈 Investors
- View audits results (filter on under review, under correction, finalized) [mvp]
- Invest in a project [optional]
- Check the status of a project on which money was invested [optional]

### 💀 Hacker


## Technologies
 
- Solidity (Smart Contract)
- Truffle (testing / unbox react)
- React / Bootstrap (Front-End)
- NodeJS (API)
- FileCoin (Project source code version control on the BlockChain) [optional] ... otherwise simple hash of the contract + storage online
 
## Progress
 
I'll be sharing the work progress using of course this GitHub repository by committing frequently code and updating this readme file. During the analysis phase though, I will most probably be working first using a Miro Board, which has public visibility: https://miro.com/app/board/o9J_lwU-JWc=/
 
## Disclaimer
 
- When I joined the Bootcamp, I wanted to find a project idea that could make a bridge between the blockchain and AI (I am currently following a course on Udacity about deep reinforcement learning. Link:https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893). I haven't given up on this idea so I do not exclude changing the project subject before the end of this month.
- I am a very optimistic person but please be ensured that I am not (totally) delusional. Choosing a solidity code audit project when I am still learning the basics is just a way for me to allow myself to concentrate on a field that I am very keen to deepen: security (tester background). Even if no real audit will be produced, I will try my best to populate the front-end with examples of defaults and code fixes suggestions that a solidity code may contain. I will most probably only solve the infrastructure aspect (front-end basic capabilities, general workflow, communication between parties, communication with the smart contract) and not the core business which is the actual audit of smart contracts.
- Please note that after writing this draft, I feel like this is a lot to do if I consider that I still have to go over the course material. Therefore, I have tagged the strict minimal key features with [mvp] and the nice to have features with [optional]. The MVP would be to audit code and make it visible to the public + basic back and forth between the project team and the auditor + making sure the contract deployed on the main net is the one that was audited
- Sorry for posting the link to my project this late. I joined the Bootcamp this Tuesday and even if I knew before joining that I would be noted on a project, I just realized that I had to submit a link with the project idea yesterday morning (just finished chapter 1 of the course)
 
*Notes to myself ... but you can read it :)*
- [ ] Make the distinction between projects who solve problems inherent to the blockchain (layer 2, new blockchains, cross-chain interoperability, ...) for which the seriousness is more easily established and relatively simple projects like ERC20 tokens that consist of a single .sol file. Should I simply limit the discussion to ERC20 tokens?
- [ ] I should clearly say what is Out Of Scope regarding the projects that could hypothetically be audited here
- [ ] Citing Wikipedia is ok, but I think I can find a more furnished article
- [ ] Find a nice name for my project
- [ ] Add some workflow diagram to make the info easier to follow
- [ ] Add some formatting to this readme
- [ ] Add a table of content
- [ ] Decide whether I will be explaining the code in this readme or on a separate blog/wiki
- [ ] It seems to be a lot to develop. I should simplify the problem
- [ ] How can I handle the tokens that I will receive from the project teams? Is it even possible considering the different types of addresses (BEP2, BEP20,...) I will have a lot of different tokens in my wallet.
- [ ] Who will pay for the shipping of the coins? The investors?
- [ ] There is a possibility of connivance between the auditor and the project team. I should either make it obvious, mitigate it or find a way to simply suppress it
- [ ] I should make sure that everything is feasible technically + before the deadline
- [ ] Proofreading: a lot of typos!
- [ ] Explain why I need a blockchain to solve this use case: make progress in the audit rating transparent to the public + show publicly attempts to sneak malicious code
