---
title: Szállítás kezelés áttekintése
description: Ez a témakör áttekintést ad a szállításkezelés funkcióiról a Supply Chain Management szolgáltatásban.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4affc5846ee329a4571d6fb3e0c42873387241ad
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016378"
---
# <a name="transportation-management-overview"></a>Szállításkezelés áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést ad a szállításkezelés funkcióiról a Supply Chain Management szolgáltatásban.

A Szállításkezelés lehetővé teszi, hogy a vállalata szállítását használja, továbbá hogy azonosítsa a szállítót és az útvonal-tervezési megoldásokat a bejövő és a kimenő rendelésekhez. Például azonosíthatja a leggyorsabb vagy a legolcsóbb útvonalat a szállítmányhoz. A következő táblázat bemutatja a szállításkezelésben használatos fő eseteket.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Eset</th>
<th>A szállításkezelés segíthet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A külső logisztikai szolgáltatók használatában a szállítási tevékenységekhez.</td>
<td>A szállításkezelés használatában a bejövő és/vagy kimenő szállításhoz.</td>
</tr>
<tr class="even">
<td>A vállalat saját flottája elérhető kiszállításhoz/felvételhez, és a szállítási költségek a vevőkre vannak terhelve.</td>
<td>A kimenő folyamatokhoz használhatja a szállításkezelést, hogy meghatározza a szállítási díjakat és a vevőkre terhelje azokat. Azonban a szállítói számlák egyeztetési folyamata nem szükséges.</td>
</tr>
<tr class="odd">
<td>A vállalat saját flottája elérhető kiszállításhoz/felvételhez, de a szállítási díjak nincsenek a vevőkre terhelve, mert a termékárak tartalmazzák a szállítást.</td>
<td>Sok szállításkezelési funkcióra nincs szükség. Azonban használhatja a szállításkezelést, hogy meghatározza a szállítási díjakat, és ennek megfelelően állítsa be az eladási árat.</td>
</tr>
<tr class="even">
<td>A logisztikai szolgáltatást egy másik jogi személy biztosítja, ugyanazon vállalatból.</td>
<td><ul>
<li>Úgy használhatja a szállításkezelést, hogy a másik jogi személyt úgy kezeli, mint bármely másik szállítmányozót. Nem automatizálhatja a gazdasági tranzakciókat jogi személyek között. Ezért ezeket a tranzakciókat manuálisan kell kezelnie (például egy beszerzési rendelés létrehozásával).</li>
<li>Abban a jogi személyben, amely a logisztikai szolgáltatást biztosítja a szállításkezelés használható a szállítási díjak megállapításához.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a>Szállítás tervezése a Supply Chain Management alkalmazásban
A szállításkezelésben a szállítási tervezés alapulhat rendeléseken vagy az adott rendelések alapján létrehozott szállítmányokon. A szállítmány mindig létezik valamikor a folyamat során, de nem szükséges a szállítási tervezéshez. Az átmozgatási rendelések a kimeneti eset részei, és megtervezhetők az értékesítési rendelésekkel közösen. 

![Rajz betöltése](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a>Kimenő szállítás
Amikor cikkeket rendel szállítótól, és a cikkeket a raktárába kell szállítani, akkor érdemes saját magának elrendeznie a cikkek szállítását. Arra használhatja a Supply Chain Management rendszert, hogy megtervezze egy beérkező rakomány fogadását. A következő ábra bemutatja a szállítás bejövő terhelésének tervezéséhez és feldolgozásához használatos üzleti folyamatokat. 

![Üzleti folyamatábra: bejövő szállítási rakományok](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a>Kimenő szállítás
Megtervezheti és feldolgozhat egy kimenő terhelést bizonyos cikkek szállításához a cég raktárából a vevőhöz. Arra használhatja a Supply Chain Management rendszert, hogy megtervezze egy kimenő rakomány szállítását. A következő ábra bemutatja a szállítás kimenő terhelésének tervezéséhez és feldolgozásához használatos üzleti folyamatokat. 

![Kimenő rakományok tervezése és feldolgozása](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a>Rakomány-összeállítás
A Supply Chain Management biztosít egy rakomány-összeállítási stratégiát, amely a Térfogaton alapuló rakomány-összeállítási stratégia nevet viseli. Ez a stratégia lehetővé teszi a rakomány-sablonban megadott maximális magasság- és súlyértékek használatát, vagy a beállítások felülírását új értékek megadásával. A használatához válassza ki a stratégiát a **Rakomány-összeállító munkaterület** oldal **Beállítások** gyorslapján található **Rakomány-összeállítási stratégia** mezőben. Ezenkívül hozzáadhatja a saját rakomány-összeállítási stratégiáját egy új osztály létrehozásával az alkalmazásobjektum-fán (AOT) belül.



