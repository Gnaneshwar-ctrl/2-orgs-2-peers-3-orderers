# 2-orgs-2-peers-3-orderers
a simple network with 2 orgs 2 peers 3 orderers

Org1 peer environment variables
You can now set the environment variables that allow you to operate the peer CLI as Org1:
# Environment variables for Org1
 
export CORE_PEER_TLS_ENABLED=true

export CORE_PEER_LOCALMSPID="Org1MSP"

export CORE_PEER_TLS_ROOTCERT_FILE=${PWD}/organizations/peerOrganizations/org1.example.com/peers/peer0.org1.example.com/tls/ca.crt

export CORE_PEER_MSPCONFIGPATH=${PWD}/organizations/peerOrganizations/org1.example.com/users/Admin@org1.example.com/msp

export CORE_PEER_ADDRESS=localhost:7051

CORE_PEER_TLS_ROOTCERT_FILE  refer to org1 peer ca certficate.

CORE_PEER_MSPCONFIGPATH  refer to org1 peer msp material.

Org2 peer environment variables
You can now set the environment variables that allow you to operate the peer CLI as Org2:
# Environment variables for Org2
 
export CORE_PEER_TLS_ENABLED=true

export CORE_PEER_LOCALMSPID="Org2MSP"

export CORE_PEER_TLS_ROOTCERT_FILE=${PWD}/organizations/peerOrganizations/org2.example.com/peers/peer0.org2.example.com/tls/ca.crt

export CORE_PEER_MSPCONFIGPATH=${PWD}/organizations/peerOrganizations/org2.example.com/users/Admin@org2.example.com/msp

export CORE_PEER_ADDRESS=localhost:9051





# Adding more ordered nodes 

1) In crypto-config under OrdererOrgs: Specs: create a new hostname for your orderer (using the same domain and name as your other).

2) Run the command ./cryptogen extend --config=../test-network/organizations/cryptogen/crypto-config-orderer.yaml NOTE: the 'extend' part so it generates what you need and not regenerate everything.
 
