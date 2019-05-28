---
title: Vevőikifizetés-információk (előnézet)
description: Ez a témakör leírja, hogyan segíthet a vevőikifizetés-információk megjósolni egy számla kifizetésének időpontját és segíti a szervezetet optimalizálási stratégiájának létrehozásához, mely javítja a határidőre fizetések arányát.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566244"
---
# <a name="customer-payment-insights-preview"></a>Vevőikifizetés-információk (előnézet)

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Ez a funkció egy célzott kiadés része, és csak azoknak a felhasználóknak érhető el, akik részt vesznek a Privát előnézet programban. Ez a funkció egy, a közeljövőben kiadandó általános rendelkezésre állású verzióban fog szerepelni.

# <a name="overview"></a>Áttekintés

Szervezetek gyakran nehezen jósolják meg, hogy a vevő mikor fizeti ki a számláikat. Betekintést hiánya pontatlan pénzforgalmi előrejelzéseket nem hatékony behajtási folyamatokat és rendeléseket kiadását okozhatja olyan vevőknek, akik pénzügyi kockázatot jelentenek. A Vevői kifizetés információk (előnézet) gépi tanulással jósolja meg egy számla kifizetését.. Optimalizálási stratégiákat is kínál, amelyek testreszabhatók, hogy maximalizálni lehessen annak valószínűségét, hogy a vevők időre fizessenek.

## <a name="predictions"></a>Előrejelzések

Fizetési előrejelzésekhez segítségével a szervezet javíthatja üzleti folyamatait, azáltal, hogy segít:

-   Könnyen azonosítani a várhatóan késedelmesen fizetett számlákat.
-   Megfelelő intézkedéseket tehessenek, melyek növelik az időre fizetés valószínűségét.

A Vevői kifizetés információk (előnézet) gépi tanulással jósolja meg egy számla kifizetését.. Korábbi számla- fizetési és a vevői adatok használatával egy számítógépes tanulási modellt hoz létre, mellyel megjósolható a számla fizetésének időpontja.

Minden nyitott számla esetében a Vevői fizetési információk (előnézet) három fizetési valószínűséget jósol:

-  Kifizetés időben valószínűsége ( a számla esedékességi dátumán belül).
-  Kifizetés valószínűsége a lejárattól számított 30 napon belül.
-  Kifizetés valószínűsége a lejárattól számított 30 napon túl.

A kifizetések valószínűsége az előrejelzés szakaszban tekinthetők meg.

[![Fizetési előrejelzések](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)

Minden számlához hozzárendeli a legjobb fizetési valószínűséget a fent meghatározott három előre jelzett fizetési valószínűségek közül. A legnagyobb fizetési valószínűséggel rendelkező eset a nyertes eset.


Például tegyük fel, hogy egy számlához az előrejelzés szerint 71 százalékos valószínűsége, hogy a számla fizetése időben történik a 13 százalékos valószínűsége, hogy a számla kifizetése az esedékességi dátumot követő 30 napon belül történik, és 16 százalékos valószínűsége, hogy a számla fizetése az esedékességi dátumot követő 30 napon túl történik. A legnagyobb valószínűséggel a számla ki lesz időben fizetve helyzetnek van, így a számlát valószínűleg időben kifizetve címkét kap.

[![Fizetési előrejelzések](./media/payment-predict.png)](./media/payment-predict.png)

## <a name="optimization-strategies"></a>Optimalizálási stratégiák

Kívül fizetési előrejelzéseken túl a Vevői kifizetési információk (előnézet) használatával optimalizálási stratégiákkal javíthatja az időben fizetés valószínűségét. Ez lehetővé teszi a szervezeteknek egy"Mi történik, ha" elemzés elvégzését. úgy, hogy a felhasználóknak megengedi számla és a vevői paraméterek beállítását, és azok hatásának elemzését az időbeni számlafizetés valószínűségére

Például egy szervezet szeretné kiértékelni, hogy milyen hatással lenne a készpénzfizetési engedmény frissítése a számlákon az időben történő kifizetés valószínűségére. Amikor számlák optimalizálva vannak az új engedmény használata, a felhasználók áttekinthetik az engedmény alkalmazásnak hatását ezen számlák időben történő kifizetésének valószínűségére. Ha az engedmény alkalmazásának költsége minimális az időben történő kifizetés előnyeihez képest esetén a vállalat dönthet a kijelölt engedmény alkalmazása mellett az összes jövőbeni nyitott rendelésre.

> [!NOTE] 
> Jelenleg csak az engedmény érhető el optimalizálási stratégiának.a Vevői kifizetés információk (előnézet) funkcióban.

[![Optimalizált előrejelzések](./media/optimized-pay.png)](./media/optimized-pay.png)

## <a name="how-to-get-customer-payment-insights-preview"></a>Vevőikifizetés-információk (előnézet) lekérése

Ha szeretné kipróbálni a vevőikifizetés-információkat (előnézet) lépett fel, kérjük, írjon e-mailt a [Pénzügyi információk előnézet csapatnak](mailto:fiap@microsoft.com) 

## <a name="privacy-statement"></a>Adatvédelmi nyilatkozat

Az előnézetek az Egyesült Államokban tárolják az ügyféladatokat. Mindemellett az előnézetek (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmaznak, mint a Dynamics 365 for Finance and Operations szolgáltatás (2) és nem tartalmazza s szolgáltatásiszint szerződés ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.
