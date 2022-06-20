---
title: Rendelések szállítása egy másik üzletből költségküldési szolgáltatással
description: Ez a témakör a Költség küldése szolgáltatást ismerteti.
author: ashishmsft
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: d73a21bfe9a284bd6e222e73bb0250648912b230
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863513"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a>Rendelések szállítása egy másik üzletből költségküldési szolgáltatással

[!include [banner](includes/banner.md)]

A Commerce költségküldési funkciójával a vevői rendelések feladhatók egy üzletben, és kiszállíthatók egy másik üzletből.

A pénztári (POS) ügyfélen feladott vevői rendelések több teljesítési lehetőséget támogatnak. Néhány példa a teljesítési lehetőségekre:

- Felvétel ugyanabban az üzletben egy másik napon.
- Felvétel egy másik az üzletben ugyanazon a napon vagy egy másik napon.
- Szállítás az üzlethez társított, alapértelmezett szállítási raktárból, és szállítás egy adott dátumon.

A költségküldési szolgáltatás a következő POS-műveleteket használj: az összes termék szállítás és a kijelölt termékek szállítása. Ez lehetővé teszi a tárolóadminisztrátor számára a „szállítás kiindulási helye” kiválasztását, ahonnan a rendelés vagy a rendeléssor teljesíthető. Alapértelmezés szerint a „szállítás kiindulási helye” az üzlethez társított a szállítási raktár. Az üzlet eladója azonban módosíthatja ezt a helyet, és minden üzletet kiválaszthat, amely az üzlethez társított lokátorcsoportban meg van adva.

A „szállítás célhelye” kiválasztásának képessége változatlan marad.

A rendelési sor teljesítéséhez használható szállítási módok a termékek és a címek érvényes szállítási módjainak konfigurációján alapulnak. Mivel az érvényes szállítási módok szabályainak karbantartása csak a Központban (HQ) történik, a POS-ügyfél a valós idejű hívással olvassa be a szállítási sor érvényes szállítási módjait.


[!INCLUDE[footer-include](../includes/footer-banner.md)]