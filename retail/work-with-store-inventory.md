---
title: "Kiskereskedelmi árukészlet kezelése"
description: "A cikk ismerteti, amelyek segítségével kezelheti a készletet a dokumentumtípusokat."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fbe9945799f1e65ed6ad624a3df270fa4eb72b88
ms.lasthandoff: 03/31/2017


---

# <a name="manage-store-inventory"></a>Kiskereskedelmi árukészlet kezelése

A cikk ismerteti, amelyek segítségével kezelheti a készletet a dokumentumtípusokat.

A következő típusú dokumentumok segítségével a kezelheti a szervezete készletét.

## <a name="purchase-orders"></a>Beszerzési rendelések
A beszerzési rendeléseket a központi irodában készítik. Kiskereskedelmi raktár szerepel a beszerzési rendelés fejlécében, ha a rendelés képes fogadni az üzletben Modern POS (MPOS) vagy felhő POS használata a Microsoft Dynamics 365 műveletek - kiskereskedelmi. Miután az üzletben kapott mennyiségek vannak megadva, hogy helyben is elmentheti további módosításra. Másik lehetőségként a mennyiségek vállalhatóak és a központi irodába küldhetőek. A központi iroda az üzletben kapott mennyiségek jelennek meg Dynamics 365 műveletek, a **fogadása most** mező a beszerzési rendelésen.
Átmozgatási rendelések
---------------

Az átmozgatási rendelés megadhatja, hogy egy adott üzlet egy olyan hely, ahonnan cikkek szállíthatóak. Ebben az esetben az átadás rendelés jelenik meg az üzletben MPOS vagy felhő POS kiadási kérelem. Után igényelt mennyiségek leltárhoz, ezeket véglegesítése és a központi iroda küldött. A központi iroda az üzletben kivett mennyiségek jelennek meg Dynamics 365 műveletek, a **Szállítás most** az átadás rendelés mezőben. Az átmozgatási rendelés megadhatja, hogy egy adott üzlet egy olyan hely, ahová cikkek szállíthatóak. Ebben az esetben az átadás rendelés jelenik meg az üzletben MPOS vagy felhő POS fogadó kérelmet. Miután az üzletben kapott mennyiségek vannak megadva, hogy helyben is elmentheti további módosításra. Másik lehetőségként a mennyiségek vállalhatóak és a központi irodába küldhetőek. A központi iroda az üzletben kapott mennyiségek jelennek meg Dynamics 365 műveletek, a **fogadása most** az átadás rendelés mezőben.

## <a name="stock-counts"></a>Leltárok
A leltárok lehetnek ütemezettek és nem tervezettek is. A tervezett leltárokat a központi irodában kezdeményezik, ami meghatározza, hogy melyik cikkeket kell leltározni. A központi iroda az üzletben, ahol a tényleges aktuális készlet mennyiségét megadott MPOS vagy felhő POS kapott leltárbizonylatot hoz létre. A nem tervezett leltárakat üzlet kezdeményezi, és a tényleges aktuális készlet mennyiségét MPOS vagy a felhő POS frissítette. Ütemezett leltárak, ellentétben a nem tervezett leltárakat nem rendelkezik előre definiált elemek listája. Amikor bármely típusú leltár befejeződik vállalásra kerül és a központi irodába küldik. A központi irodában a leltárt ellenőrzik és feladják.




