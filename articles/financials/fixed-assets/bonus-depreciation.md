---
title: Rendkívüli értékcsökkenés
description: Ez a cikk a rendkívüli értékcsökkenési funkcióról nyújt áttekintést.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 687ba57042ad65d3a1ff4ad92f0da774c6751eac
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840673"
---
# <a name="bonus-depreciation"></a>Rendkívüli értékcsökkenés

[!include [banner](../includes/banner.md)]

Ez a cikk a rendkívüli értékcsökkenési funkcióról nyújt áttekintést.

Rendkívüli értékcsökkenés esetében különleges vagy rendkívüli értékcsökkenési összegeket alkalmazhat egy eszköz üzembe helyezésének és értékcsökkenésének első évében. A rendkívüli értékcsökkenést a többi értékcsökkenési számítás előtt kell végrehajtani. Ezért célszerű a rendkívüli értékcsökkenés olyan könyvekkel történő használata, ahol a Feladás a főkönyvbe funkció le van tiltva. Használhatja a **Főkönyvbe nem feladott tranzakciók törlése** lehetőséget könyveket, a nem a főkönyvbe feladott könyvek előzménytranzakcióinak törléséhez. A rendkívüli értékcsökkenést az eszköz életciklusának későbbi pontjában rendezheti úgy, hogy törli a korábban feladott értékcsökkenési tranzakciókat. 

A rendkívüli értékcsökkenést kiszámíthatja a javaslati eljárással, vagy létrehozhatja manuálisan a rendkívüli értékcsökkenési tranzakciókat. Ha az adott eszköz könyvében már vannak értékcsökkenés-tranzakciók vagy értékcsökkenés-módosítási tranzakciók, akkor nem lehet létrehozni rendkívüli értékcsökkenési tranzakciókat.

Ha a javaslati művelet segítségével számítja ki a rendkívüli értékcsökkenést, minden létező rendkívüli értékcsökkenési tranzakció szerepel az alap kiszámításában. A számítás tartalmazza a korábban a manuálisan beírt rendkívüli értékcsökkenést is. 

Ha egy eszközre több rendkívüli értékcsökkenést alkalmaz, akkor a rendszer figyelembe veszi a prioritást. Minden rendkívüli értékcsökkenés csökkenti a következő rendkívüli értékcsökkenés eszközalapját. A program a maradványértéket nem kezeli az eszközalap részeként a rendkívüli értékcsökkenés számításánál, és az értékcsökkenési szabály nem vonatkozik a rendkívüli értékcsökkenésre. 

Jelenleg az Egyesült Államokban bizonyos vagyontárgyak 179-es szakaszba tartozó vagyontárgyaknak minősülnek. A 179-es szakasz szerinti levonás esetén lehetőség van arra, hogy leírja egy bizonyos vagyontárgy költségének egészét vagy egy részét – egy bizonyos határig. A költséget a vagyontárgy szolgálatba állításának az első évében írhatja le.

## <a name="example"></a>Példa
Az alábbi rendkívüli értékcsökkenések egy eszköz könyvéhez társulnak:

-   **179-es szakasz:** 1000,00 dollár, 1-es prioritás
-   **Liberty Zone:** 30 százalék, 2-es prioritás

Az eszköz beszerzési ára 5000,00 dollár. A rendkívüli értékcsökkenési összeg számítása során az első rendkívüli értékcsökkenési összeg 1000,00 dollár lesz a 179-es szakasz értékcsökkenése alapján. 

A következő rendkívüli értékcsökkenési összeg kiszámítása – a Liberty Zone értékcsökkenés alapján – az alábbi számítással történik: 

Beszerzési ár – 1000 dollár (a 179-es szakasz értékcsökkenése) x 30 százalék = 1200 dollár 

Ha a rendkívüli értékcsökkenés összege nagyobb, mint a maradék beszerzési ár, akkor a rendkívüli értékcsökkenési összeg a számított rendkívüli értékcsökkenés, vagy a maradék beszerzési ár közül a kevesebbik lesz. 

Ha a maradék beszerzési ár 0 (nulla) vagy kevesebb, akkor nem készülnek rendkívüli értékcsökkenési tranzakciók. 

Ha a rendkívüli értékcsökkenést a javaslati művelettel számítja ki, akkor az eszköz könyvéhez társított valamennyi alkalmazható rendkívüli értékcsökkenési rekordhoz létrejön egy rendkívüli értékcsökkenési tranzakció. 

A létrehozható rendkívüli értékcsökkenési rekordok száma korlátlan. Miután az eszközcsoport könyvéhez társította a rekordokat, a program alkalmazza őket az eszköz könyvére. 

A rendkívüli értékcsökkenést százalékként vagy százalékként vagy rögzített összegként kell megadni. Ha értékcsökkenési javaslatot ad fel, akkor a program az értékcsökkenés tranzakcióitól különálló tranzakciókként adja fel a rendkívüli értékcsökkenés tranzakcióit a könyvbe.



