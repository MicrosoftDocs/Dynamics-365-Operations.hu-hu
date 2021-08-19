---
title: Készletjelölés tervezési optimalizálással
description: Ez a témakör a megerősített rendelések készletének megjelölésére használható beállításokról nyújt tájékoztatást a tervezésoptimalizálás során.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: dc94ca8b15d626d8ff64f50718d7d2e3e0326144465f3d27787805220842849f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6711905"
---
# <a name="inventory-marking-with-planning-optimization"></a>Készletjelölés tervezési optimalizálással

[!include [banner](../../includes/banner.md)]

Ez a témakör a megerősített rendelések készletének megjelölésére használható beállításokról nyújt tájékoztatást a tervezésoptimalizálás során.

A *Jelölés* a kínálat és kereslet összekapcsolására szolgál. Ez hasonlít az *igénykövetés* műveletre, amely azt jelzi, hogy az alaptervezés hogyan tervezi a szükségletek lefedését. Tervezési szempontból a fő különbség az, hogy a jelölés állandóbb, mint az igénykövetés.

A jelölést a speciális költségszámítási esetek támogatására vezették be a elsőként be, elsőként ki (FIFO) és utolsóként be, elsőként ki (LIFO) esetekhez. Azonban most már néhány nem költségszámítási esethez is használatos. A kínálat és a szükséglet közötti jelölés nem kötelező, és csaknem állandó. A jelölést a felhasználó manuálisan is eltávolíthatja, vagy az értékesítésirendelés-sor alábontásával eltávolíthatja, ha be van jelölve a **Jelölés törlése** beállítás.

Az igénykövetést az Alaptervezés vezérli, hogy a szükségletet a szükséges kínálattal kapcsolja. Az igénykövetés a szükségletek fedezéséhez szükséges kínálat optimalizálása céljából minden tervezési futtatásnál módosítható. Amikor az alaptervezési frissíti az igénykövetési információkat, minden meglévő jelölést figyelembe vesz.

Az igénykövetés a megfelelő jelöléssel, az aktuális készletfoglalásokkal és a rendelésen szereplő foglalásokkal együtt kezdődik, a következő sorrendben:

1. Szükséglet és kínálat közötti jelölés
1. Aktuális készletfoglalások
1. Rendelésen szereplő foglalások

Ha egy tervezett rendelést erősít meg, akkor a **Megerősítés** párbeszédpanelen szerepel egy **Jelölés frissítése** mező, amellyel beállíthatók a megerősítés során létrehozott rendelésekre vonatkozó jelölési beállítások. Válasszon a következő értékek közül:

- **Nem** – Nem alkalmaztak készletjelölést.
- **Standard** – a készletjelölés frissítése az igénykövetés alapján történik. Egy szükségleti rendelést (igény) és egy teljesítési rendelést (kínálat) állít jelöléssel párba a program. Ha a teljesítési rendelésen bizonyos mennyiség megmarad, a rendszer nem jelöli meg, és a hivatkozási adatok üresen maradnak. Ha például egy 100 ea-ra vonatkozó értékesítési rendelést igénykövetéssel egy 150 ea-s beszerzési rendeléssel állítják szembe, akkor a hivatkozási adatokat a rendszer csak az értékesítési rendeléshez rendeli hozzá.
- **Bővített** – mind a szükségleti rendelést (szükséglet), mind a teljesítési rendelést (ellátás) megjelöli a program, függetlenül attól, hogy marad-e mennyiség a teljesítési rendelésen. Ha például egy 100 ea-ra vonatkozó értékesítési rendelést igénykövetéssel egy 150 ea-s beszerzési rendeléssel állítják szembe, akkor a hivatkozási adatokat a rendszer mint az értékesítési rendeléshez, mind a beszerzési rendeléshez hozzárendeli.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]