---
swagger: "2.0"
x-collection-name: Neblio
x-complete: 0
info:
  title: Neblio Get Issuance Metadata of Token
  description: Returns the metadata associated with a token at time of issuance.
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