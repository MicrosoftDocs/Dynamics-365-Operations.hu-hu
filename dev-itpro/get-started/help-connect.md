---
title: "A Súgó rendszer csatlakoztatása"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Operations súgórendszer komponenseit, áttekinti azok kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 5ac5e30cff2239f601778001368fa7aaba478f5c
ms.lasthandoff: 03/31/2017


---

# <a name="connect-the-help-system"></a>A Súgó rendszer csatlakoztatása

Ez a témakör ismerteti az összetevők a súgóban a Microsoft Dynamics 365 műveletekhez. Áttekintést csatlakozás ezeket az összetevőket, és bemutatja, hogyan hozhat létre egyéni összefoglaló súgóját. 

<a name="help-architecture"></a>Súgó-architektúra
-----------------

A következő ábrán a Dynamics 365 műveletek a Súgó rendszer részei. A termék súgója a Dynamics 365 műveletek hely https://docs.microsoft.com, valamint az üzleti folyamat modellező életciklus-szolgáltatások (LCS) tárolt feladat segédvonalak cikkek lekéri. 
**Megjegyzés:** a diagram egy csillag szerepel a szolgáltatások (\*) tervezett, de még nem állnak rendelkezésre. [![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Csatlakozás a súgóban
Segítségével a **Rendszerparaméterek** lapon a rendszergazdák csatlakozni a darabok megvalósítását a súgóban. [![Súgó beállításait a rendszer paraméterei képernyő](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) meg a **Rendszerparaméterek** lap, kövesse az alábbi lépéseket:

1.  **Fontos:** az első megnyitásakor a **segítségével** lap, csatlakoznia kell a szolgáltatások életciklus. Győződjön meg arról, hogy kattintson a hivatkozásra a képernyő közepén, várjon, amíg a kapcsolat, zárja be a párbeszédpanelt, és kattintson **OK** eljut a **Rendszerparaméterek** oldalon. [![Csatlakozni LCS](./media/connect-to-lcs-crop-1024x365.png "csatlakozni LCS")](./media/connect-to-lcs-crop.png)
2.  A csatlakozáshoz válassza ki a Lifecycle Services-projektet.
3.  Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.
4.  Adja meg a BPM könyvtárak megjelenítési sorrendjét. Ez meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.

Miután végrehajtotta ezeket a lépéseket nyissa meg a **Súgó** ablakot, és kattintson a **Feladat útmutatók** lapra. Ekkor megjelennek a Dynamics 365 for Operations rendszer aktuális oldalához kapcsolódó feladat-útmutatók. Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.

### <a name="showing-translated-task-guides"></a>Lefordított feladat-útmutatók megjelenítése

Lefordított feladat segédvonalak először leszállították a május 2016 az APQC egyesített, és a bevezetés függvénytárak. Ha szeretné a honosított feladat-útmutató súgóját látni a Dynamics 365 for Operations rendszerben, győződjön meg arról, hogy csatlakozva van a Május könyvtárhoz. A nyelvi tevékenység segédvonal jelenik meg a minden felhasználó vezérli a nyelvi beállítások **beállítások**&gt;**beállítások**. **Megjegyzés:** Annak ellenére, hogy sok feladat-útmutató le van már fordítva, a Dynamics 365 for Operations rendszer jelenleg nem jelzi a lefordított feladat-útmutatók neveit. Is csak február 2016 kiadott feladat segédvonalak a fordítás a május könyvtárban találhatók. További fordításokat tartalmazó frissített könyvtárat fogunk megjelentetni hamarosan.

-   Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.
-   Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.

## <a name="creating-custom-help"></a>Egyéni súgó létrehozása
Lehetősége van egyéni súgót létrehozni saját Dynamics 365 for Operations példányához; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie. Partnerekhez, ha egy tárat vállalati kódtár előléptetett, és helyezze el a megoldás lesz a felhasználók számára érhető el. Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, majd a módosítást követően elmentheti a rögzítéseket a változtatásokkal együtt. További tudnivalókért lásd: [létrehozása a feladat felvétel dokumentáció használatára vagy képzési](../user-interface/task-recorder.md).

<a name="see-also"></a>Lásd még
--------

[Help overview](help-overview.md)

[Feladat Hangrögzítő – áttekintés](../user-interface/task-recorder.md)

[Feladatrögzítés létrehozása dokumentációként vagy képzésként való felhasználás céljából](../user-interface/task-recorder-training-docs.md)

[Új képzési könyvtárak létrehozása a Dynamics 365 üzemeltetéshez életciklus szolgáltatások a feladatrögzítővel (külső hivatkozás)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


