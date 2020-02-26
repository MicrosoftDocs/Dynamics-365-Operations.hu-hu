## <a name="terms-of-payment-to-msdyn_paymentterms"></a>Az msdyn_paymentterms fizetési feltételei

Ez a sablon szinkronizálja az adatokat az Finance and Operations alkalmazások és a(z) Common Data Serviceközött.

Finance and Operations mező | Térkép típusa | Egyéb Dynamics 365 mező | Alapértelmezett érték
---|---|---|---
LEÍRÁS | = | msdyn_description | 
NÉV | = | msdyn_name | 
HÓNAPOKSZÁMA | = | msdyn_numberofmonth | 
AHÓNAPLEÁLLÍTÁSINAPJA | = | msdyn_cutoffdayofmonth | 
KÉSZPÉNZBELIKIFIZETÉS | >< | msdyn_iscashpayment | 
NAPOKSZÁMA | = | msdyn_days | 
TANÚSÍTOTTVÁLLALATELLENŐRZÉSE | >< | msdyn_iscertifiedcompanycheck | 
ALAPÉRTELMEZETTFIZETÉSIFELTÉTEL | >< | msdyn_isdefaultpaymentterm | 
HITELKÁRTYAFIZETÉSITÍPUSA | >< | msdyn_creditcardpaymenttype | 
HITELKÁRTYAHITELELLENŐRZÉSITÍPUSA | >< | msdyn_creditcardcreditchecktype | 
FIZETÉSINAPNEVE | = | msdyn_paymentdayname.msdyn_name | 
FIZETÉSIMÓDTÍPUSA | >< | msdyn_paymentmethodtype | 
KIFIZETÉSÜTEMEZÉSÉNEKNEVE | = | msdyn_paymentschedulename.msdyn_name | 
