---
title: A Súgórendszer csatlakoztatása
description: Ez a témakör bemutatja a Súgó rendszer komponenseit a Finance and Operations alkalmazásban, áttekinti azok kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4427388d75c1aef40a978ce35c831d5b714f2562
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006172"
---
# <a name="connect-the-help-system"></a>A Súgórendszer csatlakoztatása

[!include [banner](../includes/banner.md)]

Ez a témakör a Finance and Operations alkalmazások – például Dynamics 365 Finance, Supply Chain Management, Commerce és Human Resources – súgórendszerének összetevőit ismerteti. Áttekinti ezen összetevők kapcsolatát, valamint összefoglalja az egyéni súgó létrehozásának módszereit.

## <a name="help-architecture"></a>Súgó-architektúra

A következő ábrán a súgórendszer részei láthatók. A termék súgója a https://docs.microsoft.com webhelyről tölt le cikkeket, valamint az itt tárolt feladat-útmutatókat használja: Business Process Modeler in Lifecycle Services (LCS).

> [!NOTE]
> A diagramban csillaggal (\*) szereplő funkciók tervbe vannak véve, de még nem érhetők el.

[![Súgó-architektúra](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Csatlakozás a Súgó rendszerhez

> [!NOTE]
> A **Feladat-útmutatók** lap jelenleg nem érhető el a Microsoft Dynamics 365 Human Resources és Commerce alkalmazásban. Jelenleg azon dolgozunk, hogy a funkcionalitás engedélyezett legyen valamelyik jövőbeli programverzióban. A Human Resources Első lépések részének feladat-útmutatói továbbra is rendelkezésre állnak az alapvető funkciók ismertetéséhez. Az eljárási Súgó a docs.microsoft.com webhelyről is elérhető, mind a Human Resources, mind a Commerce számára.

A **Rendszerparaméterek** oldalon a rendszergazdák csatlakoztathatják a Súgó rendszer különböző darabjait az adott megvalósításhoz.

[![Rendszerparaméterek űrlap – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

A **Rendszer paraméterei** oldalon kövesse az alábbi lépéseket:

> [!IMPORTANT]
> Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz. Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.
>
> [![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Kapcsolódás az LCS szolgáltatáshoz")](./media/connect-to-lcs-crop.png)

1. A csatlakozáshoz válassza ki a Lifecycle Services-projektet.
2. Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.
3. Adja meg a BPM könyvtárak megjelenítési sorrendjét. Ez meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.

Miután végrehajtotta ezeket a lépéseket, nyissa meg a **Súgó** ablakot, és kattintson a **Feladat-útmutatók** lapra. Ekkor megjelennek a Finance and Operations-alkalmazások aktuális oldalához kapcsolódó feladat-útmutatók. Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.

### <a name="showing-translated-task-guides"></a>Lefordított feladat-útmutatók megjelenítése

A honosított feladat-útmutatók először a 2016. májusi APQC Egyesített könyvtárban, valamint az Első lépések könyvtárban lettek szállítva. Ha szeretné a honosított feladat-útmutató súgót látni a Finance and Operations-alkalmazásokban, győződjön meg róla, hogy csatlakozva van a Május könyvtárhoz. Minden felhasználó esetében a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások határozzák meg a feladat-útmutató nyelvét.

> [!NOTE]
> Megjegyzés: Annak ellenére, hogy sok feladat-útmutató le van már fordítva, az ügyfél jelenleg nem jelzi a lefordított feladat-útmutatók neveit. Valamint csak a 2016. februárban megjelent feladat-útmutatók fordításai elérhetőek a májusi könyvtárban jelenleg. További fordításokat tartalmazó frissített könyvtárat fogunk megjelentetni hamarosan.
>
> - Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.
> - Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.

## <a name="creating-custom-help"></a>Egyéni súgó létrehozása

Használhatja a feladat-útmutatókat az egyéni súgó létrehozásáhot, vagy hozzákapcsolhat egy webhelyet a Súgópanelhez.

### <a name="create-custom-help-with-task-guides"></a>Egyéni súgó létrehozása feladat-útmutatókkal

Lehetősége van egyéni súgót létrehozni saját Finance, Supply Chain Management és Commerce példányához; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie. A Human Resources rendszerben nem hozhat létre egyéni feladat-útmutatókat.

Partnerekhez, ha egy tárat vállalati kódtár előléptetett, és helyezze el a megoldás lesz a felhasználók számára érhető el. Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, majd a módosítást követően elmentheti a rögzítéseket a változtatásokkal együtt. További tájékoztatás: [Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Egyéni webhely csatlakoztatása

A Microsoft rendelkezésre bocsátott egy ismertetőt és mintakódot, amely leírja, hogy hogyan lehet egy egyéni súgówebhelyet létrehozni, és a Súgópanelhez csatlakoztatni. További tájékoztatás:

- [Egyéni Súgó létrehozása a Finance and Operations-alkalmazásokhoz (ismertető)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Egyéni súgó GitHub-tárház](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>További erőforrások

[Súgórendszer](help-overview.md)

[Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md)

[Dokumentáció vagy képzés létrehozása Feladatrögzítő segítségével](../../dev-itpro/user-interface/task-recorder-training-docs.md)
