---
title: "A Súgó rendszer csatlakoztatása"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Operations súgórendszer komponenseit, áttekinti azok kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 86c7cb3961ba5170c32979e77aaa5f506ffac8a1
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="connect-the-help-system"></a>A Súgó rendszer csatlakoztatása

[!include[banner](../includes/banner.md)]


Ez a témakör a Microsoft Dynamics 365 for Operations súgórendszerének összetevőit írja le. Áttekinti ezen összetevők kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit. 

<a name="help-architecture"></a>Súgó-architektúra
-----------------

A következő ábra a Dynamics 365 for Operations rendszer súgórendszerének részeit jeleníti meg. A beépített súgórendszer lekéri a https://docs.microsoft.com Dynamics 365 for Operations Súgó webhelyen található cikkeket, valamint a Lifecycle Services (LCS) Üzletifolyamat-modellezőjében tárolt feladat-útmutatókat. 
**Megjegyzés:** A diagramban csillaggal (\**) szereplő funkciók tervbe vannak véve, de még nem érhetők el. [![Súgó-architektúra](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Csatlakozás a Súgó rendszerhez
A **Rendszerparaméterek** oldalon a rendszergazdák csatlakoztathatják a Súgó rendszer különböző darabjait az adott megvalósításhoz. [![Rendszerparaméterek – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) A **Rendszerparaméterek** lapon végezze el az alábbi lépéseket:

> [!IMPORTANT]
> Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz. Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.[![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)

1.  A csatlakozáshoz válassza ki a Lifecycle Services-projektet.
2.  Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.
3.  Adja meg a BPM könyvtárak megjelenítési sorrendjét. Ez meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.

Miután végrehajtotta ezeket a lépéseket nyissa meg a **Súgó** ablakot, és kattintson a **Feladat útmutatók** lapra. Ekkor megjelennek a Dynamics 365 for Operations rendszer aktuális oldalához kapcsolódó feladat-útmutatók. Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.

### <a name="showing-translated-task-guides"></a>Lefordított feladat-útmutatók megjelenítése

A honosított feladat-útmutatók először a 2016. májusi APQC Egyesített könyvtárban, valamint az Első lépések könyvtárban lettek szállítva. Ha szeretné a honosított feladat-útmutató súgóját látni a Dynamics 365 for Operations rendszerben, győződjön meg arról, hogy csatlakozva van a Május könyvtárhoz. Minden felhasználó esetében a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások határozzák meg a feladat-útmutató nyelvét. 

> [!NOTE]
> Annak ellenére, hogy sok feladat-útmutató le van már fordítva, a Dynamics 365 for Operations rendszer jelenleg nem jelzi a lefordított feladat-útmutatók neveit. Valamint csak a 2016. februárban megjelent feladat-útmutatók fordításai elérhetőek a májusi könyvtárban jelenleg. További fordításokat tartalmazó frissített könyvtárat fogunk megjelentetni hamarosan.
> -   Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.
> -   Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.

## <a name="creating-custom-help"></a>Egyéni súgó létrehozása
Lehetősége van egyéni súgót létrehozni saját Dynamics 365 for Operations példányához; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie. Partnerekhez, ha egy tárat vállalati kódtár előléptetett, és helyezze el a megoldás lesz a felhasználók számára érhető el. Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, majd a módosítást követően elmentheti a rögzítéseket a változtatásokkal együtt. További tudnivalókért lásd: [Dokumentációként használandó feladatrögzítés vagy oktatás létrehozása](../user-interface/task-recorder.md).

<a name="see-also"></a>Lásd még
--------

[Súgó áttekintése](help-overview.md)

[Feladatrögzítő áttekintése](../user-interface/task-recorder.md)

[Feladatrögzítés létrehozása dokumentációként vagy képzésként való felhasználás céljából](../user-interface/task-recorder-training-docs.md)





