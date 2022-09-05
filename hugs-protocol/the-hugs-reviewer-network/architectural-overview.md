---
description: The stakeholders and data flows in the Hugs Reviewer Network
---

# Architectural Overview

### The Data Review Cycle

The Hugs Reviewer Network uses a blockchain network to track the data across the flow and link it to the required collateral. Initially, Solana will be used because of its low transaction fees, but the goal is to eventually integrate different blockchain solutions as well and allow cross-chain interactions.

![The Hugs Reviewer Network](<../../.gitbook/assets/Schermafbeelding 2022-06-07 om 09.16.05.png>)

### Stakeholders

* **Contributors -**  Make contributions or provide data input to the Hugs Reviewer network. These contributions are represented as Review Requests.
* **Reviewers -** Process Review Requests and produce Reviewed data which is made available to Consumers. Reviewers have to provide a specific amount of $HUGS as collateral for every review.
* **Consumers -** Consumers reward Contributors and Reviewers to get access to the Reviewed Data.
* **Curators -** Signal interesting Review Opportunities or Consumers by staking $HUGS tokens. Curators are rewarded with a percentage of the reviewer rewards.
* **Delegators -** Allocate $HUGS tokens to reviewers, allowing them to process more review volumes. Delegators are rewarded with a percentage of the reviewer rewards.

### Data Flows

The typical flow for these stakeholders is indicated on the overview above and goes as follows:

1. **Review Opportunities -**  Represents a specific type of contribution with corresponding limitations and guidelines. Depending on the type of Review opportunity and signalling of Curators, Reviewers can assess if they want to take up these opportunities or pass on them.\
   Example: Contributions updating a wiki with the latest information.
2. **Review Proposal -** Created by a Reviewer if they want to accept the specific Review Opportunity and start reviewing the corresponding Review Requests. The Review Proposal contains the price of the produced review data and the share that the contributors, curators and delegators will receive. This mechanism creates an open market where multiple Reviewers can create proposals and contributors can select the most beneficial proposal for them to make their contribution.&#x20;
3. **Review Request -** A contributor can make a specific Review Request in which they agree with the terms of the Review Proposal and request a Review. This allows the reviewer to execute the collateralised review process (see below) and results in a Review.
4. **Review -** Once reviewed, the Review will be added to a Review Marketplace where consumers can pay the price of the produced review and get access to the underlying data.
5. **Rewards -** When the Consumer accepts the review they received, the rewards as indicated by the Review Proposal are paid out to the necessary participants. These participants can be Contributors, Reviewers, Curators and Delegators. More about rewards and the $HUGS token usage can be found below.
