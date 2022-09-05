---
description: Safeguarding data quality in the blockchain
---

# The Hugs Reviewer Network

### Introduction

The objective of the Hugs Reviewer Network is to increase the quality of off-chain data by introducing an on-chain Reviewer Network. To accomplish this, it uses a decentralized review process where $HUGS tokens and reputation are used as collateral, incentivizing the Reviewer to execute a valuable Review. Reviews are typically manual interactions verifying the correctness of the data. Consumers are benefitting from high quality Reviewed Data and reward Contributors and Reviewers for their efforts.

### Architectural Overview

The Hugs Reviewer Network uses a blockchain network to track the data across the flow and link it to the required collateral. Initially, Solana will be used because of its low transaction fees, but the goal is to eventually integrate different blockchain solutions as well and allow cross-chain interactions.

![The Hugs Reviewer Network](<../../.gitbook/assets/Schermafbeelding 2022-06-07 om 09.16.05.png>)

The following stakeholders are involved:

* **Contributors -**  Make contributions or provide data input to the Hugs Reviewer network. These contributions are represented as Review Requests.
* **Reviewers -** Process Review Requests and produce Reviewed data which is made available to Consumers. Reviewers have to provide a specific amount of $HUGS as collateral for every review.
* **Consumers -** Consumers reward Contributors and Reviewers to get access to the Reviewed Data.
* **Curators -** Signal interesting Review Opportunities or Consumers by staking $HUGS tokens. Curators are rewarded with a percentage of the reviewer rewards.
* **Delegators -** Allocate $HUGS tokens to reviewers, allowing them to process more review volumes. Delegators are rewarded with a percentage of the reviewer rewards.

The typical flow for these stakeholders is indicated on the overview above and goes as follows:

1. **Review Opportunities -**  Represents a specific type of contribution with corresponding limitations and guidelines. Depending on the type of Review opportunity and signalling of Curators, Reviewers can assess if they want to take up these opportunities or pass on them.\
   Example: Contributions updating a wiki with the latest information.
2. **Review Proposal -** Created by a Reviewer if they want to accept the specific Review Opportunity and start reviewing the corresponding Review Requests. The Review Proposal contains the price of the produced review data and the share that the contributors, curators and delegators will receive. This mechanism creates an open market where multiple Reviewers can create proposals and contributors can select the most beneficial proposal for them to make their contribution.&#x20;
3. **Review Request -** A contributor can make a specific Review Request in which they agree with the terms of the Review Proposal and request a Review. This allows the reviewer to execute the collateralized review process (see below) and results in a Review.
4. **Review -** Once reviewed, the Review will be added to a Review Marketplace where consumers can pay the price of the produced review and get access to the underlying data.
5. **Rewards -** When the Consumer accepts the review they received, the rewards as indicated by the Review Proposal are paid out to the necessary participants. These participants can be Contributors, Reviewers, Curators and Delegators. More about rewards and the $HUGS token usage can be found below.

### Collateralized Review Process

The Hugs Reviewer Network (HRN) uses a collateralized review process to incentivize honest and trustworthy reviews. After a Reviewer receives a request on his Review Proposal he will be able to start the process by staking the amount of $HUGS tokens as indicated in the proposal. These tokens will be locked until the consumer accepts the review or a timeout occurs. (Tokens can also be unlocked after a consumer unsuccessfully asks for a refund. More on this later) Next,  consumers have the option to access the Review by locking the same amount of tokens in an escrow account, which gives them access to the content. When the consumer confirms the Review has been executed correctly, the escrow account is used as payment for the Reviewer and the Contributor.

![Successfull Collateralized Review Process](<../../.gitbook/assets/image (7).png>)

But what happens if the review did not happen as it should have happened and the Consumer wants to dispute the Review in the hope he can retrieve the amount locked in the escrow account?

In this case, the review will go to a dispute committee, existing of a set of reviewers with a high reputation. The dispute committee will execute the same collateralized review process and the majority consensus determines the outcome of the dispute. If the consumer wins the dispute, his escrow account is released and the reviewer collateral is divided among the committee. Alternatively, if the consumer loses the dispute, the escrow account is used instead to reward the committee.

![](<../../.gitbook/assets/Hugs Reviewer Network.png>)

### Hugs Token Usage

The Hugs Reviewer Network uses $HUGS tokens for a wide range of utilities each contributing to a unique mechanism.

#### $HUGS for curators

Curators choosing to stake tokens signal to the network that the corresponding Review Opportunity or Consumer has a great potential of generating rewards in the future. This way they act as prospecting agents giving valuable info to the rest of the network. The curator receives a share for his staked tokens which will generate rewards every time it is involved in a successful review. To maximize its yield, curators are incentivised to do research and stake tokens on promising and high-quality Review Opportunities and Consumers. Curators signalling rather unknown leads (with a lower amount of curator stake), will provide the curator with a higher share of the reviewer rewards, leading to a competition of finding the new kid on the block with the highest potential.

#### $HUGS for delegators

By default, a Reviewer is only allowed to review a low amount of contributions to prevent low-quality participants to have a high impact on the network. This is where delegation comes into play. Anyone can delegate $HUGS tokens to their favourite reviewer allowing them to process a higher volume of reviews. Delegators are rewarded with a percentage of the reviewer rewards, which gives them the incentive to choose reliable and successful reviewers. The Hugs delegation mechanism gives tremendous insight into the capacity and trustworthiness of a reviewer and can be a determining factor, next to reputation, when choosing to interact with it.

#### $HUGS as review collateral

Every reviewer has to stake an amount of $HUGS as review collateral. When the a review is successfully disputed by a consumer, a part of this collateral will be slashed and used as rewards for the dispute committee. This mechanism gives a direct economic incentive for a reviewer to provide high-quality reviews. Additional there is also an indirect incentive as slashing also has a negative impact on delegators.&#x20;
