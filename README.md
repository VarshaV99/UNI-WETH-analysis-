{
  ethereum(network: ethereum) {
    dexTrades(
      options: {limit: 10, desc: ["block.height", "tradeIndex"]}
      protocol: {is: "Uniswap v2"}
      buyCurrency: {is: "0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984"}
      sellCurrency: {is: "0xc02aaa39b223fe8d0a0e5c4f27ead9083c756cc2"}
    ) {
      block {
        height
        timestamp {
          iso8601
        }
      }
      transaction {
        hash
      }
      tradeIndex
      buyCurrency {
        symbol
        address
      }
      buyAmount
      sellCurrency {
        symbol
        address
      }
      sellAmount
      maker {
        address
        annotation
      }
      taker {
        address
        annotation
      }
      protocol
      smartContract {
        address {
          address
          annotation
        }
        contractType
      }
    }
  }
}
