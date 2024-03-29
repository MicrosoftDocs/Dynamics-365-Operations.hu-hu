---
title: Áfa átváltási arány áttekintése
description: Ez a cikk a Cseh Köztársaságban, Magyarországban és Lengyelországban elérhető áfaszámítás árfolyamával kapcsolatban tartalmaz tájékoztatást.
author: mrolecki
ms.date: 07/08/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Czech Republic, Hungary, Poland
ms.author: mrolecki
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 272703,  ""intro-internal
ms.assetid: 2d1fad67-8234-49cc-b009-0f3cc29f5886
ms.search.form: ExchangeRateCurrencyPairCalculationRules, LedgerParameters, SalesTaxExchangeRateType, TaxTmpWorkTrans
ms.openlocfilehash: b132eb08bbdba8c940d2e359c9f01beb1f4a376a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269341"
---
# <a name="vat-exchange-rate-overview"></a>Áfa átváltási arány áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk a Cseh Köztársaságban, Magyarországban és Lengyelországban elérhető áfaszámítás árfolyamával kapcsolatban tartalmaz tájékoztatást. Az áfa kiszámításához választott átváltási árfolyam eltérhet a vállalat könyvelési funkciói esetében alkalmazott átváltási árfolyamtól. Amikor külföldi pénznemben lévő dokumentumot adnak fel, az esetleges árfolyamkülönbségek a meghatározott főkönyvi számlákra kerülnek.

A szervezet kiválaszthatja az áfa kiszámítására használni kívánt árfolyamot az áfabevallásokhoz. Az árfolyam eltérhet attól az árfolyamtól, amelyet a szervezet a vállalati könyvelési feladatok során alkalmaz. A könyvelési feladatok közé tartozik az adókkal kapcsolatos következő dokumentumok előkészítése:

-   Számlák
-   Szabadszöveges számlák
-   Beszerzési rendelések
-   Projektszámlák
-   Jóváírások
-   Helyesbítő számlák

Amikor külföldi pénznemben lévő dokumentumot ad fel, az esetleges árfolyamkülönbségek a meghatározott főkönyvi számlákra kerülnek.

## <a name="prerequisites"></a>Előfeltételek

Ahhoz, hogy ezt a funkciót használni tudja, konfigurálnia kell a rendszert.

1.  Készítsen árfolyamtípusokat, és állítsa be az áfára vonatkozó átváltási árfolyamokat itt: **Főkönyv** &gt; **Pénznemek** &gt; **Árfolyamtípusok**. Tetszőleges számú árfolyamtípust és devizaárfolyamot adhat meg.
2.  Kapcsolja be az áfa átváltási arányainak kiszámítását a **Bank - árfolyam** paraméter bekapcsolásával, továbbá a beérkező és fizetendő áfa átváltásiárfolyam-típusainak meghatározásával itt: **Főkönyv** &gt; **Főkönyv beállításai** &gt; **Főkönyvi paraméterek**.
3.  Állítsa be a pénznemek átváltási árfolyamtípusait az adott értékesítési és beszerzési tranzakciótípusokhoz itt: **Főkönyv** &gt; **Pénznemek** &gt; **Pénznemek árfolyamtípusai az áfához**.
4.  A felszámított és fizetendő áfa közötti különbség és az eltérések főkönyvi ellenszámlájának beállítása a főkönyv feladási csoportjaiban: **Áfa** &gt; **Beállítás** &gt; **Áfa** &gt; **Főkönyvi feladási csoportok**.
5.  Nem kötelező: Állítsa be az árfolyam-számítási szabályt a pénznempárra vonatkozóan a **Főkönyv**&gt;**Pénznemek**&gt;**Pénznempárok árfolyam-számítási szabályai** pontra. Az árfolyam-számítási szabályokat a devizában meghatározott értékesítési számlák áfaösszegének a cél pénznemre való konvertálása során alkalmazza a rendszer.

## <a name="overview"></a>Áttekintés

Miután beállította a rendszert az áfaárfolyamok használatára, ha be kell írnia a dokumentumot, vagy létre kell hoznia egy devizát használó megbízást, akkor az **Áfatranzakciók** oldalon kell beállítania az **Áfatételjegyzék dátuma** értéket, illetve megadnia az alapértelmezett **Áfa árfolyama** értéket. Mindkét mező szerkeszthető. Emellett használható a **Helyesbített eredeti összeg (áfaárfolyam)** vagy a **Helyesbített áfaösszeg (áfaárfolyam)** mező is a tényleges áfaösszegek megadására abba a helyi pénznemben, amely meg van határozva egy külső dokumentumban. A könyvelés áttekintésekor megtekintheti az áfakülönbségeket az **Analitikus napló** oldalon. Amikor a dokumentumot feladják, az olyan tranzakciók esetében, amelyeket az Ön által konfigurált főkönyvi számlákra adtak fel, megtekintheti az áfa összegének azon különbségeit, amelyek az áfa pénznemének átváltási árfolyama és a számlázási devizaárfolyam különbsége okoz a szervezeted számára.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
