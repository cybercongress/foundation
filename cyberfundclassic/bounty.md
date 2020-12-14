# Bounty

@serejandmyself @savetheales

## Intro & Motivation
We propose to create an ongoing, gamified bounty process for an everlasting distribution of tokens (as long as the network agrees to do so) to those who create value for the network at its various stages of existence.

Initial token allocation plays a major role in the success of any project. Further, the initial allocation of standalone chains is a big challenge to the future success of an interplanetary, ecosystem of connected blockchains.

Bounties are a great way to constantly allocate tokens to the long tail of various actors that join the network at different stages of its lifetime. A big plus of such allocation, is its ability to be (a) ongoing and always attract new hands, (b) eliminate weak hands. Bounty allocations tend to be small and a selling occasion of bounty tokens on the open market will rarely influence the token price itself, hence, only those with interest in the project will keep those tokens, hence, create strong hands. And, (c) helps to attract an ongoing, native (background) marketing noise, while arousing interest in creating an incentive to do something, hence also helping retention.

There are many other pluses, but also minuses, that exist when running bounty campaigns. Minuses, mostly, revolve around manual distributions, altered judgment, lack of ongoing interest and, most importantly, the difficulty in joining the bounty.

Our proposition attempts to solve all these problems by gamifying and automatizing the bounty process. Please note, that we believe in simplicity as the killer feature for success, hence, our proposed implementation, includes stages that gradually progress to our end goal: a multilevel, gamified, automated allocation of tokens to bounty hunters.

## Vision
- Concept:
An ongoing bounty, that utilizes cyber.page, automatizes the rewards, enriches the core with cyberlinks and helps the distribution.

- Provision:
A) Working Keplr with cyber.page
B) Bounty tasks
C) Gift

- Description with a user story:
Bob finds a description of the bounty on Twitter or any bounty forum. He proceeds to cyber.page and sees our search box. Underneath it, Bob sees 1 single button, `bounty`.

Bob clicks the button, this opens a new page with a black screen and a message (an example message):

`You have found Cyber's top secret bounty mission to save the planet from centralization. To unlock and receive your gift of the Gods, please select your skill level`

Underneath there are 3 options: noobs, masters, god mode

Bob can select any of these options. The first option is the easiest. This is the primary bounty.

When Bob selects this option a new screen opens. There should be some type of welcoming message (We suggest to play on secrecy and easiness). Underneath that message there is a `scroll` with the mission (in the future these scrolls can be collected NFTs).  The scroll contains points:

1. To begin your mission, please install Keplr (link) / link to guide
2. Make a cyber address. Link to guide
3. Make a Twit / post / other easy tasks that do not require having tokens or understanding how the network works
4. Submission. A box where Bob has to input a web2 link to his twit / post / video / whatever
5. Click submit and wait for judgment from gods little helper: the superintendent computer  (on the initial stage, this will be done manually)

Behind the scenes: When Bob opens cyber.page, keplr and inputs the link and click submit, the work is submitted, uploaded to IPFS and a cyberlink with the tag `bounty - noob` is created. For this trick to work, we need to deploy a help bot. When the user submits a task, the bot with address and a fixed balance, creates a cyberlink:

```bash
cid("bounty_noob") -> cid(task.json)
```

where task.json is

```
{
   "round": "0",
   "submitting_timestamp": "2020-20-20:00:00:00",
   "level": "0",
   "address": "cyberaddress",
   "task_link": "https://tasklink.xyz"
}
```

And, a further pin the CIDs on a cluster for easy availability of the content.

After Bob submits this, a congratulation message appears and a link to his personal bounty cabinet.

All submissions are submitted to a table. Which is monitored by any existing Cyber user, which can vote if he likes the submission.

Behind the scenes: it is pretty easy to implement with an LCD query:
We need to get all cyberlinks from the help bot address, where cid_from is cid("bounty_noob"). And sort them by timestamps weekly for weekly rewards. A user poll should be implemented to vote on the best content by adding cyberlinks:

```bash
cid(task.json) -> cid("true")
```

It would be great to implement a button for easy-voting.

The rest is future design. Top 10/20/50 liked submissions can receive an automated payout end of each week.

As for the user story for masters and god mode:

This can include more progressive quests, with  ETH/Urbit gifts. More complicated tasks where a submission of a cyberlink is required. The option to include quests with gitcoin, etc

## Implementing stage 1

### Noob bounty, phase 0, MVP. Subjective judgment by a community advocate

There are 2 ways to arrive at the bounty screen. One, a direct web2 link cyber.page/bounty/noob from various outside resources (forums, twitter, telegram, etc) or the second way, by native crawling: first a user comes to cyber.page, where he sees a search box with the button `bounty` underneath it.

In both cases, the user arrives at a simple screen which has the title `bounty`, some text (i.e. `pick your destiny`) and 3 simple buttons: `noob`, `master`, `god`. The 2 latter buttons, will currently take the user to either cyber.page/bounty/master or cyber.page/bounty/god, and will have a message `The Gods are still in debate about the destiny of these players, please proceed to the noob section`, the word `noob` is a link to cyber.page/bounty/noob

Arriving at cyber/page/bounty/noob - the player arrives at a simple black screen with a scroll and some text (to be added):

The scroll consists of a few simple steps:

1) To start your journey, you should prepare your provisions in advance. Please install Keplr, the Metamask-like browser extension for Cosmos-based chains (link to Keplr). Link to usage guide

2) You will need a Cyber address to receive and to securely keep your treasures (tokens fromt he boutny). Open Kepl and create a Cyber address (An animated 15-second image/GIF of how to do this - no links)

3) Now, that your tools are prepared, simply submit your task for judgment

- A submission box and a follow-up judgment screen / table with the results

When Bob gets his account in `Cyber` and puts it in the pocket, he prepares a `web2` link for submitting (aka completed task) and want to submit a task for judgment. The workflow is:

![noob_bounty_wf](./bounty_img/noob_bounty_wf.jpg)

where task.json is

```
{
   "round_id": "<round_id>",                          // changeable round number according to the bounty program iteration
   "submitting_timestamp": "<submitting_timestamp>",  // get_time method on client side
   "level_id_": "<level_id>",                         // means noob if "0". For future development
   "address": "<cyberaddress>",                       // user's cyberaddress from the pocket
   "task_link": "<task_link>"                         // web2 link with completed task
}
```

Requirements for *cyber.page*:

- page-form with intro
- task.json generate method
- additional endpoint for POST method
- the set of error messages
- congratulation message.

Requirements for *cyber.bot*:

- Validation methods
- Lite SQL for <task_link> validation
- Signing and broadcasting methods
- Response standard

After the submission, Bob can go to the `bounty board` for checking the status of his submission. The status of the submission can be in `In review`, `Accepted and paid`, or in `Denied`:

![bounty_board](./bounty_img/bounty_board.jpg)

Tasks `In review` status can be pulled with a simple LCD query, filtered by `subject` (address of cyber.bot account) and `objectFrom` (cid("bounty_noob")).

To keep rounds and task levels separated the query mechanics can extend the keyword "bounty_noob" to the desirable, in future implementation. To avoid spam in reviewed it also possible to use `minheight` and `maxheight` filters. Height can be pulled with a timestamp from `cyberindex`.

The `resolved cid` snippet in the `Review` section:

![review_snippet](./bounty_img/review_snippet.jpg)

All buttons are muted, except the state with the judge's active address in the pocket. A judge should research the completed task and make a decision to approve or deny the task. If a judge clicks the `approve` button cyber.page should generate a transaction with two messages:

```
{
   "msg": [
      {
         "type": "cosmos-sdk/MsgSend",                // send msg with rewards
         "value": {
            "from_address": "<judge's_address>",
            "to_address": "<Bob's_address>",
            "amount": [
               {
                  "denom": "eul",
                  "amount": "<amount>"
               }
            ]
         }
      },
      {
         "type": "cyber/Link",                     // link msg to write decision to blockchain
         "value": {
            "address": "<judge's_address>",
            "links": [
               {
                  "from": "cid(task.json)",
                  "to": "cid(approve)/cid(deny)"   // cid("approve") or cid("deny") accordingly to judge's decision
               }
            ]
         }
      }
   ]
}
   
```

Thus, it is possible to get a CID from `Accepted and paid` and the 'Denied' sections, with simple LCD queries and with filters `subject` = <judge's_address> and 'objectTo' = cid("decision").

This design implies constant participation of the judge to avoid tasks accumulation. And a lot of mechanics with task linking. It would be a great idea to accumulate all the judges' decisions and generate one transaction per session.

In the next phases, task judgment will be done by community voting aka `the judgment day`.

### Economics of phase 0

To keep simplicity at the heart of the implementation, we propose to run the trial stags aka phase 0 with manual economics (at latter stages this will be moved to a governance decision).

We propose to `hard-code` the time of the tasks for phase 0 and the size of the prize pool. As a proposition, based upon Cybers previous tasks. The round should not be longer than 14 days (alas, we still need to market this) and the prize pool should be between 1 MEUL to 10 MEUL for each task.

For simplicity, the judge will need to use Keplr  (to quickly and comfortably move between tasks), which means the need to input the seed of an address into Keplr. For security purposes, we propose to this manually each new round with the proposed address serving as a proxy with a specific allocated amount. 

## Roadmap
We understand the difficulty in creating such a proposition, as it requires attention from the most busy engineering part of the core team of any project. We think that breaking our idea into gradual stages can help to oversee these challenges.

1) Concept
2) Design
3) Distribution dependency
4) Voting capabilities
5) TG notification bot
6) New levels and tasks (Gitcoin quests, on chain quests)
7) NFTs

## Reward
In the future such initiatives can be supported by cyberFund~Classic, alas, it doesn't exist as yet. Hence, we propose to support the creators of the bounty by using the community pool.

