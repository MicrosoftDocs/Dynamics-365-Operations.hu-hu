---
title: "Rendelés leszállítása egy másik áruházból"
description: "Ez a témakör leírja a költségküldési funkciót."
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 986ec7835dac52c326085c47313205d08b1bafa8
ms.openlocfilehash: d217bc31ad9d93c5440e5329f7b7327d089137f4
ms.contentlocale: hu-hu
ms.lasthandoff: 10/10/2017

---

# <a name="ship-an-order-from-a-different-store"></a>Rendelés leszállítása egy másik áruházból

[!include[banner](includes/banner.md)]

A Dynamics 365 for Retail költségküldési funkciójával a vevői rendelések feladhatók egy üzletben, és kiszállíthatók egy másik üzletből A pénztári (POS) ügyfélen feladott vevői rendelések több teljesítési lehetőséget támogatnak. Néhány példa a teljesítési lehetőségekre:
-   Felvétel ugyanabban az üzletben egy másik napon.
-   Felvétel egy másik az üzletben ugyanazon a napon vagy egy másik napon.
-   Szállítás az üzlethez társított, alapértelmezett szállítási raktárból, és szállítás egy adott dátumon.

A költségküldési szolgáltatás a következő POS-műveleteket használj: az összes termék szállítás és a kijelölt termékek szállítása. Ez lehetővé teszi a tárolóadminisztrátor számára a „szállítás kiindulási helye” kiválasztását, ahonnan a rendelés vagy a rendeléssor teljesíthető. Alapértelmezés szerint a „szállítás kiindulási helye” az üzlethez társított a szállítási raktár. Az üzlet eladója azonban módosíthatja ezt a helyet, és minden üzletet kiválaszthat, amely az üzlethez társított lokátorcsoportban meg van adva. 

A „szállítás célhelye” kiválasztásának képessége változatlan marad. 

A rendelési sor teljesítéséhez használható szállítási módok a termékek és a címek érvényes szállítási módjainak konfigurációján alapulnak. Mivel az érvényes szállítási módok szabályainak karbantartása csak a Kiskereskedelmi központban (HQ) történik, a POS-ügyfél a valós idejű hívással olvassa be a szállítási sor érvényes szállítási módjait. 


