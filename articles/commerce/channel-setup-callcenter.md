---
title: Hívásközpont csatorna beállítása
description: Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
manager: annbe
ms.date: 03/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3f8c47c00b920dae01213d1d241ac8ee6a18d4e3
ms.sourcegitcommit: 4c6d31f3ebd88212d3d1497a4bba9c64c5300444
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/24/2020
ms.locfileid: "4413014"
---
# <a name="set-up-a-call-center-channel"></a>Hívásközpont csatorna beállítása


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet egy új hívásközpont csatornát létrehozni a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés


A Dynamics 365 Commerce szolgáltatásban a hívásközpont egyfajta kereskedelmi csatorna, amelyet az alkalmazásban lehet megadni. Ha meghatároz egy csatornát a hívásközpont entitások számára, azzal a rendszer képes lesz specifikus adatok és megrendelések feldolgozásához tartozó alapértelmezéseket értékesítési rendelésekhez kötni. Noha egy vállalat több hívásközpont-csatornát is megadhat a Commerce-ben, fontos megjegyezni, hogy egy egyéni felhasználót csak egy hívásközpont-csatornához lehet hozzárendelve. 

Új hívásközpont-csatorna létrehozása előtt győződjön meg arról, hogy végrehajtotta a [Csatornbeállítás előfeltételeit](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Új hívásközpont csatorna létrehozása és konfigurálása

Új hívásközpont csatorna létrehozásához és konfigurálásához kövesse ezeket a lépéseket.

1. A navigációs panelen ugorjon a következő oldalra: **Kiskereskedelem és kereskedelem \> Csatornák \> Hívásközpontok \> Összes hívásközpont**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Név** mezőben adja meg az új csatorna nevét.
1. Válassza ki a megfelelő **Jogi személyt** a legördülő listából.
1. Válassza ki a megfelelő **Raktár** helyet a legördülő listából. Ezt a helyet használja a rendszer alapértelmezettként az adott hívásközpont-csatornához létrehozott értékesítési rendeléseknél, hacsak az ügyfél vagy a cikk szintjén nincs más alapértelmezés meghatározva.
1. Az **Alapértelmezett ügyfél** mezőben adjon meg egy érvényes alapértelmezett ügyfelet. Ezek az adatok az új vevői rekordok létrehozásakor az alapértelmezések automatikus feltöltésekor segítenek. A hívásközpont rendelések létrehozásakor nem tanácsos rendeléseket létrehozni az alapértelmezett vevőhöz.
1. Az **E-mail értesítési profilja** mezőben adjon meg egy érvényes e-mail-értesítési profilt. A hívásközpont-rendelések létrehozásakor és feldolgozásakor a rendszer az e-mail értesítési profilt használja a vevők számára a rendelési állapottal kapcsolatos automatikus figyelmeztetéséhez.
1. Adja meg az **Ár-felülbírálás** infókódot. Elképzelhető, hogy először létre kell hoznia egy információs kódot. Ez az információs kód olyan okkódok csoportját biztosítja, amelyet a felhasználó a hívási központ árának felülbírálási funkciójának használata esetén a programtól megadhat.
1. Adja meg a **Várakoztatási kód** infókódot. Elképzelhető, hogy először létre kell hoznia egy információs kódot. Ez az információs kód olyan nem kötelező okkódok csoportját biztosítja, amelynek kiválasztására a rendszer felszólítja a felhasználót, amikor várakoztatott állapotba helyez egy megrendelést.
1. Adja meg a **Hitel** infókódot. Elképzelhető, hogy először létre kell hoznia egy információs kódot. Ez az információs kód olyan okkódkészletet biztosít, amelyből a felhasználónak választania kell a hívásközpont megrendelési jóváírás funkciójának használatakor, ahol egyéb jellegű visszatérítést kell adni az ügyfélnek ügyfélszolgálati okokból.
1. Nem kötelező: A **Pénzügyi dimenziók** gyorslapon adjon meg pénzügyi dimenziókat. Az itt megadott dimenziók alapértelmezett értékként jelennek meg a hívásközpont-csatornában létrehozott értékesítési rendeléseken.
1. Kattintson a **Mentés** gombra.

A következő kép bemutatja egy új hívásközpont csatorna létrehozását.

![Új hívásközponti csatorna](media/channel-setup-callcenter-1.png)

A következő kép egy példát mutat a hívásközpont csatornára.

![Hívásközponti csatorna – példa](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>További csatornák beállítása

A hívásközpont csatorna beállításához szükséges további feladatok közé tartozik a fizetési módok és szállítási módok beállítása.

A következő képen láthatók a **Szállítási módok** és a **Fizetési módok** beállított lehetőségei a **Beállítás** lapon.

![További hívásközpont-csatorna-beállítási műveletek](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Fizetési módok beállítása

A fizetési módok beállításához a csatornán támogatott valamennyi fizetési típusnál kövesse az alábbi lépéseket. A felhasználóknak be kell jelölni az előre definiált fizetési módokat, hogy a hívásközpont csatornához kapcsolják őket. Mielőtt beállítja a hívásközpont fizetési módszereit, először állítsa be a fizetés alapvető módszereit a **Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Fizetési módszerek \> Fizetési módszerek** pontban.

1. A műveleti ablaktáblán válassza a **Beállítás** lapot, majd válassza ki a **Fizetési módokat**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. A navigációs ablakban válasszon ki egy fizetési módot az előre meghatározott kifizetésekhez.
1. Adja meg a fizetési típushoz szükséges további beállításokat. Hitelkártyák, ajándékutalványok vagy törzsvásárlói kártyák esetében a **kártya beállítási** funkciójának kiválasztásával további beállításokat kell megadni. 
1. A **feladás** szakasz kifizetési típusához konfigurálja a megfelelő feladási fiókokat.
1. A Művelet panelen kattintson a **Mentés** elemre.

A következő kép egy példát mutat a készpénzfizetési módra.

![Fizetési módok – példa](media/channel-setup-callcenter-payments.png)

### <a name="set-up-modes-of-delivery"></a>Szállítási módok beállítása

A konfigurált szállítási módokat a **Szállítási módok** kiválasztásával tekintheti meg a **Beállítás** lapon a **Műveleti ablaktáblán**.  

Ha módosítani szeretné vagy hozzáadna egy szállítási módot, amelyet a hívásközpont-csatornához társítana, kövesse az alábbi lépéseket.

1. A hívásközpont szállítási módok képernyőjén válassza a **Szállítási módok kezelése** lehetőséget
1. A műveleti ablaktáblán válassza az **Új** elemet új szállítási mód létrehozásához, vagy válasszon meglévő módot.
1. A **kiskereskedelmi csatornák** területen válassza a **sor hozzáadása** parancsot a hívásközpont-csatorna hozzáadásához. Csatornák hozzáadása a szervezeti csomópontok használatával, nem pedig az egyes csatornák hozzáadásával egyszerűsítheti a csatornák hozzáadását.
1. Ellenőrizze, hogy a szállítási mód be van-e állítva a **termékek** gyorslap és a **címek** gyorslap adataival. Ha a szállítási mód esetében nem érvényes egyik termék vagy szállítási cím sem, akkor a rendelésbevitel során a rendszer hibákat eredményez.
1. Miután bármilyen módosítás történt a hívásközpont szállításimód-konfigurációknál, a **Szállítási módok feldolgozása** feladatot futtatni kell a módosítási mátrix alábontásához. Ez a feladat a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Szállítási módok feldolgozása** pontban található.

A következő kép egy példát mutat a szállítási módra.

![Szállítási módok beállítása](media/channel-setup-retail-7.png)

### <a name="set-up-channel-users"></a>Csatornafelhasználók beállítása

Ha a Commerce központból a hívásközpont-csatornához kapcsolódó értékesítési rendelést szeretne létrehozni, akkor az értékesítési rendelést létrehozó felhasználónak a hívásközpont csatornához kell kapcsolódnia. A felhasználó nem kapcsolhat manuálisan a Commerce központ alkalmazásban létrehozott értékesítési rendelést a hívásközpont csatornához. A hivatkozás rendszerezett, és a felhasználónm és a felhasználó kapcsolatán alapul a hívásközpont-csatornával. Egy felhasználó csak egy hívásközpont-csatornához kapcsolható.

1. A műveleti ablaktáblán válassza a **Csatorna** lapot, és válassza ki a **Csatornafelhasználókat**.
1. A műveleti ablaktáblán kattintson az **Új** elemre.
1. Egy meglévő **Felhasználói azonosító** kiválasztásával a legördülő listából összekapcsolhatja a felhasználót a hívási központ csatornával

Miután kész a csatornafelhasználó beállítása, és a felhasználó létrehoz egy új értékesítési rendelést a Commerce központban, a rendszer az értékesítési rendelést hozzákapcsolja a társított hívásközpont-csatornához. A csatorna minden konfigurációját módszeresen fogja alkalmazni az értékesítési rendelésre. A felhasználó megadhatja, hogy az értékesítési rendelés melyik hívásközpont-csatornához kapcsolódik, és az értékesítési rendelés fejlécében megtekinti a csatorna nevének hivatkozását.


### <a name="set-up-price-groups"></a>Árcsoportok beállítása

Az árcsoport megadása nem kötelező, de ha megadja, szabályozhatja, hogy mely eladási árakat ajánlja fel a program a hívásközpont-csatornában a vevők számára. Ha nincs beállítva árcsoport a vevőhöz, vagy ha a katalógusban szereplő árcsoport nem az értékesítési rendelésen van alkalmazva (a hívásközpont rendelési fejléc **forráskód-azonosító** mezője alapján), akkor a csatorna árcsoport a cikkek árának megtalálására szolgál. Ha egy árcsoport nem található a hívásközpont csatornán, akkor a rendszer az alapértelmezett cikkek alapárát használja. 

Egy árcsoport beállításához hajtsa végre a következő műveleteket.

1. A műveleti ablaktáblán válassza a **Csatorna** lapot, és válassza ki az **Árcsoportokat**.
1. A műveleti panelen kattintson az **Új** elemre.
1. **Kiskereskedelmi árcsoport** kiválasztása a legördülő listából.

## <a name="additional-resources"></a>További erőforrások

[Csatorna beállításainak előfeltételei](channels-prerequisites.md)

[Hívásközpont értékesítési funkciói](call-center-functionality.md)

[Hívásközpont rendelésfeldolgozási beállításainak meghatározása](set-up-order-processing-options.md)

[Hívásközpont-katalógusok](call-center-catalogs.md)

[Csalással kapcsolatos figyelmeztetések beállítása és használata](set-up-fraud-alerts.md)

[Folytonossági programok beállítása hívásközpontok számára](set-up-continuity-program.md)
