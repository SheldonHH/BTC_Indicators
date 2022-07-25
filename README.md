# Structure of Profile of Account and Network

## 1. Demographic Profile of an Account (*resume-liked*)
1, Background
	- source (LT-BP)
	- destination (LT-FP)
2. Core Network Graph
	- Most Signficant Transaction Parties (Relevance)
3. Timestamp of Significant Change
4. Annotated Features
	- Retention Rate


## 2.  set of Address

### 2.1 Exchange *cryptoquant*
- Reserve:
	- Definition: The total number of coins held in the exchange.
	- Input: (same as Definition)
	- Description: 
		- As the values continue to **rise** in reserve, it indicates **higher selling** pressure and has shown an **opposite** trend in price in general. 
		- For stablecoin, value rise indicates **buying pressure**  
		- For derivative exchange, since coins could be used to open both **long/short**, a **rise in reserve** values indicates possible **high volatility**.


- [Netflow](https://cryptoquant.com/asset/btc/chart/exchange-flows/exchange-netflow-total?exchange=all_exchange&window=DAY&sma=0&ema=0&priceScale=log&metricScale=linear&chartStyle=column)
	- The difference between coins flowing into and out of the exchange. (**Inflow - Outflow = Netflow**)  
	- Positive value indicates reserve in increasing.  
	- For **spot** exchange, **high** value indicates **increasing selling** pressure.  
	- For **derivative** exchange, **high** value indicates possible high **volatility**.




- Inflow (Total)
	- Definition:  The total amount of coins transferred to the exchange.
	- Description:
		- High value indicates higher selling pressure in the spot exchange. (For stablecoin, value rise indicates buying pressure)  
		- For derivative exchange, since coins could be used to open both long/short, rise in inflows indicates possible high volatility.

- Outflow (Total)
	- Definition: The total amount of coins transferred from the exchange.  
	- Description: High value indicates decreasing selling pressure in the spot exchange.

- Inflow (Mean, MA7)
 	- Definition: The 7 days moving average of mean coins inflow to the exchange.
 	- Description:
	 	- Higher value indicates investors who **deposited a lot** at once are increasing recently.  
		- It could indicate higher selling pressure and future price drop. (For stablecoin, value rise indicates buying pressure)

- Outflow (Mean, MA7)
	- Definition: The 7 days moving average of mean coins outflow from the exchange.  
	- Description:
		- High value indicates investors who **withdrew a lot** at once are increasing recently.  
		- It could indicate **decreasing selling** pressure.

- Withdrawing Transactions
	- Definition: The total number of withdrawals count from the exchange.  
	- Description: 
		- High value indicates more transactions were made for **long-term holding in high possibility**. 
		- For derivative exchange, it could indicate the number of **withdrawals increased** to participate less in derivative trades.


- In-House Flow (Total)
	- Definition: The total amount of coins circulated within the exchange's wallets.

- In-House Flow (Mean)
	- Definition: The mean amount of coins per transaction circulated within the exchange's wallets.

- In-House Transactions
	- Definition: The number of transactions circulated within the exchange's wallets.




### 2.2.  Flow Indicator 
*Flow Indicator: on on-chain models to signal possible price movements by assessing the value of Bitcoin and allow investors and traders to operate with confidence.*

- Miners' Position Index (MPI)
	- Definition: the ratio of total miner outflow (USD) to its one-year moving average of total miner outflow (USD).  
	- Description:
		- Higher value shows that miners are sending more coins than usual which indicates possible selling.  
		- If miners send some proportion of their reserve at the same time, it could trigger a price drop.
	- Details:
		- MPI(Miners’ Position Index) is a z score of a specific period. The period range must be 2 days or more and if not, it will return an error. `mpi` is an index to understand miners’ behavior by examining the **total outflow of miners**. It highlights periods where the value of Bitcoin’s **outflow by miners on a daily basis** has historically been extremely high or low. 
		- MPI values above 2 indicate that most of the miners are selling Bitcoin. 
		- MPI values under 0 indicate that there is **less selling pressure** by miners.
	- [API](https://cryptoquant.com/docs#operation/getMPI)
- Exchange Whale Ratio
	- Definition: The ratio of the top 10 inflows to the total inflows of the exchange.
	- Description:
		- High values indicate whales are using the exchanges in large amount.



- Exchange Inflow CDD
- 
- Fund Flow Ratio
	- Definition: The ratio of coins transfers involving the exchange to the overall coins transfers network-wide.  
	- Description: 
		- High values indicate investors are actively using the exchanges.

- Exchange Stablecoins Ratio USD
	- Definition: Coins reserve(USD) divided by all stablecoins reserve held by the exchange.  
	- Description:
		- Low values mean buying power which leads to possible price rise.
- Exchange Stablecoins Ratio
	- Definition: Coins reserve divided by all stablecoins reserve held by the exchange.  
	- Description:
		- Low values mean buying power which leads to possible price rise.


- [Exchange Shutdown Index](https://cryptoquant.com/docs#operation/getExchangeShutdownIndex)
	- Definition: If there's no outflow from the exchange, the value is 1, otherwise 0.  
		Continuous appearance of '1' indicates exchange withdrawal system is not functioning.
	- Description:
		-  Stay Ahead of Exchange Hacks. See hacks as they happen by identifying sudden increases and become zero in exchange outflows and hedge against potential risk.



- Inflow CDD
	- Definition: [Coin Days Destroyed (CDD)](https://cryptoquant.com/asset/btc/chart/network-indicator/coin-days-destroyed-cdd) of coins destroyed by flowing into exchanges.  
High values indicate that more long-term holders moved their coins for the purpose of possible selling.  
This indicator is a noise-removed version of CDD with respect to exchange dumping signal.

- graph-wise
- Top-X
- Events
- Social Media
	- reddit active posts / twitter active posts




### 2.3 Market Indicator
1. Estimated Levarage Ratio (ELR)
	- Definition: The ratio of open interest divided by the reserve of an exchange.
	- ![[Pasted image 20220722155210.png]]

- Interpretation
	- Estimated Leverage Ratio indicates how much leverage is used by users on average. 
	- ELR for a derivative exchange tells us how much leverage is used by users on average. This information measures traders' **sentiment whether they take a high risk or low risk**.
	- By value itself as the degree of leverage of the market
		- High: Over Leveraged Market+ Possible Volatility
		- Low: Low Leveraged Market
	- By examining trend as the sentiment or tendency of total investors' urge to use leverage.
		- Increasing trend: Holding More Leverage
			- Increasing in values indicates more investors are taking high leverage risk in the derivatives trade. 
			- Also, if **ELR value is high compared to the last couple of days, it indicates traders are quite confident in their positions.** 
		- Decreasing trend: Taking off Leverage
			- Decreasing in values indicates more investors are taking off leverage risk in the derivatives trade. 
			- Also, if ELR value is low compared to the last couple of days, it indicates traders are changing their views or finishing their positions. 




2. Short Term Holder SOPR
	- Definition: evaluates the profit ratio of the whole market participants by comparing the value of outputs at the **spent time to created time.** 
		- In a simple way, you can estimate the distribution of spent transaction output is **in profit or not**. SOPR is calculated as the USD value of spent outputs at the **spent time(realized value)** divided by the USD value of spent outputs at the **created time(value at creation)**.
		- ![[Pasted image 20220722155857.png]]
	- Steps:
		1.  UTXO is transferred now
		2.  CryptoQuant locates the USD Value of the spent period and divide them by the  USD Value at the created time Simply put, SOPR = **Now** value/ Past value
		3. Categorize and put some figures separately by span time to conclude more specific meanings

	
	- Interpretation:
		- By Value itself
			- SOPR value greater than 1 ( SOPR > 1 ): It implies that the coins moved in a certain timescale are, on average, **selling at a profit**.
			- SOPR value of exactly 1 ( SOPR =1 ): It implies that the coins moved in a certain timescale are, on average, selling coins **at break even**.
			- SOPR value less than 1 ( SOPR < 1): It implies that the coins moved in a certain timescale are, on average, selling at a loss.
		- ![[Pasted image 20220722160133.png|350]]
	- By examining trend
		- SOPR Trending **Higher** implies profits are being **realized** and coins that were in **profit are being transferred** to others. Also, it could be implied that investors who sell their coins in profit are increasing their sell or market condition for sellers are getting **more profitable**.
		- SOPR Trending **Lower** implies losses are being realized and coins that were in loss are being transferred to others. Also, it could be implied that investors who sell their coins in loss are increasing their sell or market condition for sellers are getting less profitable
  - Investing Applied Scenario:
	  - Historically, in the middle of bull sentiment, the **market correction begins** right before the bull run begins and making SOPR drop below '1'. This could be the right time to buy before the bull run starts.
	  - Historically, in the middle of bear sentiment, the market correction begins right before the bear market starts making SOPR rise above '1'. This could be the **right time to sell before the bear market starts**.

- Why are some indicators modified?
	- 1) Can **less than an hour** long aged UTXO mean significance?(aSOPR)
		 - aSOPR stands for adjusted SOPR( Spent Output Profit Ratio) . 
		 - It derived from the standard SOPR by excluding UTXOs that has input-output span that are aged less than an hour long.
		 - If there are **too many** UTXO that are being generated recently, the indicator's value will be made equal to the number of 1 which would mean that **many UTXO are at even**.  
	 - 2) What if long/short aged UTXO specifically suffer from loss? (LTH-SOPR, STH-SOPR)
		 - LTH-SOPR stands for Long Term **Holder** - SOPR ( Spent Output Profit Ratio).  It derived from the standard SOPR by leaving only the UTXO that are **aged more than 155 days.**
		 - STH-SOPR stands for Short Term **Holder** - SOPR ( Spent Output Profit Ratio). It derived from the standard SOPR by leaving only the UTXO that are aged l**ess than 155 days and more than an hour aliv**e. 
	 - ![[Pasted image 20220722161623.png|350]]

3. Long Term Holder SOPR

4. Adjusted SOPR (aSOPR)

5. SOPR Ratio (LTH-SOPR/STH-SOPR)


6. Spent Output profit Ratio


7. MVRV Ratio (three halvings)
	- Definition: MVRV (Market Value to Realized Value) ratio is defined as an asset's market capitalization divided by [realized capitalization](https://cryptoquant.com/docs/#operation/getCapitalization).
	- ![[Pasted image 20220722161715.png]]
	- Interpretation:
		- By comparing two valuation methods, the MVRV ratio can tell us to get a sense of whether the price is fair or not, which means it is useful to **get market tops and bottoms**. 
		- It is important to note that historically, it has been an **outstanding indicator to spot market top/bottom or local top/bottom** that occurred through **three halvings**.

8. Stablecoin Supply Ratio (SSR)
	- Definition: ratio of the Market Cap of BTC divided by the Market Cap of all Stablecoins.
	- ![[Pasted image 20220722162029.png]]
	- Interpretation
		- In understanding SSR, understanding the function of stablecoin and its assumption should be done.
		- First, *stablecoins play an important role in the cryptocurrency market as a fiat currency like USD in the regulated market. This is because fiat currencies like USD as a supplier of liquidity have a lot of regulation issues.* 
		- Second, *SSR is easy to understand when there is an assumption that the market is a **closed system** containing only cryptocurrencies and stablecoins.*  
		- The relationship between BTC and Stablecoins is like **seasaw** and provide valuable insight on **who has more weight at the moment**. 
	- By value itself
		- It shows comparative power status between BTC and Stablecoin by comparing market cap
		- High : Low Potential Buying Pressure - Bearish
			- High values mean **Low Stablecoin supply** compared to the market cap of BTC indicating potential **low buying pressure** and possible price drop. 
		- Low  : High Potential Buying Pressure - Bullish 
			- Low values mean high Stablecoin supply compared to the market cap of BTC indicating potential buying pressure and possible price rise. 
	- By examining trend 
		- It shows the level of Exchange **Activeness & Volatility**
		- Increasing trend : Slowing down status of stablecoin's buying power - Bearish or **sideways sentiment**
		- Decreasing trend : Rising status of stablecoin's buying power - Bullish
 NoteAdditional **stablecoins could be minted anytime disrupting the assumption that crypto market is a closed system.** However, as crypto market continues to expand, additional mint would gradually lose its impact on the model.
As time passes, the degree of values' meaning could differ on level. 




9. Realized Price
	- Definition: Realized Cap divided by the total coin supply. It measures the average price weighted by the supply of what the entire market participants paid for their coins. It can be interpreted as the **on-chain support or resistance price.**


10. Realized Price - UTXO Age Bands
	- Definition: a set of realized prices along with age bands. The metrics help us to overview **each cohort’s holding** behavior by overlaying a set of different realized prices. Realized price is calculated as Realized Cap divided by the total supply.



### 2.4 Network Indictator
1. Net Unrealized Profit/Loss (NUPL)
2. Net Unrealized Profit (NUP)
3. Net Unrealized Loss
4. Supply-Adjusted CDD
	- Definition:  CDD value adjusted by supply. It is calculated as the value of CDD divided by total supply.  
	- Description: 
		- It is adjusted CDD for better tracking of long-term holders.  
		- High values indicate long-term holders sold more proportional to indicator's values.
	- 
5. Coin Days Destroyed (CDD)
	- Definition: Coin Days evaluates the number of coins that are not being spent, which gives more weight to estimate long-term-holder(LTH) position. When that coin is spent, the coin is considered "destroyed," and is being updated on Coin Days Destroyed(CDD) metric. CDD is the sum of products of spent transaction output alive days and its value.
	- ![[Pasted image 20220722134409.png]]
	- Interpretation: 
		- By value itself
			- **High**: Long-held coins are moving in great amounts -**Volatility Risk or Possible Trend Reversal**
			- A large number of alive days are destroyed which indicates that long-term holders' coins are exposed to selling. Since coins held long have a huge impact on the market,  
			- **Low**: Long-held coins are moving in less amount 
		- By examining trend
			- Increasing trend:  Increasing selling pressure: Long term holders' coins are continuously being sold
			- Decreasing trend: Decreasing selling pressure: Long term holders' coins are slowing down in movement
		- Note on CDD
			- CDD gives more weight to 
				1) **longer-lived** UTXO 
				2) Amount of UTXO is holding BTC. 
			Weighting more on these makes the indicator sensitive to long-term holders’ movement and show sentiment & behavior. 
		- Explanation on creation and destruction of UTXO(s): For every coin that has not been spent on that day, it accumulates one "Coin Day." To understand the concept of "Coin Day" better, check the examples below.
			- A UTXO for 1 BTC that has not been spent for 10-days has accumulated 10 coin days.
			- A UTXO for 0.5 BTC that has not been spent for 100-days has accumulated 50 coin days.
			- A UTXO for 8 BTC that has not been spent for 6-hours (1/4 day) has accumulated 2 coin days.
		- When that coin is spent, the coin is considered "destroyed," and is being updated on CDD metric.
			- CDD: An indicator reflects market participants who have been in the bitcoin on-chain for longer.
			- Supply Adjusted CDD: Normalized CDD by supply total.
			- Average Supply Adjusted CDD: Average value of Supply-Adjusted CDD since genesis block.
			- Binary CDD: Signal whether the current Supply-Adjusted CDD is larger than its average or not.

6. Average Supply-Adjusted
	- Definition:  The historical average value of Supply-Adjusted CDD after generation block.  
	- Description:
		- It indicates how much long-term holders' activeness of movement was higher or lower than average.


When UTXO is destroyed, Coin Days Destroyed (CDD) is calculated as the sum value of the number of days between created and spent multiplied by UTXO amount.  
This indicator gives more weight to the longer-lived UTXO making the indicator sensitive to long-term holders' movement.  
CDD provides the sentiment of long-term holders and behavior.  
High values indicate long-term holders moved their coins for the purpose of possible selling.'

7. Binary CDD
	- Definition: binary value and if Supply Adjusted Coin Days Destroyed (Supply-Adjusted CDD) is larger than average Supply-Adjusted CDD, Binary Coin Days points to '1' and points to '0' if not.  
	- Description:
		- It shows whether long-term holders' movements are higher or lower than average.  
		- High density of value pointing '1' indicates long-term holders moved their coins for possible selling.

8. Supply Adjusted Dormancy
	- Definition: supply adjusted average number of **destroyed days of moved** coins.  
	- Description:
		- It is calculated by dividing **Average Dormacy by the total amount of supplies**.  
		- Adjustment was made due to **increasing** supply of coins.  
		- Its value increase when l**ong-term holders move or possibly sell** their coins indicating possible price drop.
	- Details:  
		- (average_dormancy) is the average number of days destroyed per coin transacted. 
		- Supply-Adjusted Average Dormancy (sa_average_dormancy) is the average dormancy normalized by supply total, where supply total increases as more blocks mined.
	- API: https://cryptoquant.com/docs#operation/getPNLSupply

8. Average Dormancy 
	- Definition:  The average number of destroyed days of moved coins.  
	- Description:
		- It is calculated by dividing **CDD** by the total amount of movement of coins.  
		- Its value increase when long-term holders move or possibly sell their coins indicating possible price drop.
	- Input: 
		- CDD; 
		- total amount of movement of coins.  
	- API: https://cryptoquant.com/docs#operation/getDormancy


9. NVT Golden Cross
	- Definition: Modified index of Network Value to Transaction(NVT) that provides local tops/bottoms.  
	- Description:
		- Values over '2.2' indicate overbuying (possible top) 
		- under '-1.6' indicate overselling (possible bottom).
	- API: https://cryptoquant.com/docs#operation/getNVTGoldenCross


10. Puell Multiple
	- Definition: 
		- The ratio of the **daily value of the issued coin** in USD divided by 365 days moving average of the daily value of issued coins in USD.
		- ![[Pasted image 20220722141529.png]]
	- Description: 
		- Predicting Price Tops and Bottoms
			- Values over ‘4’ : Short Signal
				- If Puell multiple rises, it indicates that price=Miner's revenue is increasing significantly compared to the cost they put in. In this phase, bitcoin soared to point where Miner's revenue far exceeds the cost they put in. If we put regard bitcoin's true value with miners' cost (POW) and hashrate, this could indicate that bitcoin is overpriced.
				- In other words, this could indicate that price is overvalued along with the increasing miner's motive to sell.
			- Values under ‘0.5’ : Long Signal
				- If Puell multiple decreases, it indicates that price=Miner's revenue is decreasing significantly compared to the cost they put in. In this phase, bitcoin prices plunged to the point where miners can't handle the cost of electricity making some miners stop their mining action.
				- In other words, this could indicate that price is undervalued along with the increasing miner's motive to hold their bitcoin reserve.
		- By examining trend, it shows **miners' short-term revenues relative to long-term profits**.
			- Increasing trend : Marketcap(Price) is heating up compared to miners' cost
			- Decreasing trend : Marketcap(Price) is cooling down compared to miners' cost
			- ![[Pasted image 20220722141833.png|400]]



- Input


11. NVT Ratio
	- Definition: NVT Golden Cross (NVT_GC) is a [Bollinger-band](https://en.wikipedia.org/wiki/Bollinger_Bands)-like signaling indicator based on NVT, defined as the following equation.	- ![[Pasted image 20220722142139.png]]
	- Description
		- NVT Golden Cross targets to generate short or long signals by comparing the short-term trend of NVT and the long-term trend of NVT. 
		- This **leading indicator** predicts the appearances of local tops and bottoms, which helps traders to take their short or long positions.
		- Predicting Local Tops and Bottoms
			- Values over ‘2.2’ : Short Signal: If the short-term trend is way greater than the long-term trend is, the network can be interpreted as overpriced and will soon revert to mean value, meaning short signal. 
			- Values under ‘-1.6’ : Long Signal: If the long-term trend is way greater than the short-term trend is, the network can be interpreted as under-priced and will soon revert to mean value, meaning long signal. 
		- comparative trend difference between long-term and short-term.
			- Increasing trend : Marketcap(Price) is heating up compared to transaction volume
			- Decreasing trend : Marketcap(Price) is cooling down compared to transaction volume
			- ![[Pasted image 20220722144417.png|400]]
> Bollinger Bands: *display a graphical band (the envelope maximum and minimum of moving averages, similar to Keltner or Donchian channels) and volatility (expressed by the width of the envelope) in one two-dimensional chart.  Two input parameters chosen independently by the user govern how a given chart summarizes the known historical price data, allowing the user to vary the response of the chart to the magnitude and frequency of price changes, similar to parametric equations in signal processing or control systems. Bollinger Bands consist of an N-period moving average (MA), an upper band at K times an N-period standard deviation above the moving average (MA + Kσ), and a lower band at K times an N-period standard deviation below the moving average (MA − Kσ). The chart thus expresses arbitrary choices or assumptions of the user, and is not strictly about the price data alone.*







12. Network Value to Metcalfe Ratio(NVM) 
	- Definition: the ratio of the log of market capitalization divided by the log of the square of daily active addresses in the specified window.
		- ![[Pasted image 20220722144815.png]]
	- Description:
		- evaluates the fair value of the blockchain network by applying [Metcalfe's Law](https://en.wikipedia.org/wiki/Metcalfe's_law) where the law claims that the value of the **network is proportional to the square of the number of active users.** 
		-   **High values : Overvalued network** The network is **overvalued** by the interpretation where the price is too high compared to the low number of active addresses
		-   **Low values** **: Undervalued network** The network is **undervalued** by the interpretation where the price is too low compared to the high number of active addresses
	- Use Case: RSI based market spotting local tops and bottoms
		- measuring the **relative strength of an upward trend and downward trend**. We **apply RSI to NVM** for spotting the market's local **tops** and bottoms by **thresholding**. As you can see in the figure below, RSI of NVM quite correctly spots local tops and bottoms in a robust way.
		- ![[Pasted image 20220722145156.png|300]]


13. Stock-to-Flow Ratio
	- Definition: ratio of currently circulating coins divided by newly supplied coins.
	- Interpretation:
		- SF ratio assumes that the **scarcity** of the coin drives the price of the coin. The analysis on SF ratio is first presented by a pseudonymous [Dutch institutional investor](https://100trillionusd.github.io/) who operates under the Twitter account “[PlanB](https://twitter.com/100trillionUSD)”. By looking at SF ratio as a chart, we can spot where the market regime is.
		- ![[Pasted image 20220722150016.png|200]]
		- If Newly supplied coins decrease, SF Ratio rises.
		- If circulating coins rises, SF Ratio rises.
	- Use Case:  Statistical analysis on SF ratio
		- The log of **SF ratio** is in a linear relationship with **the log of the price**. We reproduce the results of what they claim and as a result, shown in the figure below, SF ratio and price are in a linear relationship (not perfectly but in some sense) with significant statistics (**p-value under 0.01, R-square over 90%**).
		- Following the above linear statistics (trend and intercept), we can plot how closely they are related in a time-series manner. With this graph, we can recognize that the **current price is in what regime recently**.


14. Stock to Flow Reversion
	- Definition:  ratio of the price of BTC divided by SF ratio.
	- Formula: ![[Pasted image 20220722150521.png]]
	- Interpretation: 
		- measures the relative difference between the market price and SF ratio. SF ratio so far correctly estimates the **price trend**, which means the p**rice deviation from SF ratio can be an opportunity to bet**. 
		- If SF reversion is too high compared to the price, the market price would be corrected soon, meaning a **bearish** moment.
	- Use Case: Predicting market 
		- 1st build a linear regression model of SF reversion to the price to align **two variables**. 
		- After aligning both in a single graph shown below, we can clearly see the deviations of SF reversion to the price and those points clearly indicate bullish (green boxes) and bearish (red boxes) regimes respectively.
		- ![[Pasted image 20220722151539.png|300]]

15. MCA (Mean Coin Age)
	- Definition: the mean value of products of coin unspent transaction output (UTxO) alive days and its value.
	- ![[Pasted image 20220722151820.png]]
	- Interpretation
		- MCA is similar to **CDD** but focuses more on **unspent transaction output**. Mean Coin Dollar Age is the sum value of products of 
			- coin unspent transaction output alive days, value, and the price at the created time. This indicator enables estimating the Long-Term Holders' portion.
		- MCA is the average age of UTxO. MCA drop **implies** the massive move of Bitcoin UTxOs that **haven't moved** for a long time.
		- MCDA is an indicator weighted by UTxO created price(USD) to the MCA.


16. Mean Coin Dollar Age
	- Definition: the mean value of products of coins unspent transaction output alive days, value, and price (Unit: USD) at the created time.  
	- Description:
		- '**Alive days**' means the days certain coins was kept **in a single wallet**.  
		- Sudden **decrease** in values indicate coins that were dormant moved in mass.
17. 
18. 


### 2.5 Miner Flows
1. MinerReserve: 
	- Description: Amount of coins held by the affiliated miners' wallets.  
	- Description: 
		- This value indicates the reserve that miners has **not yet sold**.  
		- When miners start selling, it could lead to price drop.


2. Miner Reserve USD

The USD value of coins held by the affiliated miners' wallets.  
This value indicates the reserve miners are holdings that are not yet sold.  
When miners start selling, it could lead to price drop.



3. Miner Outflow
	- Definition: The outflow of BTC from mining pool wallets. We define mining pool wallets in our metrics as all participants in the mining pool including individual miners.
	- Types
		- Outflow Total: The total amount of BTC transferred from the miner.
		- Outflow Mean: The mean amount of BTC per transaction sent from the miner (divided by the Transactions Count Outflow).
		- Outflow Top10: The total BTC amount of the top 10 transactions outflow from the miner
		- Outflow Mean(MA7): The 7 days moving average of mean BTC outflow from the miner.
	- Interpretation: 
		- By value itself
			- **High** : A lot of miners' coins are exposed to selling - **Bearish** 
			- **Low :** only a few of miners' coins are exposed to selling - **Bullish**
		- By examining trend
			- Increasing : Miners' selling power is increasing - Bearish
				-  Moving to the exchanges for possible selling - Bearish
					- includes the purposes of selling to cover the cost or to prepare for possible sell. Both cases are correlated to sell action which naturally lead to interpret this reason to the price drop which indicates a bearish sign.
			- Decreasing : Miners' selling power is decreasing - Bullish
			- Internal wallet movement - Neutral 
				- Moving their coins to miners' wallets excluding trading purposes has a neutral sign. It could be done to security issues. 


4. Miner Inflow (Total)
	- Definition: The total amount of coins transferred to the affiliated miners' wallets.  
	- Description:
		- It shows the amount of coins that are received as a **reward** for mining and the coins they purchased.



5. Miner Netflow Total
	- Definition: The difference between coins flowing into and out of the **exchange**. ( Inflow - outflow = Netflow) 
	- Description: 
		- Positive value indicates miner reserve in increasing.

6. Miner Withdrawing Transaction
	- Definition: The total number of withdrawals from the affiliated miners' wallets.  
	- Description: 
		- It indicates how **often** miners send their coins.  
		- If miners send some proportion of their reserve at the same time, it could trigger a price drop.


7. Miner Withdrawing Addresses
	- Definition: The number of **coins addresses making outflow transactions** from the affiliated miners' wallets.  
	- Description: 
		- It shows how many miners are **sending** their coins.  
		- If miners send some proportion of their reserve at the same time, it could trigger a price drop.
	-   View API Docs

8. Miner Depositing Addresses
	- Definition: The number of coins addresses making **inflow** transactions to the affiliated miners' wallets.

9. Miner In-House Flow Total - All Miners
	- Definition: The total amount of coins **circulated within** the affiliated miners' wallets.

10. Miner In-House Flow Mean - All Miners
	- Definition: The mean amount of coins per transaction circulated within the affiliated miners' wallets.

11. Miner In-House Transactions  - All Miners
The **number of transaction**s circulated within the affiliated miners' wallets.


### 2.6 Derivatives

### 2.7 Fund Data
### 2.8 Market Data


### 2.9 Active Addresses 


### 2.10 Fees and Revenue
Fee per Transaction:

Median Fee per Transaction:
	- Definition: The median fee per 
Sum of all Fee USD
	- Definition: The **sum of all fees** that are paid to coins miners
- Fees to Reward Ratio: 
	- Definition: The percentage of fee in total block reward. Values are between 0 and 1.

### 2.11 network Status
Blocks Mined:
	- Definition: The number of blocks generated in a **given window**.
Mean Block Size:
	-   Definition: The average time between blocks generated in seconds.
Mean Block Intervals: 
	-   Definition: The average time between blocks generated in seconds.
Mean Hashrate: 
	- Definition: The mean of hashes that miners calculate per second across all miners in the network
UTXO count
	- Definition: The total number of unspent transaction outputs existing at a specified point.
	- 

### 2.12 Supply
2. supply
	- Definition: 
	- Type
		- `supply_total`: total amopunt of bitcoins in existence (sum of all bitcoins issued by coinbase reward)
		- `supply_new`: the amount of newly issued token in a given window
- 
4. Velocity
	- Definition: Velocity is calculated by dividing the **trailing** 1 year estimated transaction volume(the **cumulated sum of transferred tokens**) by **current** supply.
	- Description:
		- a metric that explains how actively is money circulating in the market.
	
### 2.13 Transactions
1. Transaction Count
	- Types:
		- Mean Transaction Count: the mean number of transactions per block

### 2.14 Inter Entity Flows
1. Exchange to Exchange Flow
	- Definition: The total amount of coins transferred from the exchange to other exchange wallets.
	- Description:
		- The mean value is the **Flow Total** divided by the **Transactions Count Flow**. Data entries were collected from the first transaction between two entities.
	- Types
		- Flow Total: The total amount of BTC transferred from the exchange to other exchange wallets.
		- Flow Mean: The mean amount of BTC transferred from the exchange to other exchange wallets.
		- Transactions Count Flow: The number of transactions from exchange to other exchange wallets
2. Exchange Address Count



### 2.15 Bank Flows
1. Bank Reserver
	- Definition: The amount of coins held by the digital asset bank.
	- Description:
		- It shows the activeness of digital asset banks.
2. Bank Inflow 
	- Definition: The amount of coins held by the digital asset bank.
	- Description:
		- It shows the activeness of digital asset banks.

3. Bank Outflow 
	- Definition: The amount of coins held by the digital asset bank.
	- Description:
		- It shows the activeness of digital asset banks.
2. Bank Inflow 
	- Definition: The amount of coins held by the digital asset bank.
	- Description:
		- It shows the activeness of digital asset banks.
		- 



1





### 3.  System-wise1
- mining difficulty
- mining shares
- Fee
- Miner



still use top 2000 


cumulative proportion of top-N addresses and straight line of equal distribution, *static decentralization degree*

Every address own the same amount
- $\mathcal{C}_r(x)$
	- real case 
- $\mathcal{C}_e(x)$
	- ideal case

![[Pasted image 20220721224256.png]]



# 3. S



### 4. Network Stats

1. Block Mined
	- Definition:   The number of blocks generated in a given window.
2. mean size
	- Definition: (in bytes ) of all blocks generated
3. mean interval
	- Definition:   The average time between blocks generated in seconds.
4. Hashrate:
	- Definition: miners calculate per second across all miners in the network.
5. Difficulty
	- Definition: mean difficulty of mining a new block.
6. UTXO Count
	- Definition: The total number of unspent transaction outputs existing at a specified point.




- **decentralizaiton**
	- greater the **Degree Centrality**, the more important the node due to involvement in more transactions.
	a node with high PageRank score in a financial network is considered to serve as intermediary of three kinds: 
	1. (I) financial intermediary, serving as middleman for financial transactions to create efficient markets and to lower busi- ness cost; 
	2. (II) credibility intermediary, offering trust to other nodes to enable transactions; and
	3. (III) information intermediary, providing information for asset pricing, bidding, matching and others based on data from large transaction volume.



notion of **dispersion** and use it on each metric to evaluate the decentralization of the transaction networks. We define dispersion $𝑑_𝑚$ for a chose metric 𝑚 as follows
Where 𝐻𝑚 , 𝐿𝑚 and 𝐴𝑉 𝐺𝑚 stand for the **greatest**, the **least** and the **average** value for metric 𝑚. 
The higher the dispersion, the more pronounced the control of transactions by a subgroup within the whole graph, and the less the dynamic decentralization of BTC transaction network.

![[Pasted image 20220721230540.png|400]]
As we observe these three metrics, we have the following find- ings. 
First of all, it is observed that for most of the time, **the dispersion are above 20**, which means only **fewer than 5 addresses** were in uniquely important positions in terms of controlling transactions in the network.


1. Degree Centrality
	- like in the case of hyper-links between webpages.

2. PageRank
	- Transactions can be viewed as trust endorsement. The higher the PageRank score of a node, the more trust endorse- ment for the node as manifested by BTC transactions transferring the asset to this node.

In general, a node with high PageRank score in a financial network is considered to serve as intermediary of three kinds: 
- (I) **financial** intermediary, serving as middleman for financial transactions to create efficient markets and to lower busi- ness cost; 
- (II) **credibility** intermediary, offering **trust** to other nodes to enable transactions; and 
- (III) **information** intermediary, providing information for asset pricing, bidding, matching and others based on data from **large transaction** volume.



3. Herfindahl-Hirschman Index (HHI) is a classic measure of **market concentration** and has been widely used to evaluate market **efficiency**.


Where h𝑖 is the BTC held by entity 𝑖, 𝐶 is the total BTC minted by that time. The higher the HHI, the **more significant the market concentration**, and the **less the decentralization**. 
In general, a market with an **HHI** < 1,500 is considered to be a **competitive** market, an HHI of 1,500 to 2,500 a **moderately concentrated market,**




### 5. Inter Entity Flows


### 6. Bank Flows
