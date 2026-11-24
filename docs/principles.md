# Principles

This file defines the words in the README sentence, regarding the exposure claim, in the order the sentence needs them.

## System

The system is the CI/CD pipeline named in the README. It is written in Terraform and runs on AWS.

Terraform describes the configuration. An AWS account is where that configuration can be applied. The account is not the system.

The system admits one configuration. That configuration is the master record of the assets the system holds and the interactions the system admits. Public exposure is a fact about such a configuration.

## Internet

The internet is a party. The internet is not the system. Public exposure uses this party and no other party.

## Asset

An asset is an object the configuration can hold. A load balancer is an asset. A party is not an asset, so the internet is not an asset.

## Configuration

The configuration is the one complete record the system admits. It holds the assets of the system and their properties, and hence admits the interactions of the system. Both belong to this same record.

An interaction is a pair of one initiating party and one asset. A reply stays in the interaction it answers, with the same initiating party and the same asset. A reply does not add a pair.

The configuration holds an asset when the asset is in that record. The configuration admits an interaction when the pair is in that record. Carrying an interaction out can show that the record admits it. The carrying out is not the admission.

## Reach

The internet reaches an asset in the configuration if and only if both of these are true.

- The configuration holds the asset.
- The configuration admits an interaction whose initiating party is the internet and whose asset is that asset.

## Public exposure

A system is publicly exposed if and only if the internet reaches some asset in the configuration the system admits.

The system has zero public exposure if and only if it is not publicly exposed.

## Open and accepted

An interaction is open when the configuration admits it. The initiating party has opened it. The asset may accept or refuse.

An interaction is accepted when the asset agrees. Agreement is a reply inside an interaction that is already open.

Public exposure uses the open interaction whose initiating party is the internet and whose asset the configuration holds. That is reach. Acceptance is not required. A refusal does not remove the admitted interaction, so a refused opening by the internet is still reach.

## Paths

A path is publicly exposed when reach holds for its asset. Reach holds when the configuration holds the asset, the configuration admits the interaction, and the initiating party is the internet. The rows are that test.

| Path                                                                                                                                | Reach                                                                                                                                  | Publicly exposed                                                                                            |
| ----------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| The internet opens an interaction, and the asset refuses                                                                            | The configuration holds the asset and admits the interaction. The initiating party is the internet. The refusal is a reply.            | Exposed                                                                                                     |
| The internet opens an interaction, and the asset accepts                                                                            | The same reach holds. Acceptance is a reply.                                                                                           | Exposed                                                                                                     |
| The system opens an interaction toward the internet                                                                                 | The initiating party is not the internet.                                                                                              | Not exposed                                                                                                 |
| The internet replies to an interaction the system opened                                                                            | The reply stays in that interaction. It does not add a pair whose initiating party is the internet.                                    | Not exposed                                                                                                 |
| A party other than the internet opens an interaction                                                                                | The initiating party is not the internet.                                                                                              | Not exposed                                                                                                 |
| The internet opens an interaction with an asset the configuration does not hold                                                     | The configuration does not hold the asset.                                                                                             | Not exposed                                                                                                 |
| The configuration does not admit the interaction                                                                                    | The configuration does not admit the pair.                                                                                             | Not exposed                                                                                                 |
| The internet opens an interaction with an edge asset, and a party other than the internet opens an interaction with an origin asset | Reach holds for the edge. The origin interaction has a party other than the internet as its initiating party. An asset is not a party. | The edge is exposed. The origin is not exposed. Therefore, the system, which includes the edge, is exposed. |
