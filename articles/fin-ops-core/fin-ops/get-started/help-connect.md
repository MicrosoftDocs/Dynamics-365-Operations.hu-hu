---
title: A Súgó tapasztalatának konfigurálása a Pénzügy és az Üzemeltetés alkalmazáshoz
description: Ez a cikk a súgórendszer egyes Microsoft Dynamics 365-ös alkalmazásokhoz szükséges összetevőiről nyújt tájékoztatást.
author: edupont04
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: edupont
ms.search.region: Global
ms.author: edupont
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.form: SystemParameters
ms.openlocfilehash: 2c45a203303181c7ea23e20f8fa1bdce1c827aa2
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462224"
---
# <a name="configure-the-help-experience-for-finance-and-operations-apps"></a>A Súgó tapasztalatának konfigurálása a Pénzügy és az Üzemeltetés alkalmazáshoz

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Ebben a témakörben áttekintést kaphat a pénzügyi és műveletalkalmazások súgórendszerének összetevőiről, Microsoft Dynamics például a 365 Pénzügy, Dynamics 365 Supply Chain Management az és Dynamics 365 Commerce az Dynamics 365 Human Resources. A cikk bemutatja az összetevők csatlakoztatását is, és bemutatja az egyéni súgó létrehozásának folyamatát.

## <a name="help-architecture"></a>Súgó-architektúra

A Pénzügyi és műveleti alkalmazások elméleti áttekintést [Microsoft Dynamics és a 365-ös dokumentációs webhelyen közzétett egyéb témaköröket is tartalmaznak](/dynamics365/). Ez a tartalom később a termék **Súgó** paneljéből érthető el. A következő ábrán a súgórendszer részei láthatók.

[![Súgóarchitektúra.](./media/help-architecture.png)](./media/help-architecture.png)

A terméken belül található súgórendszer cikkeket tud le kérni a Microsoft dokumentumokból és más kapcsolódó webhelyekről. Ezenkívül a Microsoft Dynamics Lifecycle Services (LCS) Üzletifolyamat-modellező (BPM) alkalmazásában tárolt feladat-útmutatókat is beolvas.

## <a name="adding-task-guides"></a>Feladat-útmutatók hozzáadása

> [!NOTE]
> A **Feladat-útmutatók** lap jelenleg nem érhető el az Human Resources vagy a Commerce alkalmazásban. <!--We are currently working to enable this functionality in a future release.--> A Human Resources Első lépések részének feladat-útmutatói azonban továbbra is rendelkezésre állnak az alapvető funkciók ismertetéséhez. Az eljárási Súgó a [Microsoft Dynamics 365 dokumentáció](/dynamics365/) webhelyről is elérhető, mind a Human Resources, mind a Commerce számára.

A **Rendszerparaméterek** oldalon a rendszeradminisztrátorok konfigurálhatják egy megvalósítás releváns feladat-útmutató könyvtáraihoz való hozzáférést.

> [!NOTE]
> - A Súgó konfigurálásához be kell lépnie egy ugyanattól a bérlőtől származó fiókba, amiben az alkalmazás is telepítve van.
> - Helyi virtuális merevlemezen (VHD) futó alkalmazáspéldánnyal nem lehet csatlakozni az LCS könyvtárhoz.

[![Rendszerparaméterek űrlap – súgó beállításai.](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

A megoldás feladat-útmutatóinak konfigurálásához kövesse az alábbi lépéseket a **Rendszerparaméterek** oldalon.

> [!IMPORTANT]
> Amikor első alkalommal nyitja meg a **Súgó** lapot, kapcsolódnia kell a Lifecycle Services szolgáltatáshoz. Ügyeljen arra, hogy az űrlap közepén levő hivatkozásra kattintson, várja meg a kapcsolatot, zárja be a párbeszédpanelt, majd kattintson az **OK** gombra a **Rendszerparaméterek** oldal eléréséhez.
>
> [![Kapcsolódás az LCS szolgáltatáshoz](./media/connect-to-lcs-crop-1024x365.png "Csatlakozás az LCS-hez.")](./media/connect-to-lcs-crop.png)

1. A csatlakozáshoz válassza ki a Lifecycle Services-projektet.
2. Válassza ki a BPM könyvtárakat (a kiválasztott projekten belül) amelyekből szeretné előhívni a rögzítéseket.
3. Adja meg a BPM könyvtárak megjelenítési sorrendjét. A megjelenítési sorrend meghatározza a sorrendet, amelyben a feladatrögzítések megjelennek a **Súgó** ablakban.

A lépések befejezése után megnyithatja a **Súgó** ablakot, és kiválaszthatja a Feladat **útmutatója lapot**. Mostantól a pénzügyi és műveleti alkalmazásokban éppen használt lapra vonatkozó feladati segédalkalmazások fognak jelenni. Amennyiben nem találhatók feladat-útmutatók, kulcsszavak beírásával módosíthatja a keresést.

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

A pénzügy- és a műveletalkalmazásokat ritkán használják a mezőn túli űrlapon. Helyette a megoldást testreszabják, és kiterjesztik, hogy megfeleljen a szervezet igényeihez. A Súgó élményét testreszabhatja és ki is bővítheti. Lehetőség van például egyéni súgó hozzáadására a terméken belüli **Súgó** panelen.

A Microsoft egy eszközkészletet biztosít egyéni súgók telepítéséhez és csatlakoztatásához a **Súgó** panelen. A **Súgó** panelhez kapcsolt egyéni súgótartalom beállításával kapcsolatos tudnivalókat lásd: [Egyéni Súgó – áttekintés](../../dev-itpro/help/custom-help-overview.md).

Ha együtt szeretne működni a Microsofttal a Súgó testreszabásához szükséges eszközökkel és folyamatokkal kapcsolatban, töltse ki a következő címen található űrlapot: [https://aka.ms/customhelpfeedback](https://aka.ms/customhelpfeedback).

## <a name="see-also"></a>Lásd még

[Súgórendszer](help-overview.md)  
[Egyéni Súgó – áttekintés](../../dev-itpro/help/custom-help-overview.md)  
[Feladatrögzítő erőforrásai](../../dev-itpro/user-interface/task-recorder.md)  
[Dokumentáció vagy képzés létrehozása Feladatrögzítő segítségével](../../dev-itpro/user-interface/task-recorder-training-docs.md)  
[Egyéni súgó GitHub-tárház](https://github.com/microsoft/dynamics356f-o-custom-help)  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
