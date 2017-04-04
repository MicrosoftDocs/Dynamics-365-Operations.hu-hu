---
title: "A Költségkönyvelés elemzése kiemelt BI tartalom biztonsági beállítása"
description: "Ez a témakör ismerteti, hogyan kerülhet sor szintű biztonság a Microsoft kiemelt BI Költségkönyvelés biztonsági hozzáférési szintjét. Ez a funkció segít garantálni, hogy a felhasználók csak hozzáférést kapnak kiemelt BI adatokat látni."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1e42622e7621c645d7eda3299f78c34c7e41a251
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>A Költségkönyvelés elemzése kiemelt BI tartalom biztonsági beállítása

Ez a témakör ismerteti, hogyan kerülhet sor szintű biztonság a Microsoft kiemelt BI Költségkönyvelés biztonsági hozzáférési szintjét. Ez a funkció segít garantálni, hogy a felhasználók csak hozzáférést kapnak kiemelt BI adatokat látni.

<a name="overview"></a>Áttekintés
--------

A **a Költségkönyvelés elemzés** Microsoft Power BI tartalom kiemelt BI sor szintű biztonságot használ, a felhasználó hozzáférését korlátozni. Biztonság a hozzáférési szintű szervezeti hierarchiát, a költségkönyvelési paraméterek beállítása alapján történik. További információt a **költségkönyvelési elemzés** Power BI tartalom, lásd: [költségkönyvelési elemzés kiemelt BI-tartalom](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Beállítás
Terjesztése kiemelt BI hozzáférési szintű adatvédelmet, a kiemelt BI tartalom tulajdonosának kell kövesse az alábbi lépéseket. **Megjegyzés:** közzéteszi a felhasználó a **a Költségkönyvelés elemzés** Power BI tartalom automatikusan lesz a tulajdonosa. Csak egy tulajdonos két kiemelt biztonsági lehet beállítani. Ezenkívül addig, amíg a tulajdonos más felhasználók PowerBI.com ad hozzá, senki, kivéve a tulajdonos tekintheti meg az adatokat a **költségkönyvelési elemzés** Power BI-tartalom.

1.  A definíciós fájl közzététele kiemelt BI.
2.  Jelentkezzen be PowerBI.com.
3.  Az adathalmazban található a **a Költségkönyvelés elemzés** Power BI-tartalom.
4.  Nyissa meg a Biztonság lapot. 

    [![A Biztonság lap megnyitása](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)

5.  A **költség objektum vezérlő** szerepkör már létre van hozva. A Költségkönyvelés hozzáférési szintű szervezeti hierarchia egy részét más tagok hozzáadásához. 

    [![Tagok hozzáadása](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)

Felhasználók adódnak hozzá a **költség objektum vezérlő** szerepkört fogja látni csak azokat az adatokat, amelyek jogosultak a Költségkönyvelés hozzáférési szintű szervezeti hierarchiában szereplő meghatározás szerint, lásd:. **Megjegyzés:** sor szintű biztonsági mozaik vonatkozik, illetve műveletek kiemelt BI a beágyazott Microsoft Dynamics 365 jelentések.

## <a name="updating-security"></a>Biztonsági frissítése
Ha frissítések történnek a Költségkönyvelés biztonsági hozzáférési szint, és azt szeretné, hogy a frissítések megfelelően kiemelt BI, frissítenie kell a szervezet tárolója a **költségkönyvelési elemzés** Power BI-tartalom. Miután befejezte a Dynamics 365 műveletek tároló entitás frissítést, frissítenie kell az eltérések a PowerBI.com. Egy entitás store frissítés módjáról további információt lásd: [frissítés entitás üzlet](power-bi-integration-entity-store.md#update-entity-store). Tulajdonosa a **a Költségkönyvelés elemzés** BI kiemelt tartalom is kell tennie tároló entitás frissítést, ha új felhasználók hozzáférést kapnak a szervezeti hierarchia. Továbbá, a tulajdonos az új felhasználók hozzá kell adnia a **költség objektum vezérlő** PowerBI.com, így alkalmazzák őket, hogy a sor szintű biztonsági szerepköre.

## <a name="disabling-security"></a>Biztonsági letiltása
Feltételezzük, hogy a vállalat által az adatokhoz való hozzáférést. Ha valamilyen okból a biztonsági paraméterek le van tiltva a Költségkönyvelés futtatásakor, a tulajdonos felhasználókat kell hozzáadni a **költség könyvelő** BI kiemelt szerepet inkább. Ha egy engedélyezett államból biztonsági módosítja a letiltott állapotú, tanácsos eltávolítása a a **költség objektum vezérlő** szerepkört. És ez fordítva is igaz, ha újra engedélyezi a biztonsági. A felhasználók mindkét szerepkört is tartozhat. Közös az Unió mindkét szerepkört is. Abban az esetben, a **a Költségkönyvelés elemzés** Power BI tartalom közös hozzáféréssel rendelkező felhasználók adatokhoz való hozzáférés korlátozás nélkül. Célja, hogy a korlátozott hozzáférésű alkalmazni, ha a felhasználók csak kell hozzárendelni a **költség objektum vezérlő** szerepkört. Sor szintű biztonsági frissítésekkel azonnal érvénybe lépnek. Érintett felhasználók böngészőprogramjukkal frissíteni kell.

## <a name="additional-resources"></a>További erőforrások
További információt a Power BI sor szintű biztonság, lásd: [kezelésére a modell két kiemelt biztonsági](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).


