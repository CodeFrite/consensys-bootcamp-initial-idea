# blockchain-developer-bootcamp-final-project
Smart Contract Audit &amp; Intermediate Fund Raising Project

## Problematic

Investing in a crypto project in an early stage or even more before its commercial launch, can turn out to be a risky decision.

As stated in Wikipedia, "Due to the lack of regulation and enforcement of securities law, ICOs have been the vehicle for scams and fraud. Fewer than half of all ICOs survive four months after the offering,[8] while almost half of ICOs sold in 2017 failed by February 2018" (https://en.wikipedia.org/wiki/Initial_coin_offering).

In order to mitigate the risks, many approaches exist: reading the white paper, making sure to understand the problematic that it solves, checking the project team curriculum, checking the project's roadmap, making sure that they delivered on time previous announced milestones, and many more.

One of the first line of defense would be to *simply* review the smart contract code. Indeed, numerous projects have turned out to be complete scams, not allowing the investors to sell their coins, allowing the owner to pause the contract, changing the transaction fees or other critical parameters. Unfortunately, this is not in the reach of everyone even more today with projects presenting a complex tokenometric.

For this reason, being able to rely on the expertize of qualified reviewer would allow an investor to

*Note to myself:*
*- make the distinction between project who solve problems inherent to the blockchain (layer 2, new blockchains, cross-chain interoperability, ...) for which the seriousness is more easily established and relatively simple projects like ERC20 tokens that consists on a single .sol file. Should I simply limit the discussion to ERC20 tokens?*
*- I should clearly say what is Out Of Scope regarding the projects that could hypothetically be audited here*
*- Citing Wikipedia is ok, but I think I can find a more furnished article*

## WorkFlow

## Key Features

*Core Team:*
+ Admin view on all audit submissions
+ Admin view on all InCO [optional]
+ Publish Smart contract audit results
+ Review InterCO and accept / refuse [optional]
+ Evaluate launched projects [optional]
+ Release coins to the investors addresses [optional]
+ Return coins to the investors addresses [optional]

*Client:*
- User account creation
- Project submission
- Audit review
- Submit code fixes
- Accept audit results
- Create InterCO [optional]

*Investors:*
- View audits results (filter on under review, under correction, finalized)
- Invest in a project
- Check status of a project on which money was put

## Technologies

- Solidity (Smart Contract)
- Truffle (Smart Contract Testing)
- Vue.js (Front-End)
- Flask/NodeJS (API)
- LavaMoat (Front-End js security) [optional]
- FileCoin (Files version control on the BlockChain) [optional]

## Progress

I'll be sharing the work progress using of course this github repository by committing frequently code and updating this readme file. During the analysis phase though, I will most probably be reflecting using a Miro Board, which has a public visibility : https://miro.com/app/board/o9J_lwU-JWc=/

## Disclaimer

- Sorry for posting the link to my project this late. I joined the bootcamp last Tuesday and even if I knew before joining that I would be noted on a project, I just realised that I had to submit a link with the project idea yesterday morning (just finished chapter 1 of the course)
- When I joigned the bootcamp, I wanted to find a project idea that could make a bridge between the blockchain and AI (I am currently following a course on Udacity about deep reinforcement learning. Link:https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893). I haven't given up this idea so I do not exclude changing the project subject before the end of this month.
- I am a very optimistic person but please be ensured that I am not (totally) delusional. Chosing a solidity code audit project when I am still learning the basics is just a way for me to allow myself to concentrate on a field that I am very keen to deepen : security (tester background). Even if no real audit will be produced, I will try my best to populate the front-end with a mockup audits that will humbly list a range of possible defaults and code fix suggestions that a solidity code may face. Please, see this as an idea that I would be excited to see and for which I will most probably only solve the infrastructure aspect (front-end basic capabilities, general workflow, communication between parties, communication with the smart contract) and not really the core business which is the actual audit of smart contracts.
