---
layout: post
title: Risk management in IT - Calculating risks
subtitle: How do we calculate risks?
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/Risk03.jpg
share-img: /assets/img/path.jpg
tags: [IT, Risk, Management]
---

In the previous posts, we have taken a look at the defination of risks, threats and vulnerabilities. We have also gone over
the classification of risks and threats. Now, in this post, we would try to understand the different ways by which we can 
actually calculate risks. Senior managers in organizations always compare risks. Risks can
be classified into critical risks, high priority risks, medium priority
and low priority. This classification of risks allows us to prioritize
our efforts towards fixing them. Our budget for risk management
is always constrained so we need to ascertain which vulnerability
should be fixed first. Risk calculation can be qualitative or
quantitative in nature.

#### Qualitative risk management

 Qualitative risk management is used when
we cannot measure exact values. As such it is subjective in nature. 
It helps us in measuring the probability of an occurrence and its
possible impact. It is most commonly used with a risk matrix.

<img title="Risk matrix" alt="Risk matrix" src="/assets/img/RiskMatrix.png">

We can see that qualitative risk measurement is based on a lot of
subjective measurements as we do not have quantifiable values for
the same. It requires a lot of experience for someone to be able to
judge the probability and impact of a vulnerability. Let us try to
understand qualitative risk management with an example. In an
organization, employees are not allowed to take photographs
inside office premises. In order to enforce this, tamper proof
stickers are placed over the mobile phone cameras while entering
the office. Now let us try to find vulnerabilities in this system.
Someone can place a sticker over their mobile while going in,
remove it, capture images which contain sensitive information and 
try to sneak his device outside the office. In such a situation, the
guards have to remain extremely vigilant and carefully inspect
each and every mobile device when an employee is exiting the
office premises. However, this is difficult to do when lots of people
are exiting the office simultaneously. In such a situation, the
impact of this vulnerability is high, and the probability of it
happening is medium. So, we see that we have a high overall risk
based on our risk matrix and something else must be done to
rectify the situation.

#### Quantitative risk measurement

Quantitative risk measurement involves calculating the impact of a
vulnerability. In this method we use numerical values to convey
the severity of a particular risk. This value can be monetary or
even in terms of man-hours affected. It is also known as
probabilistic risk analysis as it is a numbers-based measurement
of the probability and impact of a particular risk.

A few key terms used in qualitative risk measurement are single loss expectancy
(SLE) and annual loss expectancy (ALE). Single loss expectancy is
defined as the monetary loss expected from the occurrence of a
risk on an asset. Mathematically it is defined as the product of the
asset value (AV) and the exposure factor. Exposure factor (EF) is
the subjective, potential percentage of loss to the specific asset if a
specific threat is realized. Annual loss expectancy is the product of
single loss expectancy and the annualized rate of occurrence
(ARO). Annualized rate of occurrence is used to represent the
number of times a risk is expected to occur. So, we have the
following formulas:

>SLE = AV × EF
>
>ALE = SLE × ARO

Let us try to understand this with an example of an organization.
We have many servers in this organization, let us assume that
their collective value is 100. The threat in this case can be power
outage which causes all air conditioners to shut down. This will
cause overheating and subsequently damage the servers. Let us
assume that the exposure factor in this case is 0.3. This means that
in the case where AC’s shut down due to power unavailability, 30%
of our servers will be damaged. So, the single loss expectancy can
be calculated as

>SLE = AV * EF = 100 * (0.3) = 70

In our case we assume that such a condition arises after every 5
years. So, the annualized rate of occurrence is (1 ÷ 5) = 0.2.
Thus, annual loss expectancy is

>ALE = SLE × ARO = 70 × 0.2 = 14

Thus, we have quantitively assesed that the monetary value associated with this particular risk is 14 per year.

