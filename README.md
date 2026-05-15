<h1 align="center">
Semestrální projekt z předmětu MPC-SSY
</h1>
Tento projekt implementuje jednoduchou end-node LoRa aplikaci. Dané zařízení je určeno k periodickému čtení dat z analogového senzoru, která následně odesílá přes LoRaWAN síť na network server.   

## Použitý hardware
### Seznam použitých komponent 
- nucleo board typu STM32-WL55JC1
- analogový senzor pro měření výšky hladiny  

###  Propojení pinů - Pinout
| Pin | Funkce |
|---|---|
| PB14 | ADC_IN1 – analogový vstup senzoru |
| LED1 | <p align="center"> Stavová LED </p>|
| LED2 | Stavová LED |
| LED3 | Stavová LED |
| BUT1 | Uživatelské tlačítko |
| PROB1 | Debug GPIO |
| PROB2 | Debug GPIO |
