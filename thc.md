

# THC: Unit of account for digital goods
@xhipster
4000K

THC protects consumers and suppliers from collapsing fiat economy while allowing sellers profit from demand increase of accounting unit in which they set prices and enabling buyers to save on gas costs.

## Introduction

First of all lets get down to what is a good unit of account is.
In our opinion good unit of account have to reach optimal balance between store of value while remaining liquid enough to become medium of exchange.

The token tend to become a unit in which agents measure profits if it is steadily growing. This property is necessary because all else being equal agent will store value in the fastest growing token. But agent will choose only from the most liquid ones. E.g. if you analyse the most popular fiat tokens you will find out that only some of them such as CHF, JPY, SGD and GBP were able to outperform dollar in last 20+ years. The other were stagnating in comparison. Nevertheless, the planet continued to think in USD because it was the most liquid out of the most performant. However, nothing stops us from assuming that both properties are possible indeed.

USD denominated ERC-20 tokens often referred as stable coins can help transition from fiat economy to cyber economy but they lack one important property which is necessary for pricing of digital goods: profitability in ETH. The reason is simple: nearly all Ethereum based utility tokens valuated in ETH because ETH was primary investment unit and it is necessary to pay for gas. Hence, setting prices in USD, DAI and other shit will result in a drain of value and will lead to non-sustainable nature of such projects. Pricing in ETH will solve part of the issue. But inability to produce more ETH while holding it open opportunity for derivatives which can. Recent advancement in the theory of money hypothesis that currencies with elastic supply are more suited for day to day commerce due to ability to absorb demand smoother. So, we introduce such a tool which is a good store of value also. It can effectively capture value of the best performing tokens based on investment baskets which we refer to as gTokens.

gTokens works as a basis for THC sustainability, liquidity and profitability.

## gTokens

gToken (g - growing) is an investment token which maximise profitability for longterm investors. gTokens are collective investment vehicles which simultaneously (1) balance between assets and (2) between trading and lending depending on the market demand. Price of gTokens is an index of underlying assets and reflects quality of asset management of a collective. All emergent profits from the pool are extracted as steady flow of THC tokens for investors. This allow holders to generate steady cashflow while keeping basic profitability agains target token or benchmark.

Invest. Каждый может поставить базовые токен (bToken). Чем дефицитнее поставлен bToken тем дешевле фи на ввод. Чем больше инвестиций провернул протокол,тем выше фи. Чем выше фи, тем меньшая доля уходит рефералу. Стейкинг THC дает буст реферальных наград.

Redeem. Чем дефицитнее выведен dETH, тем выше фи на вывод. Метод под вопросом. https://andrecronje.medium.com/crypto-economics-perpetual-liquidity-and-il-offsets-197558347a53

Stake. Stake gETH for amount of days you want and get more THC rewards.

Exchange. Чем выше относительные обороты, тем выше фи. Модуль по расчету цен обновляем.

Transfer. Трансфер gTokens облагается налогом. Цель налога - добавить инцентив на расчеты в THC. Чем выше оборачиваемость - тем выше налоговая ставка.

Borrow. Процентная ставка определяется как функция доходности от торговых комиссий! Чем доходнее трейдинг - тем выше процентная ставка на кредиты.

В момент займа происходит несколько вещей:
- Из пула заемщику трансферится bToken
- В пул минтится dToken
- заемщику минтится не перемещаемое обязательство погашения
- заемщику минтится право выкупить dToken из пула по расчетной цене

Repay.

A collective define the following properties:
- listing principles (simple majority vote, weighted, etc)
- management actions (claim rewards, vote in proposals, etc)
- pricing curve (simple, active, stable, non-fungible, etc.)
- lending curve (plain, progressive, etc)
- local taxes (gTokens and dTokens transfers, exchange invest, redeem, borrow, repay)

Deployment. gTokens can be created .. + ERC721 for org.

## dTokens

dTokens (d - debt) is a colateralized debt token which

Чем больше доля долга в пуле - тем выше процентная ставка. Рациональ - управление коэффициентом резервирования. Чем выше коэффициент резервирования - тем выше риск, тем выше доходность. По мере роста доходности спрос уменьшается. Следовательно рынок самостоятельно находит равновесие в точке оптимального соотношения риск/доходность.

## THC

Расчетный токен. Расчеты в THC выгодны так как генерируют дополнительный доход и тем, кто устанавливает в THC цены и тем кто рассчитываются в нем. В токен встроены следующие механизмы:
- инцентив тем, кто получает его
- субсидия на газ тем, кто его перечисляет
- эластично перераспределения повышенного спрос на THC его держателям. Цена THC стремится к стоимости индекса dASSET взвешенного на ( ? ликвидность, сумму активов, оборачиваемость)

Mint. Volume of minting is coupled with amount of taxes collected by the protocol.

Key idea of the mint distribution is that there exist feedback loop between amount of provided liquidity and exchanged volumes. At first exchange is impossible without liquidity. But then only growing volumes can boost liquidity grow further as exchange rewards maximise profitability of liquidity providers. So we have to create positive feedback loop between these two processes. We assume that the distribution have to be s-curve like with bigger share for liquidity providers in the beginning and bigger share for traders than the system matures. The problem with this approach is to (1) assume optimal s-curve and (2) assume maturity.

Transfer. Имплементирован таким образом, чтобы эфир был не нужен. Газ субсидируется! Цель - сделать трансфер THC дешевле чем трансфер эфира. Получатель токена получает дополнительный доход.

Stake. Чем на дольше застейкано - тем дешевле услуги и выше награды.
- выше награды с ликвидности
- дешевле торговые комиссии
- выше бонус при получении
- больше субсидия при отправке
- больше награда реферала
- выше сила голоса
- лучше процентная ставка на кредиты

Stakers define the following policies for products:
- Staking policy
- tax policies (gTokens and dTokens transfers, invest, redeem, borrow, repay, AUM)
- local voting policy (THC power)
- discount curves (exchange, borrow, THC transfer)
- rewards boosters (invest, referral, receive)

Any time cyber~Foundation can delegate the function to the stakers of gTokens.

Get rewards. Минтится тем кто держит ликвидность с учетом модификаторов.

Burn. Чем больше выручка - тем больше сжигается

Using any token as unit of account extend value over intrinsic properties. So we introduce nitro method which rebase balances if market price is not around the target price which is compound index of all gAssets weighted on their valuation. Key purpose of rebased  is redistribution of excess value to THC holders created by the use of THC as an accounting unit. Rebase happens every hour:

1. Коэффициент вычислить
2. Дернуть методы из вайтлиста
2. Вывести доход и конвертнуть его в THC
3. Допечатать THC в базу
4. Перевычислить стратегию (целевую структуру портфеля)
5. Пересчитать размер субсидии

(?) Чем ближе THC к пегу, тем больше наград

## NODE

vTHC holders also have the right to mint NODE tokens based on the idea to mint 4B NODE in 10 years with S-curve schedule.

16 symbols - planets
8 symbols - stars
8 symbols - galaxies

Every organization is ERC-721 token with name and controller, which can be ERC-20 token

## Highlands

Implemented as gToken org template

The biggest task is to create a product with ETH profitability

Assets: WETH, cETH, aETH, bETH, rETH, sETH, THC

## Deep lake

Implemented as gToken org template

In order THC become value of exchange it needs good external liquidity:

- WETH/THC Uniswap
- WETH/THC Sushuswap
- WETH/THC Moonyswap
- WETH/THC Balancer
- WETH/THC Dodo

## Gazprom

Implemented as elastic org template.

Creation of gas based investment product is necessary to hedge against high gas prices.

- CHI
- GST2

## Alphabet

- ANT/THC
- REN/THC
- FOAM/THC
- MANA/THC
- REP/THC
- RDN/THC
- UNI/THC
- BAL/THC
- AAVE/THC
- SNT/THC
- MLN/THC
- RPL/THC
- LPT/THC
- GNT/THC

## Mountain of Force

80% of minted THC supply is under control of cyber~Foundation

Basic idea is to stimulate liquidity not on desire to have liquidity, but stimulate liquidity in principle in the place there liquidity organically emerge. So the protocol must not overpay for unneeded liquidity.

## Magic Forest

20% of minted THC supply is absorbed by the Magic Forest. Great Web needs them. Magic forest will also help create cyber creatures (cyber protocol deployments into different consensus architectures and computers). This deployments will be available exclusively to THC stakers.

5 причин высокой доходности
жизненный цикл звезды
Обмен долями с нонсенс
Proof of value mechaism эмиссии
