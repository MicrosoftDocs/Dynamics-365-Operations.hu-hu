---
title: Készletjelölés
description: Ez a cikk a visszaeső rendelésekben a készlet megjelölésére rendelkezésre álló beállításokkal kapcsolatban tartalmaz tájékoztatást.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: c86db6a670d7d0f7bfe74b7466b9bce766e4a08d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740577"
---
# <a name="inventory-marking"></a>Készletjelölés

[!include [banner](../../includes/banner.md)]

Ez a cikk a visszaeső rendelésekben a készlet megjelölésére rendelkezésre álló beállításokkal kapcsolatban tartalmaz tájékoztatást.

A *Jelölés* a kínálat és kereslet összekapcsolására szolgál. Ez hasonlít az *igénykövetés* műveletre, amely azt jelzi, hogy az alaptervezés hogyan tervezi a szükségletek lefedését. Tervezési szempontból a fő különbség az, hogy a jelölés állandóbb, mint az igénykövetés.

A jelölést a speciális költségszámítási esetek támogatására vezették be a elsőként be, elsőként ki (FIFO) és utolsóként be, elsőként ki (LIFO) esetekhez. Azonban most már néhány nem költségszámítási esethez is használatos. A kínálat és a szükséglet közötti jelölés nem kötelező, és csaknem állandó. A jelölést a felhasználó manuálisan is eltávolíthatja, vagy az értékesítésirendelés-sor alábontásával eltávolíthatja, ha be van jelölve a **Jelölés törlése** beállítás.

Az igénykövetést az Alaptervezés vezérli, hogy a szükségletet a szükséges kínálattal kapcsolja. Az igénykövetés a szükségletek fedezéséhez szükséges kínálat optimalizálása céljából minden tervezési futtatásnál módosítható. Amikor az alaptervezési frissíti az igénykövetési információkat, minden meglévő jelölést figyelembe vesz.

Az igénykövetés a megfelelő jelöléssel, az aktuális készletfoglalásokkal és a rendelésen szereplő foglalásokkal együtt kezdődik, a következő sorrendben:

1. Szükséglet és kínálat közötti jelölés
1. Aktuális készletfoglalások
1. Rendelésen szereplő foglalások

Ha egy tervezett rendelést erősít meg, akkor a **Megerősítés** párbeszédpanelen szerepel egy **Jelölés frissítése** mező, amellyel beállíthatók a megerősítés során létrehozott rendelésekre vonatkozó jelölési beállítások. Válasszon a következő értékek közül:

- *Nem* – Nem alkalmaztak készletjelölést.
- *Standard* – a készletjelölés frissítése az igénykövetés alapján történik. Egy szükségleti rendelést (igény) és egy teljesítési rendelést (kínálat) állít jelöléssel párba a program. Ha a teljesítési rendelésen bizonyos mennyiség megmarad, a rendszer nem jelöli meg, és a hivatkozási adatok üresen maradnak. Ha például egy 100 ea-ra vonatkozó értékesítési rendelést igénykövetéssel egy 150 ea-s beszerzési rendeléssel állítják szembe, akkor a hivatkozási adatokat a rendszer csak az értékesítési rendeléshez rendeli hozzá.
- *Bővített* – mind a szükségleti rendelést (szükséglet), mind a teljesítési rendelést (ellátás) megjelöli a program, függetlenül attól, hogy marad-e mennyiség a teljesítési rendelésen. Ha például egy 100 ea-ra vonatkozó értékesítési rendelést igénykövetéssel egy 150 ea-s beszerzési rendeléssel állítják szembe, akkor a hivatkozási adatokat a rendszer mint az értékesítési rendeléshez, mind a beszerzési rendeléshez hozzárendeli.
- *Egyszintű szabvány* – egyszintű jelölést használ. Az egyszintű jelölés csak a fő cikket jelöli, az anyagjegyzék összetevőit nem. Ezért a megingás után rugalmasan lehet tartani a termelési rendelések összetevő-hozzárendelését. Az egyszintű jelölés segítségével optimalizálhatja a rendszer az utolsó percek igényváltozását. Az *egyszintű* normál jelölésnél a követelményrendelések a teljesítménnyel vannak megjelölve, de a teljesítménnyel kapcsolatos rendelések nem jelölve meg, ha maradt mennyiségük.
- *Egyszintű kiterjesztett* – egyszintű jelölést használ. A *kiterjesztett* egyszintű jelölésnél a követelményrendelések a teljesítménnyel, a teljesítménnyel kapcsolatos rendeléseket pedig mindig megjelölik, függetlenül attól, hogy marad-e mennyiség.

A rendszer alapértelmezett jelölési beállításának **\>\> beállításához használja az Alaptervezés beállítása alaptervezési paramétereit.** Ezután a Szokásos **frissítés** lapon állítsa **a** Jelölés frissítése mezőt a preferált beállításra.

> [!NOTE]
> Az *egyszintű szabványos* és *az* *egyszintű kiterjesztett lehetőségek csak akkor érhetők el, ha engedélyezve van a* rendelésre való ellátásautomatizálási funkció a rendszerben. A funkcióval és engedélyezésével kapcsolatos további tudnivalókat lásd a [Rendelésre hozás ellátási automatizálásban](../make-to-order-supply-automation.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
