# Infrastructure

## The Machine
Ropsten  
Rinkeby  
Mainnet  
Arbitrum (aktuell auf das testnet zeigend... Der ausführende Bot (trading actor) greift aktuell auf die testnet node zu port: 8455)  

Produktiv können wir den trading actor per infura.io o.Ä. mit Arbitrum connecten...  


## CI/CD

Option 1:  
Wir lassen den backend (trading-actor) zunächst z.B. eine Woche auf dem Testnet Arbitrum laufen (staging) bevor wir die selben smart contracts auf Arbitrum laufen lassen.    

... contracts nach erfolgreichen (eine woche nicht mehr als 30% verlust... gemacht... --> kann detailliert werden)   tests automatisiert deployen lassen (1. gläubigerschutz 2. programmierfehler früherkennungsdisziplin ...)  

Option 2:   
Wir deployen Änderungen direkt auf Arbitrum (nicht erst Testnet Arbitrum)    

