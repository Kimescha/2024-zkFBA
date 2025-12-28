# Zeequent Batch Auctions



| **Price** | **Bid ⛰️** | **Ask ⛰️** | **Bid Depth** | **Ask Depth** | Bid Surplus $\mathbb{Z}_+$ | Ask Surplus $\mathbb{Z}_+$ | **Trade Vol** | MCV  | **Delta** |
| --------- | --------- | --------- | ------------- | ------------- | -------------------------- | -------------------------- | ------------- | ---- | --------- |
| 0         | 0         | 1         | 8             | 1             | 7                          | 0                          | 1             | 4    | 7         |
| 1         | 1         | 0         | 8             | 1             | 7                          | 0                          | 1             | 4    | 7         |
| 2         | 2         | 1         | 7             | 2             | 5                          | 0                          | 2             | 4    | 5         |
| 3         | 0         | 2         | 5             | 4             | 1                          | 0                          | 4             | 4    | 1         |
| 4         | 1         | 0         | 5             | 4             | 1                          | 0                          | 4             | 4    | 1         |
| 5         | 0         | 2         | 4             | 6             | 0                          | 2                          | 4             | 4    | 2         |
| 6         | 1         | 1         | 4             | 7             | 0                          | 3                          | 4             | 4    | 3         |
| 7         | 3         | 0         | 3             | 7             | 0                          | 4                          | 3             | 4    | 4         |



BidsDepth = Accumulate[Bids]

AsksDepth = Accumulate[Asks]

TradeVol:

​	BidDepth=BidSuprlus+TradeVol

​	AskDepth=AskSurplus+TradeVol

​	Positive[BidDepth]

​	Positive[AskDepth]

​	BidSuprlus*AskSurplus=0

Plateau:

​	MCV:=4

​	MCP-LeftInterval:=3

​	MCP-RightInterval:=6

​	TradeVol[MCP-LeftInterval]=MCV

​	TradeVol[MCP-RightInterval]=MCV

​	Positive[TradeVol - MCV] 

​		Alt: Selector*(TradeVol-MCV)=0 and some work that selector is correct shape (blocks of 1's in sea of 0's)

​		Alt 2:Selector[i]-Selection[i+1] is a multiset of {1,-1,0,0,0,0,...} with permutation argument 

Plateau Cliffs:

​	MCV=TradeVol[MCP-LeftInveral-1]+1+Slack

​	MCV=TradeVol[MCP-RightInveral+1]+1+Slack

​	Positive[Slack]	

Delta=BidSurplus+AskSurplus

​	Same as TradeVol plateau
