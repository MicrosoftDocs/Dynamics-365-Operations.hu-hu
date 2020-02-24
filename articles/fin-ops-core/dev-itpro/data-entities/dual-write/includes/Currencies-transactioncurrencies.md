## <a name="currencies-to-transactioncurrencies"></a>Pénznemek a tranzakció-pénznemekhez

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Forrásszűrő: ((PÉNZNEMKÓD ! = „999”))

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
PÉNZNEMKÓD | = | isopénznemkód | 
NÉV | = | pénznemneve | 
SZIMBÓLUM | = | pénznemszimbólum | 
egyik sem | >> | árfolyam | 1
