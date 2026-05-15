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
| PB14 | ADC_IN1 – analogový vstup ze senzoru |
| LED1 | <p align="center"> Stavová LED </p>|
| LED2 | Stavová LED |
| LED3 | Stavová LED |
<br>



## Popis software 
### LoRa example
Prvotní základ celého projektu vychází z example LoRa aplikace LoRaWAN_End_Node_LBM, který implementuje LoRaWAN end-node zařízení, které se po spuštění připojí do LoRaWAN sítě pomocí OTAA aktivace a následně periodicky odesílá aplikační data na network server. 

Pro realizaci komunikace slouží Sub-GHz rádio integrované v mikrokontroléru STM32WL a LoRaWAN middleware stack. Aplikace obsahuje debug UART rozhraní a má implementovánu obsluhu pro různé příchozí eventy, jako je obecný ALARM, TXDONE - odeslání dat, DOWNDATA - příjem dat a další. Dále je zajištěna podpora pro periodické posílání aplikačních dat na network server.      

### Přidané funkce 
K výše popsané základní aplikaci jsou dále uživatelsky implementovány vlastní funkce za účelem:
- práci s ADC periferií
- návrh vlastního aplikačního payloadu
- serializaci dat za pomoci union struktury
- parsování zařízením přijatých dat
- rozšíření UART debuggingu payloadů

Níže bude každý z těchto bodů rozveden spolu s podrobnějším popisem a důvody této změny.
