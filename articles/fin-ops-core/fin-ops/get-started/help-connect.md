---
title: A Finance and Operations alkalmazások súgóélményének konfigurálása
description: Ez a témakör néhány Microsoft Dynamics 365 alkalmazáshoz tartalmaz tájékoztatást a Súgó rendszer összetevőiről. Bemutatja az alkalmazások csatlakoztatásának módját, valamint az egyéni súgó létrehozási folyamatának összegzését.
author: margoc
manager: AnnBe
ms.date: 05/11/2020
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
ms.openlocfilehash: 827d4cd14f497b79c85fb084a6295af13c5eb0c7
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367384"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>A Finance and Operations alkalmazások súgóélményének konfigurálása

[!include [banner](../includes/banner.md)]

Ebben a témakörben egy áttekintést talál a Finance and Operations alkalmazások súgórendszerének összetevőiről, például a Microsoft Dynamics 365 Finance, a Dynamics 365 Supply Chain Management, a Dynamics 365 Commerce és a Dynamics 365 Human Resources. A témakör emellett bemutatja az összetevők csatlakoztatásának módját, valamint az egyéni súgó létrehozási folyamatának összegzését.

## <a name="help-architecture"></a>Súgó-architektúra

A Finance and Operations alkalmazások fogalmi áttekintéseket és egyéb témaköröket tartalmaznak, amelyek a [https://docs.microsoft.com/dynamics365](/dynamics365/) webhelyen vannak közzétéve. Ez a tartalom később a termék **Súgó** paneljéből érthető el. A következő ábrán a súgórendszer részei láthatók.

[![Súgó-architektúra](./media/help-architecture.png)](./media/help-architecture.png)

A terméken belüli súgórendszer a docs.microsoft.com webhelyről és egyéb kapcsolódó webhelyekről olvas be cikkeket. Ezenkívül a Microsoft Dynamics Lifecycle Services (LCS) Üzletifolyamat-modellező (BPM) alkalmazásában tárolt feladat-útmutatókat is beolvas.

## <a name="adding-task-guides"></a>Feladat-útmutatók hozzáadása

> [!NOTE]
> A **Feladat-útmutatók** lap jelenleg nem érhető el az Human Resources vagy a Commerce alkalmazásban. <!--We are currently working to enable this functionality in a future release.--> A Human Resources Első lépések részének feladat-útmutatói azonban továbbra is rendelkezésre állnak az alapvető funkciók ismertetéséhez. Az eljárási Súgó a [https://docs.microsoft.com/dynamics365](/dynamics365/) webhelyről is elérhető, mind a Human Resources, mind a Commerce számára.

A **Rendszerparaméterek** oldalon a rendszeradminisztrátorok konfigurálhatják egy megvalósítás releváns feladat-útmutató könyvtáraihoz való hozzáférést.

> [!NOTE]
> - A Súgó konfigurálásához be kell lépnie egy ugyanattól a bérlőtől származó fiókba, amiben az alkalmazás is telepítve van.
> - Helyi virtuális merevlemezen (VHD) futó alkalmazáspéldánnyal nem lehet csatlakozni az LCS könyvtárhoz.

[![Rendszerparaméterek űrlap – súgó beállításai](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

A megoldás feladat-útmutatóinak konfigurálásához kövesse az alábbi lépéseket a **Rendszerparaméterek** oldalon.

> [!IMPORTANT]
> Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz. Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.
>
> [![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Kapcsolódás az LCS szolgáltatáshoz")](./media/connect-to-lcs-crop.png)

1. A csatlakozáshoz válassza ki a Lifecycle Services-projektet.
2. Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.
3. Adja meg a BPM könyvtárak megjelenítési sorrendjét. A megjelenítési sorrend meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.

Miután végrehajtotta ezeket a lépéseket, nyissa meg a **Súgó** ablakot, és kattintson a **Feladat-útmutatók** lapra. Ekkor megjelennek a Finance and Operations-alkalmazások aktuális oldalához kapcsolódó feladat-útmutatók. Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.

### <a name="showing-translated-task-guides"></a>Lefordított feladat-útmutatók megjelenítése

A honosított feladat-útmutatók először a 2016. májusi APQC Egyesített könyvtárban, valamint az Első lépések könyvtárban lettek szállítva. Ha szeretné a honosított feladat-útmutató súgóját látni, győződjön meg róla, hogy a Dynamics 365 megoldása csatlakoztatva van a 2016. május könyvtárhoz. A felhasználók a **Beállítások** &gt; **Beállítások** menüben található nyelvi beállítások alatt módosíthatják a feladat-útmutató megjelenítési nyelvét.

> [!NOTE]
> Annak ellenére, hogy sok feladat-útmutató le van már fordítva, az ügyfél jelenleg nem jelzi a lefordított feladat-útmutatók neveit. Valamint csak a 2016. februárban megjelent feladat-útmutatók fordításai elérhetőek a 2016. május könyvtárban jelenleg. A Microsoft további fordításokat tartalmazó frissített könyvtárat fog megjelentetni hamarosan.
>
> - Ha egy feladat-útmutató le van fordítva, akkor a kiválasztott nyelven fog megjelenni a feladat-útmutató teljes szövege.
> - Ha egy feladat-útmutató még nincs lefordítva, akkor a kiválasztott nyelven csak néhány szöveg (a vezérlők szövegei) fog megjelenni.

## <a name="adding-custom-help"></a>Egyéni súgó hozzáadása

A feladat-útmutatók használatával egyéni súgót hozhat létre, vagy csatlakoztathat egy egyéni Súgó webhelyet a **Súgó** panelhez.

### <a name="create-custom-help-by-using-task-guides"></a>Egyéni súgó létrehozása feladat-útmutatókkal

Lehetősége van egyéni súgót létrehozni a támogatott alkalmazásokhoz; ehhez létre kell hoznia az egyedi megoldásokat magukban foglaló feladatrögzítéseket, majd azokat egy LCS Üzletifolyamat-tárba kell mentenie. A Human Resources rendszerben nem hozhat létre egyéni feladat-útmutatókat.

Ha partnerként hozzájárul egy könyvtárral egy vállalati tár kialakításához, valamint beilleszti azt egy megoldásba, akkor az a vevői számára elérhetővé válik. Ezenkívül az APQC Egyesített globális tárról is készíthet másolatot; megnyithatja a saját másolatot és az abban található feladatrögzítéseket, szerkesztheti őket, majd elmentheti a módosításait. További tájékoztatás: [Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-help-site"></a>Egyéni súgóoldal csatlakoztatása

A Finance and Operations alkalmazások ritkán használatosak a gyári állapotukban. Helyette a megoldást testreszabják, és kiterjesztik, hogy megfeleljen a szervezet igényeihez. A Súgó élményét testreszabhatja és ki is bővítheti. Lehetőség van például egyéni súgó hozzáadására a terméken belüli **Súgó** panelen.

A Microsoft egy eszközkészletet biztosít egyéni súgók telepítéséhez és csatlakoztatásához a **Súgó** panelen. A **Súgó** panelhez kapcsolt egyéni súgótartalom beállításával kapcsolatos tudnivalókat lásd: [Egyéni Súgó – áttekintés](../../dev-itpro/help/custom-help-overview.md).

Ha együtt szeretne működni a Microsofttal a Súgó testreszabásához szükséges eszközökkel és folyamatokkal kapcsolatban, töltse ki a következő címen található űrlapot: [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Lásd még

[Súgórendszer](help-overview.md)  
[Egyéni Súgó – áttekintés](../../dev-itpro/help/custom-help-overview.md)  
[Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md)  
[Dokumentáció vagy képzés létrehozása Feladatrögzítő segítségével](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Egyéni súgó GitHub-tárház](https://github.com/microsoft/dynamics356f-o-custom-help)  
