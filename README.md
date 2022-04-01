# Infrastructure

## The Machine

### Hardware
The Machine has the following hardware installed:
- AMD Threadripper 3960x
    - be quiet! Dark Rock Pro TR4 Cooler
- 64GB G.Skill RipJaws V schwarz DDR4-3200 DIMM CL16 Quad Kit
- 4GB MSI GeForce GTX 1650 (no real power needed)
- 850 Watt be quiet! Straight Power 11 Modular 80+ Gold

#### **Storage**
Main M.2 Boot-SSD and Ethereum Main-Chain saved on: 
- 2TB Samsung 970 Evo Plus

Second SATE-SSD for Testnet and Arbitrum-Chains. This SSD is mounted to the following dir within the master-users home folder at startup: `/home/master/2ndSSD`

We use the following SSD:
- 2TB Samsung 870 QVO 2.5"


### **Network**
The machine is running different nodes, dependent on the current needs of the team. All paths that are presented in the following passages are saved under the master-users home directory.

#### **Rinkeby-Testnet**
The testnet is synced to the SATA-SSD under the following path:
`/home/master/2ndSSD/.rinkeby`

To run the Node execute the `run.sh` scirpt within the directory. This scritp will start the node. It will be available under the following ports:
- http: 8545
- ws  : 8546

It will use port `30303` to connect to other peers.

#### **Ropsten-Testnet**
The testnet is synced to the SATA-SSD under the following path:
`/home/master/2ndSSD/.ropsten`

To run the Node execute the `run.sh` scirpt within the directory. This scritp will start the node. It will be available under the following ports:
- http: 8541
- ws  : 8542

It will use port `30301` to connect to other peers.

#### **Arbitrum-Rinkeby**
The testnet is synced to the SATA-SSD under the following path:
`/home/master/2ndSSD/arb-rinkeby`

To run the Node execute the `run.sh` scirpt within the directory. This script will start the docker-container provided by Offchainlabs. *Make sure that the rinkeby node is running on the local machine on port 8545!! The container depends on that connection!* 

For persistence reasons we need to mount a local directory to the container. In our case we bind the path `/home/master/2ndSSD/arb-rinkeby` to the following dir within the container: `/home/user/.arbitrum/rinkeby`.

The node will be available under the followings ports after a succesful start:
- http: 8547
- ws  : 8548

#### **Arbitrum-Mainnet**
This node uses the simular parameters as the arbitrum-rinkeby node. It is synced to the following dir: `/home/master/2ndSSD/arb-mainnet`

The only difference to the Arbitrum-Rinkeby-Node is the different directory and the fact that it expects a mainnet-node at localhost:8543. *START THE ETHEREUM-MAINNET-NODE BEFORE STARTING THE ARBITRUM NODE1* 

After that the node should be available at the following ports:
- http: 8547
- ws  : 8548

Produktiv können wir den trading actor per infura.io o.Ä. mit Arbitrum connecten...  


## CI/CD

Option 1:  
Wir lassen den backend (trading-actor) zunächst z.B. eine Woche auf dem Testnet Arbitrum laufen (staging) bevor wir die selben smart contracts auf Arbitrum laufen lassen.    

... contracts nach erfolgreichen (eine woche nicht mehr als 30% verlust... gemacht... --> kann detailliert werden)   tests automatisiert deployen lassen (1. gläubigerschutz 2. programmierfehler früherkennungsdisziplin ...)  

Option 2:   
Wir deployen Änderungen direkt auf Arbitrum (nicht erst Testnet Arbitrum)    

## Healthchecks

### Check disk usage
```sh 
du -h
```
### Check how much disk-space the different folders use
```sh 
du -h
```
### Show running process
```sh 
ps aux
```
### Show open ports
```sh 
netstat -npl
```
### Kill a process
```sh 
kill <process-id>
```
