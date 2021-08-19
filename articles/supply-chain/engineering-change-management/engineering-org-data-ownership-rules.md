---
title: Mérnöki vállalatok és adattulajdonlási szabályok
description: Ez a témakör bemutatja, hogyan használhat egy vagy több mérnöki vállalatot annak biztosítására, hogy a termékek alapadatai központilag jöjjenek létre és legyenek karbantartva. Egy mérnöki vállalat képviseli a mérnöki termékeket birtokló vállalatot, és ez mérnöki szempontból releváns adatait.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 8bfb0a05fb608f1ee7c6377adaba0c15ee360579aefb74d8218ea4b3dfed9003
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716542"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>Mérnöki vállalatok és adattulajdonlási szabályok

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>Mérnöki vállalatok és operatív vállalatok

Annak biztosítására, hogy a termékek alapadatai központilag jöjjenek létre és legyenek karbantartva, egy vagy több *mérnöki vállalatot* alkalmazhat. Egy mérnöki vállalat birtokolja a mérnöki termékeket és ennek mérnöki szempontból releváns adatait. Mindig egy meglévő *jogi személyhez* kapcsolódik (alapul), amely egyben vállalat is. Ezzel a kapcsolattal a rendszer központi belépési pontot hoz létre a mérnöki vállalat mérnöki termékeinek műszaki szempontból releváns összes adatához. Ebben a központi belépési pontban mérnöki termékek jönnek létre, és a műszaki szempontból releváns adatokat karbantartják. Ebből a mérnöki termékeket és a műszaki szempontból releváns adatokat olyan *operatív vállalatok* számára adják át, amelyek más jogi személyek. (A kiadás kezelésével kapcsolatos további információkért lásd: [Termékstruktúrák kiadása](release-product-structure.md).) Ezek az operatív vállalatok a mérnöki adatokat úgy használják, ahogy a mérnöki vállalat megtervezte őket. A logisztikai adatokat az egyes mérnöki vállalatok és operatív vállalatok helyileg karbantartják.

Mérnöki vállalat létrehozásához nyissa meg a **Mérnöki változáskezelés \> Beállítás \> Mérnöki szervezetek** pontot. Válassza az **Új** lehetőséget, adja meg a mérnöki vállalat nevét, és válassza ki azt a meglévő vállalatot (jogi személyt), amelyen alapul.

Ha külső termékéletciklus-kezelő (PLM) rendszerekkel integrál, létre kell hoznia egy olyan részleget (vállalattípust), amely külső vállalattá válik.

## <a name="engineering-product-categories-and-engineering-companies"></a>Mérnöki termékkategóriák és mérnöki vállalatok

*A mérnöki termékkategóriák* segítenek biztosítani, hogy a mérnöki termékek a vállalat üzleti szabályainak megfelelően jönnek létre, és szükség szerint viselkedjenek. A mérnöki termékkategóriákkal kapcsolatos további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).

Minden egyes mérnöki termékkategória egy adott mérnöki vállalathoz tartozik, és csak az adott vállalathoz tartozó termékeket hozhat létre. Hasonlóképpen, a műszaki termék fenntartásának joga is ahhoz a vállalathoz tartozik, amely az adott termék mérnöki termékkategóriájához van társítva.

## <a name="data-that-is-owned-by-the-engineering-company"></a>A mérnöki vállalat tulajdonában lévő adatok

Mivel a mérnöki vállalat tulajdonában vannak a mérnöki szempontból releváns adatok, a következő folyamatokat szabályozza:

- **Mérnöki termékek létrehozása:** Minden mérnöki vállalat csak olyan új mérnöki termékeket hozhat létre, amelyek az általa birtokolt mérnöki termékkategórián alapulnak. Egyes esetekben az operatív vállalatok saját helyi adatokat tartanak fenn, amelyek ezekhez a termékekhez kapcsolódnak.
- **Mérnöki verziók létrehozása:** Amikor egy vállalat új mérnöki terméket hoz létre, a rendszer automatikusan létrehozza a kezdeti mérnöki verziót. Csak a tulajdoni joggal rendelkező mérnöki cég képes lesz létrehozni az új verziókat az adott termékhez.
- **Mérnöki verziók létrehozása és karbantartása:** Amikor egy vállalat új mérnöki terméket hoz létre, a rendszer automatikusan hozzáad mérnöki attribútumokat. Csak a tulajdonjoggal rendelkező mérnöki vállalat képes létrehozni és karbantartani az attribútumok értékeit. A mérnöki attribútumokkal kapcsolatos további információ: [Mérnöki attribútumok és mérnöki attribútumok keresése](engineering-attributes-and-search.md).
- **A mérnöki verziókhoz kapcsolódó anyagjegyzékek (AJ-k) létrehozása és karbantartása:** A tulajdonjoggal rendelkező mérnöki vállalat közvetlenül csatlakoztathatja az anyagjegyzéket egy mérnöki termékverzióhoz. Amikor ezeket az anyagjegyzékeket más jogi személyek számára is kiadják, az anyagjegyzékek műszaki adatainak módosításai a következő módokon korlátozottak:

    - Az operatív vállalat nem tudja eltávolítani a kiadott anyagjegyzéksorokat.
    - Az anyagjegyzéksorok mérnöki mezői írásvédettek az operatív vállalatnál. Minden más mező logisztikai végrehajtási terület, és az operatív vállalat szerkesztheti.
    - Az operatív vállalat anyagjegyzéksorokat adhat ugyanahhoz az anyagjegyzékhez. Ily módon helyi kiegészítéseket adhat hozzá, például csomagolóanyagokat vagy kenőfolyadékokat.
    - Az operatív vállalat hozzáadhat egy teljesen új, helyi anyagjegyzéket. Erre a módosításra szükség lehet olyan esetekben, amikor például a kiadás során nem áll rendelkezésre anyagjegyzék. Az operatív vállalat birtokolja és karbantartja ezeket a helyi anyagjegyzékeket. A kiadáskezelésről további információt a [Termékstruktúrák kiadása](release-product-structure.md) című témakörben talál.
    - Minden helyi anyagjegyzék és anyagjegyzéksor megmarad, amikor a mérnöki vállalat frissíti az anyagjegyzékét.

- **A mérnöki verziókhoz kapcsolódó anyagjegyzékek (AJ-k) létrehozása és karbantartása:** A mérnöki vállalat közvetlenül csatlakoztathat egy útvonalat az egyes mérnöki termékverziókhoz. Amikor ezeket az útvonalakat más jogi személyek számára is kiadják, az útvonalak műszaki adatainak módosításai a következő módokon korlátozottak:

    - A többi jogi személy nem távolíthatja el a mérnöki adatokat az útvonalakon.
    - A többi jogi személy műveleteket adhat hozzá az útvonalhoz. Ily módon helyi útvonallépéseket adhatnak hozzá.
    - Az operatív vállalatok hozzáadhatnak teljesen új, helyi útvonalakat. Erre a módosításra szükség lehet olyan esetekben, amikor például a kiadás során nem adott meg útvonalakat. Az operatív vállalatok birtokolják és karbantartják ezeket a helyi útvonalakat. A kiadáskezelésről további információt a [Termékstruktúrák kiadása](release-product-structure.md) című témakörben talál.
    - A helyileg végrehajtott módosítások megmaradnak, amikor a mérnöki vállalat frissítéseit kiadják az útvonalakon.

- **Mérnöki dokumentumok létrehozása és karbantartása:** A mérnöki vállalat minden mérnöki verzióhoz mérnöki dokumentumokat csatolhat.

    - Amikor ezeket a dokumentumokat más jogi személyeknek adják ki, a dokumentumokat az operatív vállalat védi az eltávolítástól.
    - Más jogi személyek teljesen új, helyi dokumentumokat adhatnak hozzá. Az operatív vállalat birtokolja és karbantartja ezeket a helyi dokumentumokat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]