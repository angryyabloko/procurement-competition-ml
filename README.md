# procurement-competition-ml

Analysis of competition in public procurement using machine learning.

Coursework for the "Programming Technologies" course, NUST MISIS.

## Motivation

Public procurement costs less when more suppliers compete for each contract.
Studies of Danish and Finnish tenders show that each additional bid lowers the contract price,
with the largest effect when a second bidder joins a single-bid tender
([Aagaard & Linaa, 2024](https://kfst.dk/media/bmgjjy3w/the-impact-of-competition-for-public-contracts-on-public-finances.pdf);
[Ijäs, 2026](https://www.kkv.fi/uploads/sites/2/2026-01-working-papers-are-we-paying-too-much-the-cost-of-low-competition-in-public-procurement.pdf)).
A review of international evidence reports price reductions of 10–20% from a few additional bidders
([Adam et al., 2021](https://www.govtransparency.eu/wp-content/uploads/2021/09/Adam-et-al_Evidence-paper_procurement-competition_210902_formatted_2.pdf)).

## Russian context

Russian data point in the same direction. In a study of contracts of a large public organization,
price reductions grew from about 1% with one admitted bid to about 24% with three or more
([Yakovlev, Demidova & Balaeva](https://institutiones.com/general/2034-prichiny-snizheniya-cen-na-torgax-i-problemy-ispolneniya-goskontraktov.html)).

Low competition is widespread. According to the Accounts Chamber, about 60% of procurement by value
in 2023 was declared failed, and in more than 80% of these cases only one supplier applied
([news report](https://forum-goszakaz.ru/news/2025/01/27/schetnaya-palata-fiksiruet-rost-nesostoyavshihsya-zakupok/)).

Under Federal Law 44-FZ, a single-bid procurement is declared failed, but the contract is still
concluded with the only bidder (Art. 52 and Art. 93). The price cannot exceed the starting maximum
contract price or the bidder's own offer (Art. 93, Part 5). In an electronic auction with one bid,
no bidding takes place, so the contract is concluded at the starting maximum price.
This makes the link between competition and price especially direct.

## Limitations

More competition is not always better.
A lower price at the award stage can be partly lost later through renegotiation, cost overruns and delays
([Decarolis, 2014](https://ideas.repec.org/a/aea/aejapp/v6y2014i1p108-32.html);
[Carril et al., 2026](https://www.aeaweb.org/doi/10.1257/aer.20221345)).
For this reason, the project does not treat a high number of bidders as a goal in itself.

Price reductions are measured against the starting maximum price set by the customer.
If this price is set too high or too low, the measured savings are distorted.

## Goal

The project looks for procurements with unusually low competition.
A model predicts how many bids a procurement should attract, using only information available
before the bidding deadline: product category, starting price, procurement method, deadlines,
requirements for bidders and legal restrictions (such as small-business-only procurements).
Procurements that received far fewer bids than expected are flagged for closer review.

A flag is not proof of a violation. It marks a procurement that is worth a closer look.
