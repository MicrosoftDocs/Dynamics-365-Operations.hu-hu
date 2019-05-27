---
title: Szervizrendelések létrehozása manuálisan
description: Szervizrendeléseket a szolgáltatási szerződésből vagy a **Szervizrendelések** képernyőn lehet manuálisan létrehozni.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9fbcdaa50a8f13247c13c1885cdb4ab7f5f39a47
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552230"
---
# <a name="create-service-orders-manually"></a>Szervizrendelések létrehozása manuálisan    

[!include [banner](../includes/banner.md)]


Szervizrendeléseket a szolgáltatási szerződésből vagy a **Szervizrendelések** képernyőn lehet manuálisan létrehozni. Projektekből is létre lehet hozni szervizrendelést.

> [!TIP]
> <P>Automatizált folyamatok segítségével hozhat létre szervizrendeléseket. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Szervizrendelés manuális létrehozása egy szolgáltatási szerződésből

1.  Kattintson a **Szolgáltatáskezelés** \> **Közös** \> **Szolgáltatási szerződések** \> **Szolgáltatási szerződések** lehetőségre.

2.  Válasszon ki egy szolgáltatási szerződést, vagy hozzon létre egy új szolgáltatási szerződést.

3.  Kattintson a **Szállítás** lapra, és a **Létrehozás** csoportban kattintson a **Tervezett szervizrendelések** lehetőségre a **Szervizrendelések létrehozása** képernyő megnyitásához.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Szervizrendelés manuális létrehozása a Szervizrendelések képernyőn

1.  Kattintson a következőkre: **Szolgáltatáskezelés** \> **Közös** \> **Szervizrendelések** \> **Szervizrendelések**.

2.  Nyomja le a CTRL+N billentyűkombinációt új szervizrendelés létrehozásához.

3.  Hozza létre a szervizrendelés szervizrendeléssorait.

> [!NOTE]
> <P>Ha a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Engedélyezés szolgáltatási szerződés nélkül</STRONG> jelölőnégyzete be van jelölve, akkor a szervizrendeléssorok tranzakcióit fel lehet adni anélkül, hogy szolgáltatási szerződéshez társítaná a szervizrendelést. Ha nincs bejelölve a jelölőnégyzet, akkor a kézzel létrehozott szervizrendelést társítani kell a projekthez a szervizrendeléssorok feladása előtt.</P>

## <a name="create-a-service-order-from-a-project"></a>Szervizrendelés létrehozása egy projektből

1.  Kattintson a következőkre: **Projektvezetés és könyvelés** \> **Közös** \> **Projektek** \> **Minden projekt**.

2.  A **Projektek** képernyőn, a **Műveleti ablakban**, kattintson a **Kezelés** lapra \> kattintson **Szolgáltatás** \>**Szervizrendelések** lehetőségre.

3.  Az előbbi eljárás segítségével hozza létre manuálisan a szervizrendelést a **Szervizrendelések** képernyőn. A **Projekt azonosító** mezőben látható a projektreferencia.

> [!NOTE]
> <P>Ha a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Engedélyezés szolgáltatási szerződés nélkül</STRONG> jelölőnégyzete be van jelölve, akkor a szervizrendeléssorok tranzakcióit fel lehet adni anélkül, hogy szolgáltatási szerződéshez társítaná a szervizrendelést. Ha nincs bejelölve a jelölőnégyzet, akkor a kézzel létrehozott szervizrendelést társítani kell a projekthez a szervizrendeléssorok feladása előtt.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Szervizrendelés létrehozása az értékesítési rendelés képernyőn

Szervizrendelést az **Értékesítési rendelések** képernyő használatával is létrehozhat; ehhez használja az **Új szervizrendelés létrehozása az értékesítési rendelés alapján** varázslót.

1.  Kattintson ide: **Értékesítés és marketing** \> **Közös** \> **Értékesítési rendelések** \> **Minden értékesítési rendelés**.

2.  Nyissa meg a megfelelő értékesítési rendelést.

3.  Az **Értékesítési rendelés** fülön kattintson a **Szervizrendelés** lehetőségre ahhoz, hogy elindítsa az **Új szervizrendelés létrehozása az értékesítési rendelés alapján varázslót**.

4.  Kattintson a **Tovább \>** gombra, majd végezze el a következő lépéseket a **Válassza ki a szerződést a szervizrendeléshez** lapon:
    
      - A **Szolgáltatási szerződés** mezőben válassza ki azt a szolgáltatási szerződést, amelyhez az új szervizrendelést társítani kívánja.
    
      - Nem kötelező: A **Projektazonosító** mező segítségével egy projekthez társíthatja a szervizrendelést.

5.  Kattintson a **Tovább \>** gombra, majd végezze el a következő lépéseket a **Szervizrendelés létrehozása** lapon:
    
      - Adja meg a szervizhívás indításának dátumát és időpontját a **Preferált szolgáltatási idő** mezőben.
    
      - Nem kötelező. módosítsa a **Leírás** mezőben szereplő szöveget. Alapértelmezés szerint ez a mező tartalmazza az előző lapon kiválasztott szolgáltatási szerződés leírását.
    
      - A **Felelős** mezőben válassza ki annak az alkalmazottnak az azonosítóját, aki felelős a szerződésért, illetve ha ismert, akkor adja meg annak a technikusnak az azonosítóját, akit az ügyfél előnyben részesít szervizhíváskor.
    
      - A **Kapcsolattartó azonosítója** mezőben válassza ki azt a személyt a vevő vállalatánál, akivel kapcsolatba kell lépni a szervizrendeléssel kapcsolatban.

6.  Kattintson a **Új\>** gombra, majd a **Befejezés** gombra.


## <a name="see-also"></a>Lásd még

[Szervizrendelések](service-orders.md)

[Szervizrendelések automatikus létrehozása](create-service-orders-automatically.md)

[Szervizrendelések létrehozása (osztályképernyő)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\)) 

