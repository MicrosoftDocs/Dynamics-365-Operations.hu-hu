---
title: "A Súgó rendszer csatlakoztatása"
description: "Ez a témakör bemutatja a Microsoft Dynamics 365 for Finance and Operations súgórendszer komponenseit, áttekinti azok kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit."
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c0942b66859da3659be49b19986bfd146ac43130
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="connect-the-help-system"></a>A Súgó rendszer csatlakoztatása

[!INCLUDE [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 for Finance and Operations súgórendszerének összetevőit írja le. Áttekinti ezen összetevők kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit. 

## <a name="help-architecture"></a>Súgó-architektúra
A következő ábra a Finance and Operations rendszer súgórendszerének részeit jeleníti meg. A beépített súgórendszer lekéri a https://docs.microsoft.com Finance and Operations Súgó webhelyen található cikkeket, valamint a Lifecycle Services (LCS) Üzletifolyamat-modellezőjében tárolt feladat-útmutatókat. 
> [!NOTE]
> A diagramban csillaggal (\*) szereplő funkciók tervbe vannak véve, de még nem érhetők el. [![Súgó-architektúra](./media/help-architecture.png)](./media/help-architecture.png)


## <a name="connecting-the-help-system"></a>Csatlakozás a Súgó rendszerhez
> [!NOTE]
> A **Feladat-útmutatók** lap jelenleg nem áll rendelkezésre a Microsoft Dynamics 365 for Talent és a Microsoft Dynamics 365 for Retail esetében. Jelenleg azon dolgozunk, hogy a funkcionalitás engedélyezett legyen valamelyik jövőbeli programverzióban. A Talent Első lépések részének feladat-útmutatói továbbra is rendelkezésre állnak az alapvető funkciók ismertetéséhez. Az eljárások lépéseit ismertető súgó is elérhető a docs.microsoft.com webhelyen ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) mind a Retail, mind a Talent esetében.


A **Rendszerparaméterek** oldalon a rendszergazdák csatlakoztathatják a Súgó rendszer különböző darabjait az adott megvalósításhoz. [![Rendszerparaméterek – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) A **Rendszerparaméterek** lapon végezze el az alábbi lépéseket:

> [!IMPORTANT]
> Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz. Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.[![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Kapcsolódás az LCS szolgáltatáshoz")](./media/connect-to-lcs-crop.png)

1.  A csatlakozáshoz válassza ki a Lifecycle Services-projektet.
2.  Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.
    - A Finance and Operations Microsoft-tartalom esetében válassza ki a legújabb Microsoft Dynamics 365 Finance and Operations APQC Egyesített könyvtárat. 
    - A Retail esetében a könyvtárat a közeljövőben adjuk ki. 
    - A Talent esetében nem kell könyvtárat választani – a kapcsolatot a megfelelő könyvtárhoz létrehozzuk Önnek. 

3.  Adja meg a BPM könyvtárak megjelenítési sorrendjét. Ez meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.

Miután végrehajtotta ezeket a lépéseket, nyissa meg a **Súgó** ablakot, és kattintson a **Feladat-útmutatók** lapra. Ekkor megjelennek a Finance and Operations aktuális oldalához kapcsolódó feladat-útmutatók. Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.

### <a name="showing-translated-task-guides"></a>Lefordított feladat-útmutatók megjelenítése

A honosított feladat-útmutatók először a 2016. májusi APQC Egyesített könyvtárban, valamint az Első lépések könyvtárban lettek szállítva. Ha szeretné a honosított feladat-útmutató súgót látni a Finance and Operationsben, győződjön meg arról, hogy csatlakozva van a májusi könyvtárhoz. Minden felhasználó esetében a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások határozzák meg a feladat-útmutató nyelvét. 

> [!NOTE]
> Annak ellenére, hogy sok feladat-útmutató le van már fordítva, a Finance and Operations rendszer jelenleg nem jelzi a lefordított feladat-útmutatók neveit. Valamint csak a 2016. februárban megjelent feladat-útmutatók fordításai elérhetőek a májusi könyvtárban jelenleg. További fordításokat tartalmazó frissített könyvtárat fogunk megjelentetni hamarosan.
> -   Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.
> -   Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.

## <a name="creating-custom-help"></a>Egyéni súgó létrehozása
Lehetősége van egyéni súgót létrehozni saját Finance and Operations és Retail példányához; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie. A Talent rendszerben nem hozhat létre egyéni feladat-útmutatókat. 

Partnerekhez, ha egy tárat vállalati kódtár előléptetett, és helyezze el a megoldás lesz a felhasználók számára érhető el. Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, majd a módosítást követően elmentheti a rögzítéseket a változtatásokkal együtt. További tudnivalókért lásd: [Dokumentációként használandó feladatrögzítés vagy oktatás létrehozása](../../dev-itpro/user-interface/task-recorder.md).

<a name="see-also"></a>Lásd még
--------

[Súgó áttekintése](help-overview.md)

[Feladatrögzítő áttekintése](../../dev-itpro/user-interface/task-recorder.md)

[Feladatrögzítés létrehozása dokumentációként vagy képzésként való felhasználás céljából](../../dev-itpro/user-interface/task-recorder-training-docs.md)





