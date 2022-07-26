# Structure of Profile of Account and Network
- [Structure of Profile of Account and Network](#structure-of-profile-of-account-and-network)
  - [1. Demographic Profile of an Account (*resume-liked*)](#1-demographic-profile-of-an-account-resume-liked)
  - [2. Demographic of Transaction](#2-demographic-of-transaction)
  - [3. Set of Address](#3-set-of-address)
    - [1. Address Active Addresses](#1-address-active-addresses)
    - [2. Address Balances (Native)](#2-address-balances-native)
    - [3. Address Balances (USD)](#3-address-balances-usd)
    - [4.  Address Growth](#4--address-growth)
    - [5. Addresses in Profit/Loss](#5-addresses-in-profitloss)
    - [6. Exchange Activity](#6-exchange-activity)
    - [7. Hodlers](#7-hodlers)
  - [4. Token Summary](#4-token-summary)
    - [4.1 Overview:](#41-overview)
    - [4.2 Four Main Onchain Signals](#42-four-main-onchain-signals)
    - [4.3 Exchange Signals](#43-exchange-signals)
    - [4.4 Derivatives](#44-derivatives)
    - [5. Exchange Flow Indicator](#5-exchange-flow-indicator)
      - [5.1 IntoTheBlock](#51-intotheblock)
      - [5.2 CrytoQuant](#52-crytoquant)
        - [1. Reserve:](#1-reserve)
        - [2. Exchange In/Outflow & Netflow](#2-exchange-inoutflow--netflow)
        - [3. Withdrawing Transactions](#3-withdrawing-transactions)
        - [4. In-House Flow (Total/Mean)](#4-in-house-flow-totalmean)
    - [6. On-chain Flow Indicators CryptoQuant](#6-on-chain-flow-indicators-cryptoquant)
## 1. Demographic Profile of an Account (*resume-liked*)
1. Background
	- source (LT-BP)
	- destination (LT-FP)
2. Core Network Graph
	- Most Significant Transaction Parties (Relevance)
3. Timestamp of Significant Change
4. Annotated Features
	- Retention Rate
5. Num of Transactions
6. Total Received
7. Total Sent
8. Final Balance
9. Transactions

- Fee 
	- BTC
	- (17.704 sat/B - 7.025 sat/WU - 223 bytes)
	- (28.000 sat/vByte - 141 virtual bytes)
	- Hash


## 2. Demographic of Transaction

1. Block
2. Time	2022-07-17 05:03:04
3. Size	113 (bytes)
4. Total Input	0.00014639 BTC
5. Total Output	0.00010691 BTC
6. Fees	0.00003948 BTC



## 3. Set of Address 
https://studio.glassnode.com/metrics?a=BTC&m=addresses.ActiveCount

### 1. Address Active Addresses 
1.1. Active Addresses  
1.2. Sending Addresses 
1.3. Receiving Addresses

### 2. Address Balances (Native)
2.1. With Non-zero Balance
2.2. Balance ≥ 0.01
2.3. Balance ≥ 0.1
2.4. Balance ≥ 1
2.5. Balance ≥10
2.6. Balance≥100
2.7. Balance≥1k
2.8 Balance≥10k

### 3. Address Balances (USD)
3.1. Balance ≥ $1
3.2. Balance ≥ $10
3.3. Balance ≥ $100
3.4. Balance ≥ $1k
3.5. Balance ≥ $10k
3.6. Balance ≥ $100k
3.7. Balance ≥ $1M


### 4.  Address Growth
4.1. Address Supply Distribution
4.2. Supply Held by Addresses with Balance < 0.001
4.3. Supply Held by Addresses with Balance 0.001 - 0.01
4.4. Supply Held by Addresses with Balance 0.01-0.1
4.5. Supply Held by Addresses with Balance 0.1-1
4.6. Supply Held by Addresses with Balance 1-10
4.7. Supply Held by Addresses with Balance 10-100
4.8. Supply Held by Addresses with Balance 100-1k
4.9. Supply Held by Addresses with Balance 1k-10k
4.10. Supply Held by Addresses with Balance 10k-100k
4.11. Supply Held by Addresses with Balance >100k

### 5. Addresses in Profit/Loss
5.1. Percent Addresses in Profit
5.2. Addresses in Profit
	- Definition: 
	- The number of unique addresses whose funds have an average buy price that is lower than the current price. 
	- "Buy price" is here defined as the price **at the time coins were transferred into an address**.
5.3. Addresses in Loss
	- Definition:
		- The number of unique addresses whose funds have an average buy price that is higher than the current price. 
		- "Buy price" is here defined as the price at the time coins were transferred into an address.




### 6. Exchange Activity
6.1. Number of Addresses Depositing to Exchanges
	- Definition:
		- The number of unique addresses that appeared as a **sender** in a transaction sending funds to exchanges.
6.2. Number of Addresses Withdrawing from Exchanges
	- Definition: 
		- The number of unique addresses that appeared as a **receiver** in a transaction receiving funds from an exchanges.


### 7. Hodlers 
7.1. Accumulation Addresses
	-  have at least 2 incoming **non-dust** transfers and have **never spent funds.** Exchange addresses and addresses receiving from coinbase transactions (miner addresses) are discarded. To account for lost coins, addresses that were last active more than 7 years ago are omitted as well.
	- *Bitcoin dust is a series of trace amounts of bitcoins that individually are less valuable than the computing power or fee that is required to process them; as a result, the transaction is impossible to process.*
	- *The cost of the fee to process a bitcoin transaction fluctuates based on the volume of transactions on the network.*
	- *While Bitcoin dust can slow down network transactions, attempting to clean up Bitcoin dust can create a privacy problem, especially for small users.*

7.2. Accumulation Addresses [BTC]
	- The total amount of funds held in accumulation addresses. 
	- Accumulation addresses are defined as addresses that have at least 2 incoming non-dust transfers and have never spent funds. 
	- Exchange addresses and addresses receiving from coinbase transactions (miner addresses) are discarded. To account for lost coins, addresses that were last active more than 7 years ago are omitted as well.






## 4. Token Summary
### 4.1 Overview:
1. Holders Making Money at Current Price
	 - Definition: 
		- For any addresses with a balance of tokens, ITB identifies the average cost at which those tokens were purchased and compares it to current price.
		- If Current Price > Average Cost
			- address is **in the Money**
		- If Current Price < Average Cost 
			- address is Out of Money
	- More: https://resources.intotheblock.com/blockchain-analytics/token-summary#holders-making-money-at-current-price


2. Concentration by Large Holders
	- Definition: This indicator aggregates the percentage of circulating supply held by whales (addresses holding over 1% of supply) and investors (addresses holding between 0.1%-1%). The sum of these two is the total concentration by large holders. 
	- Input:  the percentage of circulating supply held by 
		- whales (addresses holding over 1% of supply)  
		- investors (addresses holding between 0.1%-1%)
	- Calculation
		- sum of these two is the total concentration by large holders. 
	- More: https://resources.intotheblock.com/blockchain-analytics/token-summary#concentration-by-large-holders



3. Price Correlation with Bitcoin
	- Definition:
		- 30-day price correlation with BTC
	- More: https://resources.intotheblock.com/blockchain-analytics/token-summary#price-correlation-with-bitcoin

4. Holders' Composition by Time Held
	- Defintion:
		- Classification of addresses according to their weighted average holding period of the token
	- More: https://resources.intotheblock.com/blockchain-analytics/token-summary#holders-composition-by-time-held


5. Transactions Greater than $100K
	- Definition:
		- Number of transactions each value is greater than $100K
	- More: https://resources.intotheblock.com/blockchain-analytics/token-summary#transactions-greater-than-usd-100-k

6. Transactions Demographics
	- Defintion: 
		- Num of transactions that occur during Western trading times (10AM to 10PM UTC) vs those that occur during Eastern trading times (10PM to 10AM UTC) for the last 14 days
	- More: https://resources.intotheblock.com/blockchain-analytics/token-summary#total-exchanges-inflows


7. Total Exchanges Inflows
	- Definition: 
		- Total amount (in $ or tokens) entering exchange(s) deposit wallets
	- More: https://resources.intotheblock.com/blockchain-analytics/token-summary#total-exchanges-outflows


8. Total Exchanges Outflows
	- Total amount (in $ or tokens) entering exchange(s) withdrawal wallets




### 4.2 Four Main Onchain Signals
1. Net Network Growth
	- Definition: This signal measures the change in the **total number of addresses for a particular crypto-asset.** 
		- Specifically, it tracks the **variation relative to the previous** week’s total addresses, **optimizing the thresholds** considered bullish or bearish to each asset’s nature. 
	- More: https://resources.intotheblock.com/blockchain-analytics/actionable-signals/on-chain-signals#net-network-growth



2. In-the-money
	-  Interpretation:
		- Using IntoTheBlock’s In/Out of the Money indicator, we are able to estimate the volume of tokens that are in the money, or profiting for a particular crypto-asset at a given price level. This model follows the 7-day moving average in the total volume of supply in the money and compares it to the value from the previous day. 

3. Concentration
	- Input:  addresses that hold over 1% of circulating supply, and investors, addresses that hold between 0.1% and 1% of supply.
	- Definition: The concentration signal measures daily changes in the positions of whales, addresses that hold over 1% of circulating supply, and investors, addresses that hold between 0.1% and 1% of supply.
	- Interpretation:
		- If whales and investors are adding to their positions it is generally bullish, though the specific thresholds vary by crypto-asset.
	- More: https://resources.intotheblock.com/blockchain-analytics/actionable-signals/on-chain-signals#concentration

4. Large Transactions
	- Interpretation: 
		Based on IntoTheBlock’s large transactions metric, this signal analyzes shifts in the number of transactions of over $100,000, and acts as a proxy to institutional investors’ and high net-worth individuals’ activity. The model is optimised by tracking the convergence/divergence between the **21-day exponential moving average (EMA)** and the **30-day EMA** for large transactions. 
	More: https://resources.intotheblock.com/blockchain-analytics/actionable-signals/on-chain-signals#concentration



### 4.3 Exchange Signals
1. Smart Price
	- Defintion: 
		- A variation of the mid price where the average of the bid and ask prices is weighted according to their inverse volume (i.e., 
			- the bid is weighted with the volume posted at the ask, and 
			- the ask is weighted with the volume posted at the bid
	- More: https://app.intotheblock.com/coin/BTC
2. Bid-Ask Volume Imbalance
	- Definition: 
		- Volume at the bid price - Volume at the ask price
	- More: https://app.intotheblock.com/coin/BTC

### 4.4 Derivatives 
- Futures Market Premium
	- Definition:
		- Signal combining futures price, volume and open interest assessing bullish or bearish momentum
	- More: https://app.intotheblock.com/coin/BTC






### 5. Exchange Flow Indicator 
#### 5.1 IntoTheBlock
On-chain flows display how crypto assets are moving **to and from exchanges**. Data could be subject to change as IntoTheBlock's models evolve over time.
- View Group Chart: https://app.intotheblock.com/coin/BTC/deep-dive?group=exchanges&subgroup=on-chain-flows&chart=all
1. On-chain Flows
	- Definition: Total amount (in $ or tokens) entering exchange(s) deposit wallets. "All Exchanges" refers to all supported exchange

2. Inflow Transaction Count
	- Definition: Total number of deposit transactions
	- Changes: in Percentage %
		- 24h Change, 7-Day Change, 30-Day Change

3. Outflow Volume
	- Definition:  Total amount (in $ or tokens) **leaving** exchange(s) **withdrawal** wallets.
	- Changes: in Percentage %
		- 24h Change, 7-Day Change, 30-Day Change



4. Outflow Transaction Count
	- Definition: Total number of **withdrawal** transactions
	- Changes: in Percentage %
		- 24h Change, 7-Day Change, 30-Day Change

5. Netflows
	- Definition: Netflows show the difference between tokens **entering** an exchange - those **leaving** exchanges
	- Changes: in BTC
		- 24h Change, 7-Day Change, 30-Day Change
		

6. Total Flows
	- Definition: Sum of amount entering an exchange plus the amount leaving an exchange
	- Changes: in Percentage %
		- 24h Change, 7-Day Change, 30-Day Change

#### 5.2 CrytoQuant
A money flow of Bitcoin transferred to and from exchange wallets to evaluate investors' behavior.
Group Chart: https://cryptoquant.com/asset/btc/chart/exchange-flows

##### 1. Reserve:
- Definition: The total number of coins held in the exchange.
- Input: (same as Definition)
- Description: 
	- As the values continue to **rise** in reserve, it indicates **higher selling** pressure and has shown an **opposite** trend in price in general. 
	- For stablecoin, value rise indicates **buying pressure**  
	- For derivative exchange, since coins could be used to open both **long/short**, a **rise in reserve** values indicates possible **high volatility**.
- View: https://cryptoquant.com/asset/btc/chart/exchange-flows/exchange-reserve?exchange=all_exchange&window=DAY&sma=0&ema=0&priceScale=log&metricScale=linear&chartStyle=line
- User Guide: https://dataguide.cryptoquant.com/exchange-flows-indicators/exchange-reserve-1
- API: https://cryptoquant.com/docs#operation/BTCgetReserve

##### 2. Exchange In/Outflow & Netflow
- Transactions Count:
	- Definition: This endpoint returns the number of transactions flowing in/out of Bitcoin exchanges.
	- API: https://cryptoquant.com/docs#operation/BTCgetTransactionsCountEF
- Addresses Count:
	- Definition: This endpoint returns the number of addresses involved in inflow/outflow transactions
	- API: https://cryptoquant.com/docs#operation/BTCgetAddressesCountEF
- Netflow
	- Definition: https://cryptoquant.com/docs#operation/BTCgetExchangeNetflow
		- The difference between coins flowing into and out of the exchange. (**Inflow - Outflow = Netflow**)  
		- Positive value indicates reserve in increasing.  
		- For **spot** exchange, **high** value indicates **increasing selling** pressure.  
		- For **derivative** exchange, **high** value indicates possible high **volatility**.
	- View: https://cryptoquant.com/asset/btc/chart/exchange-flows/exchange-netflow-total?exchange=all_exchange&window=DAY&sma=0&ema=0&priceScale=log&metricScale=linear&chartStyle=column
	- User Guide: https://dataguide.cryptoquant.com/exchange-flows-indicators/exchange-in-outflow-and-netflow
	- API: https://cryptoquant.com/docs#operation/BTCgetExchangeNetflow
- Inflow 
	- API: https://cryptoquant.com/docs#operation/BTCgetInflow
	- Inflow (Total)
		- Definition:  The total amount of coins transferred to the exchange.
		- Description:
			- High value indicates higher selling pressure in the spot exchange. (For stablecoin, value rise indicates buying pressure)  
			- For derivative exchange, since coins could be used to open both long/short, rise in inflows indicates possible high volatility.
	- Inflow (Mean, MA7)
	 	- Definition: The 7 days moving average of mean coins inflow to the exchange.
	 	- Description:
		 	- Higher value indicates investors who **deposited a lot** at once are increasing recently.  
			- It could indicate higher selling pressure and future price drop. (For stablecoin, value rise indicates buying pressure)
- Outflow
	- API: https://cryptoquant.com/docs#operation/BTCgetOutflow
	- Outflow (Total)
		- Definition: The total amount of coins transferred from the exchange.  
		- Description: High value indicates decreasing selling pressure in the spot exchange.
	- Outflow (Mean, MA7)
		- Definition: The 7 days moving average of mean coins outflow from the exchange.  
		- Description:
			- High value indicates investors who **withdrew a lot** at once are increasing recently.  
			- It could indicate **decreasing selling** pressure.

##### 3. Withdrawing Transactions
- Definition: The total number of withdrawals count from the exchange.  
- Description: 
	- High value indicates more transactions were made for **long-term holding in high possibility**. 
	- For derivative exchange, it could indicate the number of **withdrawals increased** to participate less in derivative trades.
- More: https://dataguide.cryptoquant.com/exchange-flows-indicators/exchange-addresses-count
- API: https://cryptoquant.com/docs#operation/BTCgetAddressesCountEF



##### 4. In-House Flow (Total/Mean)
- Definition: The total amount of coins circulated within the exchange's wallets.
- View: https://cryptoquant.com/asset/btc/chart/exchange-flows/exchange-in-house-transactions?exchange=all_exchange&window=DAY&sma=0&ema=0&priceScale=log&metricScale=linear&chartStyle=line
- API: https://cryptoquant.com/docs#operation/BTCgetInHouseFlow





### 6. On-chain Flow Indicators CryptoQuant
*Flow Indicator: on on-chain models to signal possible price movements by assessing the value of Bitcoin and allow investors and traders to operate with confidence.*
- On-chain models to signal possible price movements by assessing the value of Bitcoin and allow investors and traders to operate with confidence.

1. Miners' Position Index (MPI)
	- Definition: the ratio of total miner outflow (USD) to its one-year moving average of total miner outflow (USD).  
	- Description:
		- Higher value shows that miners are sending more coins than usual which indicates possible selling.  
		- If miners send some proportion of their reserve at the same time, it could trigger a price drop.
	- Details:
		- MPI(Miners’ Position Index) is a z score of a specific period. The period range must be 2 days or more and if not, it will return an error. `mpi` is an index to understand miners’ behavior by examining the **total outflow of miners**. It highlights periods where the value of Bitcoin’s **outflow by miners on a daily basis** has historically been extremely high or low. 
		- MPI values above 2 indicate that most of the miners are selling Bitcoin. 
		- MPI values under 0 indicate that there is **less selling pressure** by miners.
	- Guide: https://dataguide.cryptoquant.com/miner-flows-indicators/miners-position-index
	- [API](https://cryptoquant.com/docs#operation/getMPI)
2.  Exchange Whale Ratio
	- Definition: The ratio of the top 10 inflows to the total inflows of the exchange.
	- Description:
		- High values indicate whales are using the exchanges in large amount.



3.  Exchange Inflow CDD [Coin Days Destroyed (CDD)](https://cryptoquant.com/asset/btc/chart/network-indicator/coin-days-destroyed-cdd) of coins destroyed by flowing into exchanges.
	- View https://cryptoquant.com/asset/btc/chart/flow-indicator/exchange-inflow-cdd
	1. Fund Flow Ratio
		- Definition: The ratio of coins transfers involving the exchange to the overall coins transfers network-wide.  
		- Description: 
			- High values indicate investors are actively using the exchanges.
	
	2. Exchange Stablecoins Ratio USD
		- Definition: Coins reserve(USD) divided by all stablecoins reserve held by the exchange.  
		- Description:
			- Low values mean buying power which leads to possible price rise.
	3. Exchange Stablecoins Ratio
		- Definition: Coins reserve divided by all stablecoins reserve held by the exchange.  
		- Description:
			- Low values mean buying power which leads to possible price rise.

	4. [Exchange Shutdown Index](https://cryptoquant.com/docs#operation/getExchangeShutdownIndex)
		- Definition: If there's no outflow from the exchange, the value is 1, otherwise 0.  
			Continuous appearance of '1' indicates exchange withdrawal system is not functioning.
		- Description:
			-  Stay Ahead of Exchange Hacks. See hacks as they happen by identifying sudden increases and become zero in exchange outflows and hedge against potential risk.
		- API: https://cryptoquant.com/docs#operation/getExchangeShutdownIndex



- Inflow CDD
	- Definition: [Coin Days Destroyed (CDD)](https://cryptoquant.com/asset/btc/chart/network-indicator/coin-days-destroyed-cdd) of coins destroyed by flowing into exchanges.  
High values indicate that more long-term holders moved their coins for the purpose of possible selling.  
This indicator is a noise-removed version of CDD with respect to exchange dumping signal.

