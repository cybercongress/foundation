# Elastic: Defi primitive with supply feedback 
@xhipster
4700K

Simple contract fabric would allow anybody create trustless derevatives with elastic supply based on uniswap price feed. Simplicity of construction eleminates expensive governance process and any possible single point of failure. Applications are numerous. One of such application is unit of account for digital goods: ETH derevative which protects consumers and suppliers from collapsing fiat economy while enable profiting from demand increase of accounting unit in which they set prices. Another application is digital oil: gas derevative which allow to hedge against gas price fluctiations while capturing value of increased usage of the tool. Of course it also could be used to create elastic derevatives based on unstable collapsing fiat unit of account. In this paper we outline implementation ratiaonale and incentive details behind the implementation of the fabric.

## Introduction

Recent real market experiments such as AMPL shows that an idea of the mechanism in which supply is adjusted based on target price can be viable. It can be used for not only for tracking dollar value. But mentioned project lacks essential properties reqired for defi:
- conract must not be ownable
- price feeds have to be bulletproof
- initial distribution have to be more open
- the concept can be generalized
- liquidity incentive have to be embedded
- rebased incentives have to be in place
- extended value extraction for agents can be applied

This facts create opportunity for more open and resilient tool.

## THC

Dollar denominated tokens often reffered as stable coins can help transition from fiat economy to cyber economy but they lack one important property which is necessary for pricing of digital goods: profitability in ETH. The reason is simple: nearly all Ethereum based utility tokens valuated in ETH beacuse ETH is necesssary to pay for gas. Hence, setting prices in USD, DAI and other shit will result in a drain of value and will lead to non-sustainable nature of such projects. Pricing in ETH will solve part of the issue. But inability to produce more ETH while holding it open opportunity for derevatives which can. Recent advancement in the theory of money hypothesis that currencies with elastic supply are more suted for day to day commerce due to ability to absorb demand smoother. So, we introduce such a tool.

Genesis supply is 1 000 000 000 000 000 THC or 1M GTHC. THC is undivisible. At Genesis the picture is the following:
- 20% Magic Forest
- 80% Mountain of Force

UX:

How long will they suck you? 

=> Fuck them

![photo_2020-07-28 13 28 07](https://user-images.githubusercontent.com/410789/88660061-5708e180-d0d6-11ea-8cb9-210f9cdbb6e9.jpeg)


Picture: mountain, forest, river, beach, sun, well, sea.

Price * Balance = Total

Chart supply with price

=> [amount] GTHC Buy

## Nitro

Supply function depends on the average price. Target price of 1 GTHC is 1 ETH. Every 1000 blocks balances are adjusted using RebaseRatio according to the price oracle set by a consensus of cyberFoundation:

RebaseRatio = (Average price - Target price) / 73

At the start the system relies solely on the Uniswap v2 price oracle. Rebase call requre incentive for execution. Everybody can be a caller. The caller get 2x of the gas spent of the call in THC to ensure that rebase will be executed with high pripority.

UX:

Next rebase in <amount of blocks>

Last reward: 0.3 GTHC

=> Rebase

## Magic Forest

20% of Genesis supply is absorbed in the Magic Forest. Great Web needs them. Magic forest will also help create cyber creatutres (cyber protocol deployments into different consensus architectures and computers). This deployments will be available exclusivly to THC holders.

=> Subscribe to cyberCongress feed

## Mountatin of Force

80% of Genesis supply is under control of cyberFoundation but is fully available through the bonding curve.

THC price = 

Every rebase the price of the bonding curve is adjusted.

UX:

Amount of THC, OIL and ETH in cyberFoundation

Price chart of the bonding curve

=> Buy THC from cyberFoundation

## Liquid River

THC holders defines how much liquidity incentives THC needs. They do it buy staking THC on LiquidityRatio - amount of tokens substructed from the Mountatin of Force every rebase: 

LiquidityRatio = SUM (Amount of staked tokens * Liquidity ration) / staked tokens

UX:

Share in the pool
Liquidity rewards

=> Add / Remove liquidity

## Staking Beach

Liquidity reward is split between stakers and liquidity providers. The idea is the following: the more LiquidityRatio is set by the consensus - the less percent of Liquidity rewards is being recieved by stakers. Doing so we ensure that stakeholders will tend to the equilibrium ratio which will optimally incentiveze liquidity.

Staker rewards = 

=> Stake / Unstake on LiquidityRatio

## Deep Sea

Considering that the same mechanics can be applied to any fungible token we distinct them as a new asset class called "elastic". We created a factory which allow to deploy them easily. 

Factory for deploying: params: percent for self, contract for self, base token contract

UX:

List of elastics sorted by cap with the following collumns 
- price
- supply
- liquidity
- turnover
- cap

=> click on the line: Buy or Sell
=> Create elastic

## Oil well

Oil is extracted from oil well. Oil helps store and transfer gas. The only difference between avarage elastic is that there exist special price oracle which incentivize calls in order to determine gas price for rebase.

UX:

OIL price chart (target/actual)

=> Report price

## Sun

The same as Uniswap swap dialog. 

Returns eth spent for gas. Tx fees are set by governance, split between burn and cyberFoundation, burn rate is set by governance, 

=> Swap (Send)
