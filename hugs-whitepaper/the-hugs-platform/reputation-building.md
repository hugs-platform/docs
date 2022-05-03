# ⭐ Reputation Building

To provide Clients with unbiased information, it is important for the entire Hugs ecosystem that the quality of the contributions is safeguarded. Reputation Scoring plays a crucial role in this. This will help us to eliminate spam, faulty, and low-quality contributions.

When a new user joins, they automatically start as either a Contributor or a Client. They both start with a neutral Reputation Score.

### Contributor Reputation Building

* Contributors can obtain a more specialised status (i.e., Reviewer and/or Affiliate). To achieve this, they need to make a certain number of qualitative contributions that got accepted by one or multiple Reviewers.
* A built-up reputation score can tumble back down in case the Contributor delivers bad quality. The impact of a rejected contribution will be higher compared to the impact of an accepted one. This leads to downward pressure on the Contributor's Reputation Score. Contributors with a low Reputation Score will eventually be ignored by the platform.

### Client Reputation Building

* Clients receive a Reputation Score to avoid them trying to game the system. An example of gaming the system as a Client could be: rejecting issues on purpose in order to save costs, for example.
* Rejected issues by Clients are always checked by Reviewers. The outcome of these checks has an impact on the Reputation Score of the Client, but it can also reflect back on the Reputation Score of the initial Contributor and Reviewers.

The following diagram illustrates the normal flow of an accepted contribution:

![Hugs Reputation Building](../../.gitbook/assets/hugs\_issue\_flow02.png)

### Calculating Reputation Scores

The reputation score for Contributors and Clients is a weighted sum of the corresponding **Quantity Score (Rn)** and **Quality Score (Rq)**.

$$
R = wR_n + (1-w)R_q
$$

As the name indicates, the **Quantity Score** is based on the number of contributions by a user. Depending on the role of the user this has a slightly different meaning.&#x20;

* Contributors/Reviewers: Amount of reviewed contributions they are involved in&#x20;
* Clients: Amount of contributions they provided feedback for&#x20;

As we want to keep track of a continuous quantity score while users are contributing, the elapsed time between contributions is used as a metric. This elapsed time is the exact same metric as the number of contributions, but the lower its average value, the higher the quantity score should be.&#x20;

For the initial contribution, the maximum elapsed time Tmax is used to make sure a new user has to build up his reputation. Additionally, when the elapsed time exceeds Tmax, a timeout occurs and the counting starts from 0 again.&#x20;

$$
T_0 = T_{max} \\
0<T_i \leq T_{max}
$$

Because the elapsed time between 2 contributions can vary significantly, we take the exponential moving average (EMA) of this value for new elapsedTime (Ti) values. The formula is given below where the value p determines the amount of history to take into account in the EMA.​

$$
k=\frac{2}{p+1} \\
EMA(T_i) = kT_{i}+(1-k)EMA(T_{i-1})
$$

Before this value can be used as a reputation score we want it to be bounded between 0 and 1. To achieve this we use the following formula:

$$
R_n = 1 - \frac{EMA(T_i)}{T_{max}}
$$

This approach allows the quantity score to be updated in real-time on each contribution of a user.

The **Quality Score** is based on the quality of contributions from the specific user. Depending on the role of the user, this has a slightly different meaning.&#x20;

* Contributors: Quality score is based on the feedback of Reviewers and Clients.
* Reviewer: Quality score is based on the [reviewer consensus](reviewer-consensus.md) and the feedback of the Client.&#x20;
  * If the reviewer consensus agrees with the Reviewer this gives a positive quality score and vice versa.&#x20;
  * If the client feedback corresponds with the reviewer feedback this gives a positive quality score and vice versa.&#x20;
* Client: Based on the comparison between client feedback and reviewer consensus.&#x20;
  * If the client feedback corresponds to the reviewer consensus, this gives a positive quality score and vice versa.&#x20;

The Quality Score is calculated using an Exponential Moving Average, similar to the Quantity Score. The EMA is based on the values Fi Î {0,1} which indicate negative and positive quality scores for the scenario’s described above. As the values Fi are already between 0 and 1, the Quality Score is defined by:&#x20;

$$
R_q = EMA(F_i)
$$
