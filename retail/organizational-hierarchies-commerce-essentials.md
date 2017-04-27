---
title: "Szervezetek és szervezeti hierarchiák (Kereskedelmi alapok)"
description: "A Kereskedelmi alapokban háromféle belső szervezet adható meg, amelyek segítségével a kívánt szervezet üzleti folyamatot hajthat végre vagy célt érhet el."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21251
ms.assetid: 2bfc6bfe-784b-42e8-8bf0-116e9f0a558e
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 93711977ad8d861ca75ba80ee542ee112c8ddd2f
ms.lasthandoff: 03/31/2017


---

# <a name="organizations-and-organizational-hierarchies-commerce-essentials"></a>Szervezetek és szervezeti hierarchiák (Kereskedelmi alapok)

[!include[banner](includes/banner.md)]


A Kereskedelmi alapokban háromféle belső szervezet adható meg, amelyek segítségével a kívánt szervezet üzleti folyamatot hajthat végre vagy célt érhet el. 

A szervezet olyan emberek egy csoportja, akik egy üzleti folyamat végrehajtásához, vagy egy cél elérése érdekében működnek együtt. A szervezeti hierarchiák a vállalkozását alkotó üzleti egységek közötti kapcsolatotat jelölik.

## <a name="organizations"></a>Szervezetek
A Kereskedelmi alapok alatt három típusú szervezetet adhat meg: jogi személyeket, operatív egységeket és csoportokat. A Microsoft Dynamics AX rendszerben minden belső szervezet a Fél entitás valamely típusa. Ezért ezek a szervezetek a címjegyzéket használják címek és kapcsolattartási adatok tárolására. Egy félhez, amely lehet személy vagy szervezet, egy vagy több címjegyzékek is tartozhat.
### <a name="legal-entities"></a>Jogi személyek

A jogi személy olyan szervezet, amely bejegyzett vagy törvényben szabályozott jogi struktúrával rendelkezik. A jogi személyek törvényes szerződéseket köthetnek, teljesítményükről pedig tájékoztató beszámolókat kell készíteniük. Egy vállalat az egyetlen típusú jogi személy a Microsoft Dynamix AX rendszerben, és minden jogi személyhez tartozik egy vállalati azonosító. A társítás létezik, mert a Vállalatazonosító, vagy a DataAreaId már használatban van egyes adatmodellekben, ahol a vállalat jelenti az adatbiztonsági lehatárolást. A felhasználók csak annak a vállalatnak a részére férhetnek hozzá adatokhoz, amelyen éppen bejelentkeznek.

### <a name="operating-units"></a>Üzemi egységek

Egy üzemi egység olyan szervezet, amelynek segítségével meg lehet osztani a gazdasági források és működési folyamatok ellenőrzését egy üzletben. Egy üzemi egységben a személyek feladata a szűkös erőforrások maximális kihasználása, a folyamatok javítása és a teljesítményük alapján történő elszámoltatás. A Kereskedelmi alapok modulban a működési egységek típusába a költséghelyek, az üzleti egységek, az érték-előállítási folyamatok osztályai és a kereskedelmi csatornák tartoznak. A következő táblázat további információval szolgál az egyes üzemi egységek típusairól.
|                         |                                                                                         |                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Üzemi egység típusa** | **Leírás**                                                                         | **Cél**                                                                                                                                 |
| Üzleti egység           | Félig autonóm, a stratégiai üzleti célkitűzések teljesítése érdekében létrehozott üzemi egység. | Az üzleti egységeket ágazatok vagy terméksorozatokon alapuló pénzügyi jelentéseihez használják, amelyeket a szervezet jogi személyiségétől függetlenül nyújt. |
| Kiskereskedelmi csatorna          | Olyan üzemi egység, amely egy konkrét üzlethelyiségnek felel meg.                             | Ezzel egy vagy több üzletet kezelhet és vezérelhet több jogi személy között is.                                                               |

## <a name="organizational-hierarchies"></a>Szervezeti hierarchiák
A Kereskedelmi alapok modulban minden hierachiához hozzá van rendelve egy cél. A hierarchia célja meghatározza a hierarchiában szerepeltethető szervezetek típusait. A cél azt is meghatározza, mely alkalmazás környezetben használható egy hierarchia. Például a kiskereskedelmi hierarchia használható termékek beszerzéséhez és értékesítéséhez kiskereskedelmi áruházakban. Egy hierarchiába tartozó szervezetek megoszthatják egymással a paramétereket, az irányelveket és a tranzakciókat. Egy szervezet örökölheti, de felül is írhatja a szülő szervezete paramétereit. Azonban a megosztott alapadatok, például a termékek és a címjegyzékek, a teljes szervezetre vonatkoznak, és nem írhatók felül az egyes szervezetek esetében.
### <a name="best-practices-for-setting-up-an-organization-in-a-hierarchy"></a>Gyakorlati tanácsok a szervezeti hierarchia beállításához

Vegye figyelembe a következő legjobb gyakorlati tanácsokat a szervezeti hierarchia végrehajtásánál:
-   Hozzon létre részleget, hogy meghatározhassa a jogi személy és az üzleti egység közötti metszetet. Ezután felvetíthet adatot egy részlegből a jogi személynek kötelező jelentéshez és részlegből üzleti egységhez belső jelentéshez.
-   Egy jogi személyben ne hozzon létre több hierarchiát ugyanahhoz a hierarchiacélhoz.
-   Ne hozzon létre hierarchiát minden célhoz. Általában használhat egy hierarchiát több célra. Például működési egységek hierarchiáját hozzá lehet rendelni minden irányelvre vonatkozó célhoz.
-   Egyensúlyi hierarchiák létrehozása. Hierarchiában az alap csomóponttól azonos távolságra lévő csomópontok egy szintként vannak meghatározva. Kiegyensúlyozott hierarchiában üzemi egységek csak egyféle típusa fordulhat elő minden szinten, és az alap csomóponttól lévő távolság minden egyes szinten összhangban van. Ha közbenső szintek vannak a részleg és a jogi személy vagy üzleti egység között, a helyőrző szervezeteknek szükséges lehet a kiegyensúlyozott hierarchia létrehozása.
-   Ne hozzon létre külön hierarchiát az üzemi egységekhez, ha a szerkezet a jogi személyekhez egyben a működési struktúra is. A jogi személyek és üzemi egységek vegyes hierarchiája mindkét célra szolgálhat.
-   A fő átstruktúrálási tervek létrehozása előtt használja a hierarchia érvényességi dátumát a hatáselemzés és az érvényességi teszt végrehajtásához.
-   Mentse a hierarchiát vázlatként, ha még módosítaná, mielőtt közzéteszi.
-   Korlátozhatja az emberek számát, akiknek engedélye van szervezetek hozzáadásához vagy eltávolításához a hierarchiából a termékkörnyezetben. A kevesebb csökkenti annak lehetőségét, hogy költséges hibák fordulnak elő és helyesbítéseket kell elvégezni.

## <a name="retail-store-management"></a>Kiskereskedelmi üzlet kezelése
A következő táblázat leírja, hogy mely Kereskedelmi alapok típusú eseteketben használhatók szervezeti hierarchiák.
| Feladat                                                                           | Leírás                                                                                                                                                                                                                                                                                                | Hierarchia célja    |
|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Kiskereskedelmi szortimentek feladat                                                      | A kiskereskedelmi áruházban rendelkezésre álló termékek azonosítása.                                                                                                                                                                                                                                             | Kiskereskedelmi szortiment    |
| Kiskereskedelmi feltöltés                                                    | Csoport feltöltési szabályok alapján feltöltéséhez tárolja.                                                                                                                                                                                                                                          | Kiskereskedelmi feltöltés |
| Előzetes jelentés adatai                                                         | Főkönyvi csoport a jelentéskészítéshez                                                                                                                                                                                                                                                                                 | Kiskereskedelmi jelentés     |
| Készlet feladása kimutatások számításához és üzletcsoportokhoz a kimutatások feladása | Hozzon létre egy kötegelt feladat rendelt üzletcsoportokhoz. Készlet feladása, a kimutatások számításához vagy a kimutatások feladása kötegelt feladatként definiálásakor megadhatja mely hierarchia a feladat vonatkozik. Üzletek hozzáadni vagy eltávolítani a hierarchiából, amikor a kötegelt feladat módosítása nincs. | Kiskereskedelmi pénztári feladás   |






