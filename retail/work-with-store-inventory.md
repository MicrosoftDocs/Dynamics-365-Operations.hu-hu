---
title: "Kiskereskedelmi árukészlet kezelése"
description: "A cikk ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5e5043d5951015fc14d29989ef4cab20a8b24f3b
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="manage-store-inventory"></a>Kiskereskedelmi árukészlet kezelése

[!include[banner](includes/banner.md)]


A cikk ismerteti, hogy mely dokumentumtípusokat használhat a készlet kezeléséhez.

A következő típusú dokumentumok segítségével a kezelheti a szervezete készletét.

## <a name="purchase-orders"></a>Beszerzési rendelések
A beszerzési rendeléseket a központi irodában készítik. Ha kiskereskedelmi raktár szerepel a beszerzési rendelés fejlécében, akkor a rendelés fogadása az áruháznál történhet a Modern POS (MPOS) vagy a felhőalapú POS segítségével a Microsoft Dynamics 365 for Operations - Retail szolgáltatásban. Az üzletben fogadott mennyiségek beírását követően az értékek helyben menthetők a további módosításokhoz. Másik lehetőségként a mennyiségek vállalhatóak és a központi irodába küldhetőek. A központi irodában az üzlet által bevételezett mennyiségek kijelzésre kerülnek a Microsoft Dynamics 365 for Operations rendszerben a beszerzési rendelés **Fogadás** mezőjében.

## <a name="transfer-orders"></a>Átmozgatási rendelések
Az átmozgatási rendelés megadhatja, hogy egy adott üzlet egy olyan hely, ahonnan cikkek szállíthatóak. Ebben az esetben az átmozgatási rendelés megjelenik az üzletben Modern POS vagy Cloud POS rendszerben kitárolási kérelemként. Miután a kért mennységek kitárolódnak vállalásra kerülnek és a központi irodába lesznek küldve. A központi irodában az üzlet által kitárolt mennyiségek kijelzésre kerülnek a Microsoft Dynamics 365 for Operations rendszerben az átmozgatási rendelés **Szállítás most** mezőjében. Az átmozgatási rendelés megadhatja, hogy egy adott üzlet egy olyan hely, ahová cikkek szállíthatóak. Ebben az esetben az átmozgatási rendelés megjelenik az üzletben az MPOS vagy Cloud POS rendszerben bevételezési kérelemként. Az üzletben fogadott mennyiségek beírását követően az értékek helyben menthetők a további módosításokhoz. Másik lehetőségként a mennyiségek vállalhatóak és a központi irodába küldhetőek. A központi irodában az üzlet által bevételezett mennyiségek kijelzésre kerülnek a Microsoft Dynamics 365 for Operations rendszerben az átmozgatási rendelés **Fogadás** mezőjében.

## <a name="stock-counts"></a>Leltárok
A leltárok lehetnek ütemezettek és nem tervezettek is. A tervezett leltárokat a központi irodában kezdeményezik, ami meghatározza, hogy melyik cikkeket kell leltározni. A központi iroda létrehoz egy leltárbizonylatot, amelyet fogadni tudnak az üzletnél, ahol a tényleges készletmennyiségeket rögzítik az MPOS vagy a Cloud POS rendszerben. A nem ütemezett leltárakat az üzlet kezdeményezi, és a frissített tényleges készletmennyiségeket vagy az MPOS, vagy a Cloud POS rendszerben rögzítik. Az ütemezett leltárakkal ellentétben a nem ütemezett leltárak nem rendelkeznek a cikkek előre meghatározott listájával. Amikor bármely típusú leltár befejeződik vállalásra kerül és a központi irodába küldik. A központi irodában a leltárt ellenőrzik és feladják.






