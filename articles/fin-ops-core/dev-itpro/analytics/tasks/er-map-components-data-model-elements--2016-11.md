---
title: ER – A létrehozott formátum összetevőinek leképezése az adatmodellelemekre (2016. november)
description: Ez a témakör azt ismerteti, hogyan lehet leképezni az adatmodellelemeket a létrehozott Elektronikus jelentéskészítési (ER) konfiguráció összetevőire.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ae4b3123660d123fc5c06cbe0a69d5c66d306252ec2a117a1e6045505022f5a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776000"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a>ER – A létrehozott formátum összetevőinek leképezése az adatmodellelemekre (2016. november)

[!include [banner](../../includes/banner.md)]

Az alábbi eljárás azt mutatja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként képezhet le adatmodellelemeket a létrehozott elektronikusjelentési-konfigurációra, amely egy elektronikus dokumentumformátumot határoz meg a kifizetések üzleti tartománya számára. A formátumot a rendszer később elektronikus dokumentumok létrehozására használja majd a kifizetések feldolgozásához. Ebben a példában egy formátumkonfigurációt hozunk létre a „Litware, Inc.” mintavállalat számára. Ezeket a lépéseket a vállalat között megosztott ER konfigurációjaként minden vállalatnál végrehajthatja. Ezeknek a lépéseknek a végrehajtásához először hajtsa végre az „Új formátumkonfiguráció létrehozása” feladat-útmutató lépéseit.


## <a name="select-a-format-configuration"></a>Formátumkonfiguráció kiválasztása
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A fastruktúrában bontsa ki a „Kifizetések (egyszerűsített modell)” lehetőséget.
4. A fastruktúrában válassza ki a „Kifizetések (egyszerűsített modell)\BACS (UK fiktív)”.
5. Kattintson a Tervező pontra.

## <a name="map-format-components-to-data-model-elements"></a>Formátum-összetevők leképezése adatmodell-elemekhez
1. Kattintson a Csomópont kibontása/összecsukása lehetőségre.
2. Kattintson a Hozzárendelés fülre.
3. A fában bontsa ki a „model” elemet.
4. A fastruktúrában válassza ki ezt: „Xml\Üzenet\ProcessingDate\DateTime”.
5. A fastruktúrában válassza ki ezt: „modell\ProcessingDateTime”.
6. Kattintson a Kötés gombra.
7. A fastruktúrában válassza ki ezt: „Xml\Üzenet\MessageId\Karakterlánc”.
8. A fastruktúrában válassza ki a „modell\MessageIdentification” lehetőséget.
9. Kattintson a Kötés gombra.
10. A fában bontsa ki a „model\Payments” elemet.
11. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Összeg\Karakterlánc”.
12. A fastruktúrában válassza ki ezt: „modell\Fizetések\InstructedAmount”.
13. Kattintson a Kötés gombra.
14. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\TransDate\DateTime”.
15. A fastruktúrában válassza ki ezt: „modell\Fizetések\TransactionDate”.
16. Kattintson a Kötés gombra.
17. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Leírás\Karakterlánc”.
18. A fán válassza ki a következőt: „model\Payments\Description”.
19. Kattintson a Kötés gombra.
20. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Pénznem\Karakterlánc”.
21. A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.
22. Kattintson a Kötés gombra.
23. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Azonosító”.
24. A fastruktúrában válassza ki a „modell\Fizetések\End2EndID” lehetőséget.
25. Kattintson a Kötés gombra.
26. A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.
27. A fában bontsa ki a következőt: „model\Payments\Creditor\Account”.
28. A fában bontsa ki a következőt: „model\Payments\Creditor\Agent”.
29. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Név\Karakterlánc”.
30. A fán válassza ki „model\Kifizetések = Transactions\Creditor\Name” pontot.
31. Kattintson a Kötés gombra.
32. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\RoutingNumber\Karakterlánc”.
33. A fastruktúrában válassza ki ezt: „modell\Fizetések\Beszedő\Ügynök\RoutingNumber”.
34. Kattintson a Kötés gombra.
35. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\AccountNumber\Karakterlánc”.
36. A fán válassza ki „model\Kifizetések = Transactions\Creditor\Account\Number” pontot.
37. Kattintson a Kötés gombra.
38. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Név\Karakterlánc”.
39. A fában bontsa ki a „model\Payments= Transactions\Debtor” elemet.
40. A fában bontsa ki a következőt: „model\Payments\Debtor\Account”.
41. A fában bontsa ki a következőt: „model\Payments\Debtor\Agent”.
42. A fán válassza ki „model\Kifizetések = Transactions\Debtor\Name” pontot.
43. Kattintson a Kötés gombra.
44. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\RoutingNumber\Karakterlánc”.
45. A fastruktúrában válassza ki ezt: „modell\Fizetések\Kötelezett\Ügynök\RoutingNumber”.
46. Kattintson a Kötés gombra.
47. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\AccountNumber\Karakterlánc”.
48. A fán válassza ki „model\Kifizetések = Transactions\Debtor\Account\Number” pontot.
49. Kattintson a Kötés gombra.
50. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.
51. A fán válassza ki a következőt: „model\Payments”.
52. Kattintson a Kötés gombra.
53. Kattintson a Mentés gombra.

## <a name="validate-format-mapping"></a>Formátumleképezés ellenőrzése
1. Kattintson az Érvényesítés gombra.
    * Ellenőrizze az új hozzárendelést annak a biztosítására, hogy az összes kötés rendben legyen.  
2. Zárja be a lapot.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>A formátumkonfiguráció aktuális verziójának állapotmódosítása
A következő lépésekben módosítsa a formátumkonfiguráció állapotát vázlatról teljesítettre, hogy elérhetővé tegye a fizetési dokumentumok létrehozásához.  
1. Kattintson az Állapot módosítása elemre.
2. Kattintson a Befejezés gombra.
3. A Leírás mezőben adjon meg egy értéket.
    * Például: „1-es verzió”.  
4. Kattintson az OK gombra.
5. Válassza ki az aktuális konfiguráció teljesített verzióját.
    * Fontos, hogy a konfiguráció teljesített 1.1-es verzióként lesz mentve: ez a formátum 1-es verziója, amely az adatmodell 1-es verzióján alapul.  

## <a name="define-effective-date-for-completed-version-of-format"></a>Formátum teljesített verziójának érvénybe lépési dátumának meghatározása
Minden egyes formátumverzió konfigurálható egy bizonyos dátumtól kezdve használatra. Ha egynél több fájlformátum-verzió aktív egy meghatározott időpontban, a legújabb formátum (verziószáma alapján) lesz jelölve használatra. A munkamenet dátumértéke a megfelelő verzió kiválasztásához használatos.  

## <a name="restrict-access-to-created-format-from-companies"></a>Korlátozott hozzáférés a létrehozott formátumhoz a vállalatoktól
1. Bontsa ki az ISO Ország/régió kódok szakaszt.
    * A formátum-hozzáférések korlátozhatók egyes országok/régiók azonosításával, amelyekben a formátumok alkalmazhatók. Ha egy adott formátum országainak/régióinak listája üres, akkor ez a formátum használható bármely vállalatnál. Néhány ISO ország-/régiókód beszúrása esetén az országok/régiók adott listájába, a formátum csak akkor használható a vállalatokban, ha az elsődleges cím az országban/régióban van.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]