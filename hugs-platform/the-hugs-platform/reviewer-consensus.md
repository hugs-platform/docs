# ✅ Reviewer consensus

Reviewers are Contributors with a high Reputation Score and a proven track record in one or more areas of expertise. They review the validity of contributions before they are presented to Clients which assures the quality of contributions and maximises their value. Obviously the honesty of Reviewers is very important so we introduced Reviewer Buckets and Reviewer Consensus to enforce this.

### Reviewer Buckets

A Reviewer Bucket is a collection of contributions exposed to a Reviewer at a specific point in time. Every time a contribution is created, it is automatically added to a reviewer bucket.

![](<../../.gitbook/assets/TechnologyPaper-Reviewer Consensus.drawio (3).png>)

The bucket a contribution is assigned to is determined by the following formula where n is the number of buckets:

$$
b_{contribution} =  contribution\_hash\ mod\ n
$$

​At any time, a Reviewer can start the review process in which they can pick contributions they want to review. To ensure the integrity of the review process, the subset of contributions to which the Reviewer has access are assigned on a random basis. This prevents malicious collaboration between Reviewers and Contributors. Reviewer buckets are used to guarantee this random assignment. At a specific point in time, a Reviewer will only have access to 1 reviewer bucket, determined by the following formula where hash() is a secure hash function and block\_hash is the hash of the latest block on the blockchain:

$$
b_{reviewer} = {hash}(reviewer\_address\ |\ block\_hash )\ mod\ n
$$

Note: The reviewer bucket changes at specific intervals, which may not coincide with every new block.

### Reviewer Consensus

To guarantee the integrity of the review process, it is important to make sure that the impact of a Malicious Reviewer is limited. Hugs uses a reviewer consensus mechanism where multiple Reviewers evaluate the validity of a contribution and the majority vote of the Reviewers will determine the outcome of the contribution.

With this approach we take the assumption that the majority of Reviewers are honest. This is a valid assumption as incentive mechanisms are in place to maximise their honesty. Reviewers only receive compensation in HUGS tokens and reputation when they are part of the majority vote, while being part of the minority vote negatively impacts reputation.
