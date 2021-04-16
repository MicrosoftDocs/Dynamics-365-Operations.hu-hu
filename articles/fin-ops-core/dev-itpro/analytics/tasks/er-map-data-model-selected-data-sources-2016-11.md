---
title: ER - adatmodell leképezése a kiválasztott adatforrásokra
description: Ez a témakör azt mutatja be, hogyan lehet leképezni egy Elektronikus jelentéskészítési (ER) adatmodellt a kiválasztott Microsoft Dynamics 365 Finance-adatforrásokra.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0eb7f48a50e32637003c1488d80899a704709068
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751486"
---
# <a name="er-map-data-model-to-selected-data-sources"></a>ER - adatmodell leképezése a kiválasztott adatforrásokra

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként képezhet le egy Elektronikus jelentés (ER) adatmodellt a kiválasztott adatforrásokra. Ez a modell leképezést lesz később az adatforrás egy formátumkonfigurációban, amely elektronikus fizetési dokumentumok kezelésére lesz használva. Ebben a példában a mintavállalat, a Litware, a Inc. adatmodelljét képezi le az adatforrásokhoz. A lépések végrehajtásához először hajtsa végre az „Adatforrások kijelölése modell-leképezéshez” műveletsorban ismertetett lépéseket.


## <a name="open-er-configurations-tree"></a>Nyitott ER konfigurációs fa
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Konfigurációk lehetőségre.

## <a name="select-created-model-mapping"></a>Válassza ki a létrehozott modell-leképezést
1. A fán válassza ki a következőt: „Payments (simplified model)”.
    * Győződjön meg arról, hogy a „Kifizetések (egyszerűsített modell)” modellkonfigurációja előre létre lett hozva. Ellenkező esetben álljon meg itt, és térjen vissza az „Új konfiguráció létrehozása a kijelölt tartomány adatmodelljével” feladat-útmutató elvégzése után.  
2. Kattintson a Modelltervező lehetőségre.
3. Kattintson a Modell hozzárendelése adatforráshoz gombra.
4. Válassza ki a „CT leképezés” rekordot.
    * CT-leképezés  

## <a name="bind-created-data-sources-to-data-model-elements"></a>Létrehozott adatforrások adatmodell-elemekhez kötése
1. Kattintson a Tervező pontra.
2. A fastruktúrán jelölje be a „Dátum és idő feldolgozása (ProcessingDateTime)” elemet.
3. A fán jelölje be a „Dátum feldolgozása (ProcessingDateTime)” elemet.
4. Kattintson a Kötés gombra.
5. A fán jelölje be a „Fizetési üzenet azonosítása (MessageIdentification)”.
6. A fában bontsa ki a Tranzakciók csomópontot.
7. A fán jelölje be a „Tranzakciók/napló kötegelt szám(JournalNum)”.
8. Kattintson a Kötés gombra.
9. A fastruktúrában válassza ki a „Fizetések” lehetőséget.
10. A fastruktúrában válassza ki a Tranzakciók pontot.
11. Kattintson a Kötés gombra.
12. A fában bontsa ki a „Payments= Transactions” elemet.
13. A fában bontsa ki a „Payments= Transactions\Creditor” elemet.
14. A fában bontsa ki a „Payments= Transactions\Creditor\Account” elemet.
15. A fán válassza ki „Kifizetések = Transactions\Creditor\Account\Currency code(Currency)” pontot.
16. A fában bontsa ki a „Transactions\vendBankAccountInTransactionCompany()” elemet.
17. A fán válassza ki „Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)” pontot.
18. Kattintson a Kötés gombra.
19. A fán válassza ki „Kifizetések = Transactions\Creditor\Account\IBAN code(IBAN)” pontot.
20. A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)” elemet.
21. Kattintson a Kötés gombra.
22. A fán válassza ki „Kifizetések = Transactions\Creditor\Account\Number” pontot.
23. A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)” elemet.
24. Kattintson a Kötés gombra.
25. A fában bontsa ki a „Payments= Transactions\Creditor\Agent” elemet.
26. A fán válassza ki „Kifizetések = Transactions\Creditor\Agent\Name” pontot.
27. A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\Name” elemet.
28. Kattintson a Kötés gombra.
29. A fán válassza ki „Kifizetések = Transactions\Creditor\Agent\Routing number(RoutingNumber)” pontot.
30. A fában válassza ki a „Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)” elemet.
31. Kattintson a Kötés gombra.
32. A fán válassza ki „Kifizetések = Transactions\Creditor\Agent\SWIFT code(SWIFT)” pontot.
33. A fán válassza ki „Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)” pontot.
34. Kattintson a Kötés gombra.
35. A fán válassza ki „Kifizetések = Transactions\Creditor\Name” pontot.
36. A fában bontsa ki a „Transactions\findVendTable()” elemet.
37. A fastruktúrában válassza ki a „Tranzakciók\findVendTable()ame()” elemet.
38. Kattintson a Kötés gombra.
39. A fán válassza ki „Kifizetések = Transactions\Currency code(Currency)” pontot.
40. A fában bontsa ki a „Transactions\>Relations” elemet.
41. A fán bontsa ki a „Transactions\>Relations\Currency table(Currency)” pontot.
42. A fán válassza ki a „Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)” pontot.
43. Kattintson a Kötés gombra.
44. A fában bontsa ki a „Payments= Transactions\Debtor” elemet.
45. A fában bontsa ki a „Payments= Transactions\Debtor\Account” elemet.
46. A fán válassza ki „Kifizetések = Transactions\Debtor\Account\Currency code(Currency)” pontot.
47. A fastruktúrában válassza ki a „Bank Account(BankAccount)” lehetőséget.
48. A fastruktúrában bontsa ki a „Bank Account(BankAccount)” lehetőséget.
49. A fán válassza ki a „Bank Account(BankAccount)\Currency(CurrencyCode)” pontot.
50. Kattintson a Kötés gombra.
51. A fastruktúrában válassza ki a „Bank Account(BankAccount)\IBAN” lehetőséget.
52. A fán válassza ki „Kifizetések = Transactions\Debtor\Account\IBAN code(IBAN)” pontot.
53. Kattintson a Kötés gombra.
54. A fán válassza ki „Kifizetések = Transactions\Debtor\Account\Number” pontot.
55. A fán válassza ki a „Bank Account(BankAccount)\Bank account number(AccountNum)” pontot.
56. Kattintson a Kötés gombra.
57. A fában bontsa ki a „Payments= Transactions\Debtor\Agent” elemet.
58. A fán válassza ki „Kifizetések = Transactions\Debtor\Agent\Name” pontot.
59. A fastruktúrában válassza ki a „Bank Account(BankAccount)\Name” lehetőséget.
60. Kattintson a Kötés gombra.
61. A fán válassza ki „Kifizetések = Transactions\Debtor\Agent\Routing number(RoutingNumber)” pontot.
62. A fán válassza ki a „Bank Account(BankAccount)\Routing number(RegistrationNum)” pontot.
63. Kattintson a Kötés gombra.
64. A fán válassza ki „Kifizetések = Transactions\Debtor\Agent\SWIFT code(SWIFT)” pontot.
65. A fán válassza ki a „Bank Account(BankAccount)\SWIFT code(SWIFTNo)” pontot.
66. Kattintson a Kötés gombra.
67. A fán válassza ki „Kifizetések = Transactions\Debtor\Name” pontot.
68. A fán válassza ki a „Company information(Company)” pontot.
69. A fán bontsa ki a „Company information(Company)” pontot.
70. A fán válassza ki a „Company information(Company)\Name” pontot.
71. Kattintson a Kötés gombra.
72. A fán válassza ki „Kifizetések = Transactions\Description” pontot.
73. A fán válassza ki „Transactions\Description(Txt)” pontot.
74. Kattintson a Kötés gombra.
75. A fán válassza ki a „Payments= Transactions\End to end identification code(End2EndID)” pontot.
76. A fastruktúrában válassza ki a „Transactions\$EndToEndID” lehetőséget.
77. Kattintson a Kötés gombra.
78. A fán válassza ki a „Payments= Transactions\Instructed amount(InstructedAmount)” pontot.
79. A fastruktúrában válassza ki a „Transactions\$Amount” lehetőséget.
80. Kattintson a Kötés gombra.
81. A fán válassza ki a „Payments= Transactions\Transaction date(TransactionDate)” pontot.
82. A fán válassza ki „Transactions\Date(TransDate)” pontot.
83. Kattintson a Kötés gombra.

## <a name="validate-created-mapping"></a>Létrehozott leképezés validálása
1. Kattintson az Érvényesítés gombra.
    * Ellenőrizze az új hozzárendelést annak a biztosítására, hogy az összes kötés rendben legyen.  
2. Kattintson a nyílra vagy zárja be a hibalista szakaszt.
3. Kattintson a Mentés gombra.
4. Zárja be a lapot.
5. Zárja be a lapot.
6. Zárja be a lapot.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>A modellkonfiguráció aktuális verziójának állapotmódosítása
1. Kattintson az Állapot módosítása elemre.
    * Módosítsa a tervezett modellkonfiguráció állapotát – Vázlat állapotról Teljesített állapotra annak érdekében, hogy rendelkezésre álljon a kifizetési formátum tervezéséhez.  
2. Kattintson a Befejezés gombra.
    * Válassza a Kész lehetőséget  
3. A Leírás mezőben adjon meg egy értéket.
    * Például: „1-es verzió”.  
4. Kattintson az OK gombra.
5. Válassza ki az aktuális konfiguráció teljesített verzióját.
    * Fontos, hogy a létrehozott konfiguráció teljesített 1-es verzióként lesz mentve.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]