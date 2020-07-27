THC: Unit of account for digital goods

@xhipster and @litvintech

5000K

Trustless ETH derevative with elastic supply protects consumers and suppliers from collapsing fiat economy while enable profiting from demand increase of accounting unit in which they set prices. 

## Init

Dollar denominated tokens often reffered as stable coins can help transition from fiat economy to cyber economy but they lack one important property which is necessary for pricing of digital goods: profitability in ETH. The reason is simple: nearly all Ethereum based utility tokens valuated in ETH beacuse ETH is necesssary to pay for gas. Hence, setting prices in USD, DAI and other shit will result in a drain of value and will lead to non-sustainable nature of such projects. Pricing in ETH will solve part of the issue. But inability to produce more ETH while holding it open opportunity for derevatives which can. Recent advancement in the theory of money hypothesis that currencies with elastic supply are more suted for day to day commerce due to ability to absorb demand smoother. So, we introduce such a tool.

Genesis supply is 1 000 000 000 000 000 THC or 1M GTHC. THC is undivisible. At Genesis the picture is the following:
- 20% Magic Forest
- 80% Mountain of Force

UX:
How long will they suck you? 
=> Fuck them
Picture: Forest, river, mountain, sea, oil, sun
Price * Balance = Total
Chart supply with price
=> [amount] GTHC Buy

## Rebase

Supply function depends on the average price. Target price of 1 GTHC is 1 ETH. Every 1000 blocks balances are adjusted using RebaseRatio according to the price oracle set by a consensus of cyberFoundation:

RebaseRatio = (Average price - Target price) / 73

At the start the system relies solely on the Uniswap v2 price oracle. Rebase call requre incentive for execution. Everybody can be a caller. The caller get 2x of the gas spent of the call in THC to ensure that rebase will be executed with high pripority.

UX:
Next rebase in <amount of blocks>
Last reward: 0.3 GTHC
=> Rebase

## Sun

Swap and send. One convinient dialog for swapping and sending tokens.

## Magic Forest

20% of Genesis supply is lost in the Magic Forest.

## Mountatin of Force

80% of Genesis supply is under control of cyberFoundation but is fully available through the bonding curve. The price of the curve is also adjusted.

## Liquid River

THC holders defines how much liquidity incentives THC needs. They do it buy staking THC.

Emission is defined but distriubtion can be changed based on governance decisions as it is nearly impossible to predict the protocol for the liquidity source this is the only distribution aspect that can be adjusted by the governance mechanism. At Genesis the only price oracle is uniswap.

## Deep sea

Considering that the same mechanics can be applied to any fungible token we distinct them as a new asset class called "elastic". We created a factory which allow to deploy them easily. We ref them elastics. 

Factory for deploying: param: percent for self

List of elastics sorted by cap with the following collumns 
- price
- supply
- liquidity
- turnover
- cap

Action bar: click on the line 

## Oil

Oil helps store and transfer gas.
set by governance, split between burn and cyberFoundation, burn rate is set by governance, returns gas payed for tx)
