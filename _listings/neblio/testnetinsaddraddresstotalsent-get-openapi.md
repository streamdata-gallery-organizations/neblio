---
swagger: "2.0"
x-collection-name: Neblio
x-complete: 0
info:
  title: Neblio Returns total sent by address in sats
  description: Returns total NEBL sent by address in satoshis
  version: 1.0.0
host: ntp1node.nebl.io
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /ntp1/tokenid/{tokensymbol}:
    get:
      summary: Returns the tokenId representing a token
      description: Translates a token symbol to a tokenId if a token exists with that
        symbol on the network
      operationId: getTokenId
      x-api-path-slug: ntp1tokenidtokensymbol-get
      parameters:
      - in: path
        name: tokensymbol
        description: Token symbol
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - TokenId
      - Representing
      - Token
  /ntp1/broadcast:
    post:
      summary: Broadcasts a signed raw transaction to the network
      description: Broadcasts a signed raw transaction to the network. If successful
        returns the txid of the broadcast trasnaction.
      operationId: broadcastTx
      x-api-path-slug: ntp1broadcast-post
      parameters:
      - in: body
        name: body
        description: Object representing a transaction to broadcast
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Broadcasts
      - Signed
      - Raw
      - Transaction
      - To
      - Network
  /ntp1/addressinfo/{address}:
    get:
      summary: Information On a Neblio Address
      description: Returns both NEBL and NTP1 token UTXOs held at the given address.
      operationId: getAddressInfo
      x-api-path-slug: ntp1addressinfoaddress-get
      parameters:
      - in: path
        name: address
        description: Neblio Address to get information on
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Information
      - "On"
      - Neblio
      - Ress
  /ntp1/transactioninfo/{txid}:
    get:
      summary: Information On an NTP1 Transaction
      description: Returns detailed information regarding an NTP1 transaction.
      operationId: getTransactionInfo
      x-api-path-slug: ntp1transactioninfotxid-get
      parameters:
      - in: path
        name: txid
        description: Neblio txid to get information on
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Information
      - "On"
      - NTP1
      - Transaction
  /ntp1/tokenmetadata/{tokenid}:
    get:
      summary: Get Issuance Metadata of Token
      description: Returns the metadata associated with a token at time of issuance.
      operationId: getTokenMetadataOfIssuance
      x-api-path-slug: ntp1tokenmetadatatokenid-get
      parameters:
      - in: path
        name: tokenid
        description: TokenId to request metadata for
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Issuance
      - Metadata
      - Of
      - Token
  /ntp1/tokenmetadata/{tokenid}/{utxo}:
    get:
      summary: Get UTXO Metadata of Token
      description: Returns the metadata associated with a token for that specific
        utxo instead of the issuance transaction.
      operationId: getTokenMetadataOfUtxo
      x-api-path-slug: ntp1tokenmetadatatokenidutxo-get
      parameters:
      - in: path
        name: tokenid
        description: TokenId to request metadata for
      - in: path
        name: utxo
        description: Specific UTXO to request metadata for
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - UTXO
      - Metadata
      - Of
      - Token
  /ntp1/stakeholders/{tokenid}:
    get:
      summary: Get Addresses Holding a Token
      description: Returns the the the addresses holding a token and how many tokens
        are held
      operationId: getTokenHolders
      x-api-path-slug: ntp1stakeholderstokenid-get
      parameters:
      - in: path
        name: tokenid
        description: TokenId to request metadata for
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Resses
      - Holding
      - Token
  /ntp1/issue:
    post:
      summary: Builds a transaction that issues a new NTP1 Token
      description: Builds an unsigned raw transaction that issues a new NTP1 token
        on the Neblio blockchain.
      operationId: issueToken
      x-api-path-slug: ntp1issue-post
      parameters:
      - in: body
        name: body
        description: Object representing the token to be created
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Builds
      - Transaction
      - That
      - Issues
      - New
      - NTP1
      - Token
  /ntp1/sendtoken:
    post:
      summary: Builds a transaction that sends an NTP1 Token
      description: Builds an unsigned raw transaction that sends an NTP1 token on
        the Neblio blockchain.
      operationId: sendToken
      x-api-path-slug: ntp1sendtoken-post
      parameters:
      - in: body
        name: body
        description: Object representing the token to be sent
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Builds
      - Transaction
      - That
      - Sends
      - NTP1
      - Token
  /ntp1/burntoken:
    post:
      summary: Builds a transaction that burns an NTP1 Token
      description: Builds an unsigned raw transaction that burns an NTP1 token on
        the Neblio blockchain.
      operationId: burnToken
      x-api-path-slug: ntp1burntoken-post
      parameters:
      - in: body
        name: body
        description: Object representing the token to be burned
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Builds
      - Transaction
      - That
      - Burns
      - NTP1
      - Token
  /ins/tx/send:
    post:
      summary: Broadcasts a signed raw transaction to the network (not NTP1 specific)
      description: Broadcasts a signed raw transaction to the network. If successful
        returns the txid of the broadcast trasnaction.
      operationId: sendTx
      x-api-path-slug: instxsend-post
      parameters:
      - in: body
        name: body
        description: Object representing a transaction to broadcast
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Broadcasts
      - Signed
      - Raw
      - Transaction
      - To
      - Network
      - (not
      - NTP1
      - Specific)
  /ins/block/{blockhash}:
    get:
      summary: Returns information regarding a Neblio block
      description: Returns blockchain data for a given block based upon the block
        hash
      operationId: getBlock
      x-api-path-slug: insblockblockhash-get
      parameters:
      - in: path
        name: blockhash
        description: Block Hash
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Information
      - Regarding
      - Neblio
      - Block
  /ins/block-index/{blockindex}:
    get:
      summary: Returns block hash of block
      description: Returns the block hash of a block at a given block index
      operationId: getBlockIndex
      x-api-path-slug: insblockindexblockindex-get
      parameters:
      - in: path
        name: blockindex
        description: Block Index
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Block
      - Hash
      - Of
      - Block
  /ins/tx/{txid}:
    get:
      summary: Returns transaction object
      description: Returns NEBL transaction object representing a NEBL transaction
      operationId: getTx
      x-api-path-slug: instxtxid-get
      parameters:
      - in: path
        name: txid
        description: Transaction ID
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Transaction
      - Object
  /ins/rawtx/{txid}:
    get:
      summary: Returns raw transaction hex
      description: Returns raw transaction hex representing a NEBL transaction
      operationId: getRawTx
      x-api-path-slug: insrawtxtxid-get
      parameters:
      - in: path
        name: txid
        description: Transaction ID
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Raw
      - Transaction
      - Hex
  /ins/addr/{address}:
    get:
      summary: Returns address object
      description: Returns NEBL address object containing information on a specific
        address
      operationId: getAddress
      x-api-path-slug: insaddraddress-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Address
      - Object
  /ins/addr/{address}/balance:
    get:
      summary: Returns address balance in sats
      description: Returns NEBL address balance in satoshis
      operationId: getAddressBalance
      x-api-path-slug: insaddraddressbalance-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Address
      - Balance
      - In
      - Sats
  /ins/addr/{address}/unconfirmedBalance:
    get:
      summary: Returns address unconfirmed balance in sats
      description: Returns NEBL address unconfirmed balance in satoshis
      operationId: getAddressUnconfirmedBalance
      x-api-path-slug: insaddraddressunconfirmedbalance-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Address
      - Unconfirmed
      - Balance
      - In
      - Sats
  /ins/addr/{address}/totalReceived:
    get:
      summary: Returns total received by address in sats
      description: Returns total NEBL received by address in satoshis
      operationId: getAddressTotalReceived
      x-api-path-slug: insaddraddresstotalreceived-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Total
      - Received
      - By
      - Address
      - In
      - Sats
  /ins/addr/{address}/utxo:
    get:
      summary: Returns all UTXOs at a given address
      description: Returns information on each Unspent Transaction Output contained
        at an address
      operationId: getAddressUtxos
      x-api-path-slug: insaddraddressutxo-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - ""
      - UTXOs
      - At
      - Given
      - Address
  /ins/addr/{address}/totalSent:
    get:
      summary: Returns total sent by address in sats
      description: Returns total NEBL sent by address in satoshis
      operationId: getAddressTotalSent
      x-api-path-slug: insaddraddresstotalsent-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Total
      - Sent
      - By
      - Address
      - In
      - Sats
  /ins/txs:
    get:
      summary: Get transactions by block or address
      description: Returns all transactions by block or address
      operationId: getTxs
      x-api-path-slug: instxs-get
      parameters:
      - in: query
        name: address
        description: Address
      - in: query
        name: block
        description: Block Hash
      - in: query
        name: pageNum
        description: Page number to display
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Transactions
      - By
      - Block
      - Address
  /ins/sync:
    get:
      summary: Get node sync status
      description: Returns information on the node's sync progress
      operationId: getSync
      x-api-path-slug: inssync-get
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Node
      - Sync
      - Status
  /ins/status:
    get:
      summary: Utility API for calling several blockchain node functions
      description: Utility API for calling several blockchain node functions - getInfo,
        getDifficulty, getBestBlockHash, getLastBlockHash
      operationId: getStatus
      x-api-path-slug: insstatus-get
      parameters:
      - in: query
        name: q
        description: Function to call, getInfo, getDifficulty, getBestBlockHash, or
          getLastBlockHash
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Utility
      - APIcalling
      - Several
      - Blockchain
      - Node
      - Functions
  /testnet/ins/tx/send:
    post:
      summary: Broadcasts a signed raw transaction to the network (not NTP1 specific)
      description: Broadcasts a signed raw transaction to the network. If successful
        returns the txid of the broadcast trasnaction.
      operationId: testnet_sendTx
      x-api-path-slug: testnetinstxsend-post
      parameters:
      - in: body
        name: body
        description: Object representing a transaction to broadcast
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Broadcasts
      - Signed
      - Raw
      - Transaction
      - To
      - Network
      - (not
      - NTP1
      - Specific)
  /testnet/ins/block/{blockhash}:
    get:
      summary: Returns information regarding a Neblio block
      description: Returns blockchain data for a given block based upon the block
        hash
      operationId: testnet_getBlock
      x-api-path-slug: testnetinsblockblockhash-get
      parameters:
      - in: path
        name: blockhash
        description: Block Hash
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Information
      - Regarding
      - Neblio
      - Block
  /testnet/ins/block-index/{blockindex}:
    get:
      summary: Returns block hash of block
      description: Returns the block hash of a block at a given block index
      operationId: testnet_getBlockIndex
      x-api-path-slug: testnetinsblockindexblockindex-get
      parameters:
      - in: path
        name: blockindex
        description: Block Index
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Block
      - Hash
      - Of
      - Block
  /testnet/ins/tx/{txid}:
    get:
      summary: Returns transaction object
      description: Returns NEBL transaction object representing a NEBL transaction
      operationId: testnet_getTx
      x-api-path-slug: testnetinstxtxid-get
      parameters:
      - in: path
        name: txid
        description: Transaction ID
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Transaction
      - Object
  /testnet/ins/rawtx/{txid}:
    get:
      summary: Returns raw transaction hex
      description: Returns raw transaction hex representing a NEBL transaction
      operationId: testnet_getRawTx
      x-api-path-slug: testnetinsrawtxtxid-get
      parameters:
      - in: path
        name: txid
        description: Transaction ID
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Raw
      - Transaction
      - Hex
  /testnet/ins/addr/{address}:
    get:
      summary: Returns address object
      description: Returns NEBL address object containing information on a specific
        address
      operationId: testnet_getAddress
      x-api-path-slug: testnetinsaddraddress-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Address
      - Object
  /testnet/ins/addr/{address}/balance:
    get:
      summary: Returns address balance in sats
      description: Returns NEBL address balance in satoshis
      operationId: testnet_getAddressBalance
      x-api-path-slug: testnetinsaddraddressbalance-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Address
      - Balance
      - In
      - Sats
  /testnet/ins/addr/{address}/unconfirmedBalance:
    get:
      summary: Returns address unconfirmed balance in sats
      description: Returns NEBL address unconfirmed balance in satoshis
      operationId: testnet_getAddressUnconfirmedBalance
      x-api-path-slug: testnetinsaddraddressunconfirmedbalance-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Address
      - Unconfirmed
      - Balance
      - In
      - Sats
  /testnet/ins/addr/{address}/totalReceived:
    get:
      summary: Returns total received by address in sats
      description: Returns total NEBL received by address in satoshis
      operationId: testnet_getAddressTotalReceived
      x-api-path-slug: testnetinsaddraddresstotalreceived-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Total
      - Received
      - By
      - Address
      - In
      - Sats
  /testnet/ins/addr/{address}/utxo:
    get:
      summary: Returns all UTXOs at a given address
      description: Returns information on each Unspent Transaction Output contained
        at an address
      operationId: testnet_getAddressUtxos
      x-api-path-slug: testnetinsaddraddressutxo-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - ""
      - UTXOs
      - At
      - Given
      - Address
  /testnet/ins/addr/{address}/totalSent:
    get:
      summary: Returns total sent by address in sats
      description: Returns total NEBL sent by address in satoshis
      operationId: testnet_getAddressTotalSent
      x-api-path-slug: testnetinsaddraddresstotalsent-get
      parameters:
      - in: path
        name: address
        description: Address
      responses:
        200:
          description: OK
      tags:
      - Blockchain
      - Returns
      - Total
      - Sent
      - By
      - Address
      - In
      - Sats
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---