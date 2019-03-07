---
title: Szervezetek és szervezeti hierarchiák
description: Egy szervezet olyan emberek csoportja, akik valamely üzleti folyamat végrehajtása vagy egy cél elérése érdekében együtt dologoznak Szervezeti hierarchiák a vállalkozását alkotó szervezetek közötti kapcsolatotat jelölik.
author: sericks007
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMOperatingUnit,
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 17291
ms.assetid: 76b7ca45-93d4-45cc-b191-66ee63afa1fd
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72834769e393382ac511ad3af21544efddb049d3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "322237"
---
# <a name="organizations-and-organizational-hierarchies"></a>Szervezetek és szervezeti hierarchiák

[!include [banner](../includes/banner.md)]

Egy szervezet olyan emberek csoportja, akik valamely üzleti folyamat végrehajtása vagy egy cél elérése érdekében együtt dologoznak Szervezeti hierarchiák a vállalkozását alkotó szervezetek közötti kapcsolatotat jelölik.

## <a name="organizations"></a>Szervezetek

A Microsoft Dynamics 365 for Finance and Operations alatt a következő típusú belső szervezeteket adhatja meg: jogi személyek operatív egységek és csoportok.

Az összes belső szervezet a **Fél** entitás egy formája. Ezért ezek a szervezetek a címjegyzéket használják címek és kapcsolattartási adatok tárolására. Egy félhez, amely lehet személy vagy szervezet, egy vagy több címjegyzékek is tartozhat.

### <a name="legal-entities"></a>Jogi személyek

A jogi személy olyan szervezet, amely bejegyzett vagy törvényben szabályozott jogi struktúrával rendelkezik. A jogi személyek törvényes szerződéseket köthetnek, teljesítményükről pedig tájékoztató beszámolókat kell készíteniük.

A vállalat is jogi személy. Ebben a kiadásban, Microsoft Dynamics 365 for Finance and Operations a vállalatok az egyetlen típusú jogi személy, amelyet létrehozhat, és minden jogi személyhez tartozik egy vállalati azonosító. Erre a társításra azért van szükség, mert a program egyes funkcionális területeinek modelljei vállalat azonosítót vagy DataAreaIdot használnak. Ezeken a funkcionális területeken a vállalatokat határként használják az adatbiztonsághoz. A felhasználók csak azoknak a vállalatoknak az adatait érhetik el, amelyekhez éppen be vannak jelentkezve.

### <a name="operating-units"></a>Üzemi egységek

Egy üzemi egység olyan szervezet, amelynek segítségével meg lehet osztani a gazdasági források és működési folyamatok ellenőrzését egy üzletben. Egy üzemi egységben a személyek feladata a szűkös erőforrások maximális kihasználása, a folyamatok javítása és a teljesítményük alapján történő elszámoltatás.

A Microsoft Dynamics 365 for Finance and Operations rendszerben, a működési egységek típusába a költséghelyek, az üzleti egységek, az érték-előállítási folyamatok osztályai és a kereskedelmi csatornák tartoznak. A következő táblázat további információval szolgál az egyes üzemi egységek típusairól.

| Üzemi egység típusa | Leírás | Cél |
|---------------------|-------------|---------|
| Költséghely         | Olyan üzemi egység, amelyben a vezetők elszámoltathatók az előirányzott és a tényleges kiadásokért. | Jogi személyek üzleti folyamataira kiterjedő vezetői és üzemi ellenőrzésre használják. |
| Üzleti egység       | Félig autonóm, a stratégiai üzleti célkitűzések teljesítése érdekében létrehozott üzemi egység. | Olyabn ágazatok vagy terméksorozatokon alapuló pénzügyi jelentéseihez használják, amelyeket a szervezet jogi személyiségétől függetlenül nyújt. |
| Érték-előállítási folyamat        | Egy vagy több termelési folyamatot szabályzó üzemi egység. | Gyakran használják a lean manufacturing tevékenységek és folyamatok ellenőrzésére, amelyek során a fogyasztóknak termékek adnak át vagy szolgáltatást nyújtanak. |
| Részleg          | A szervezet egy kategóriáját vagy funkcionális részét képező üzleti egység egy adott feladatot, mint például az értékesítés vagy a könyvelés, látja el. | Működési területek jelentésére használt. A részlegnek lehet eredménykimutatási felelőssége, és állhat több költségcentrumból. |
| Kiskereskedelmi csatorna      | Az üzemi egység lehet fizikailag létező bolt, online üzlet vagy online piactér. | Egy vagy több jogi személy egy vagy több üzletének vezetői és üzemi ellenőrzésére használják. |

### <a name="teams"></a>Csapatok

A csapat olyan szervezet, amely tagjainak közös a felelőssége, érdeklődése és célja. Szervezeti hierarchiákban csapatok nem használható.

## <a name="organizational-hierarchies"></a>Szervezeti hierarchiák

Hozzon létre szervezeti hierarchiát, hogy segítségével több nézőpontból vizsgálhassa válalatát és készíthessen jelentést róla. Például beállíthat egy hierarchiát a jogi személyek adózási, jogi, illetve kötelezően előírt jelentéseihez. Utána beállíthat egy másik hierarchiát olyan pénzügyi információkat tartalmazó jelentéshez, mely jogilag nem kötelező, de a belső jelentésekhez használható. Például létrehozhat egy beszerzési hierarchiát a beszerzési irányelvek, szabályok és üzleti folyamatok ellenőrzésére.

Minden hierachiához hozzá van rendelve egy cél a Microsoft Dynamics 365 for Finance and Operations modulban. A hierarchia célja meghatározza a hierarchiában szerepeltethető szervezetek típusait. A cél azt is meghatározza, mely alkalmazás környezetben használható egy hierarchia.

Egy hierarchiába tartozó szervezetek megoszthatják egymással a paramétereket, az irányelveket és a tranzakciókat. Egy szervezet örökölheti, de felül is írhatja a szülő szervezete paramétereit. Azonban megosztott mesteradatok, például a termékek és a címjegyzékek, a teljes szervezetre vonatkoznak, és nem írhatók felül az egyes szervezetek esetében. Szervezetek és hierarchiák létrehozása alapos tervezést igényel. További információért lásd: [Szervezeti hierarchia tervezése](plan-organizational-hierarchy.md).
