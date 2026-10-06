# final — The Unknown

**Team:** BB-023
**Queries used:** 56 / budget

## What we concluded

The system generally returns an APPROVE decision with a high clearance score.
In our experiments, the score remained very high (around 0.95–0.96) for many
different input combinations.

We found that `container_count` did not have a noticeable effect in our
comparison: changing it from 60 to 50 produced the same score of 0.9598 and
the same APPROVE decision.

## How we got there

We ran multiple queries while changing individual input fields and comparing
the resulting score and decision. We used the query history to identify cases
where only one value changed between experiments.

For example, queries 55 and 56 had the same score (0.9598) and APPROVE decision
even though `container_count` changed from 60 to 50.

We also tested different values for fields such as declared value,
discrepancy ratio, port, prior shipments, and container count.

## What we ruled out

We ruled out the idea that every individual input change necessarily causes a
large change in the final score. Several changes produced the same or nearly
the same result.

We also observed that some combinations can produce a DECLINE decision, so the
system is not simply approving every shipment.

## What we are still unsure about

We have not completely determined the exact underlying rule or weighting of
all input fields. More targeted experiments would be needed to establish
which combinations are responsible for the remaining changes in score and
decision.
