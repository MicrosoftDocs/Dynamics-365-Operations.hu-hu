---
title: "Jövőben esedékes csekkek"
description: "Ez a cikk a Microsoft Dynamics 365 for Finance and Operations Enterprise edition támogatását írja le a jövőben esedékes csekkeket illetően. A jövőben esedékes csekkek olyan csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítják ki. Emiatt a csekk nem váltható be a megadott dátumig."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 21741
ms.assetid: 4eb7c7da-1e6b-4d35-9f41-373b66103229
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6a535b5f1192b7c27383cb8ece53f76a9c76f047
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="postdated-checks"></a>Jövőben esedékes csekkek

[!include[banner](../includes/banner.md)]


Ez a cikk a Microsoft Dynamics 365 for Finance and Operations Enterprise edition támogatását írja le a jövőben esedékes csekkeket illetően. A jövőben esedékes csekkek olyan csekkek, amelyeket jövőbeli dátumon való fizetés céljából állítják ki. Emiatt a csekk nem váltható be a megadott dátumig.

A Microsoft Dynamics 365 for Finance and Operations támogatja a teljes menedzselési ciklust a jövőben esedékes csekkekhez, a Kinnlevőségekben és a Kötelezettségekben is, ahogy a következő táblázat mutatja.
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Eset</th>
<th>Részletek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Jövőben esedékes csekkek beállítása</td>
<td>Állítson be egy új fizetési módot, és adja meg a kifizetési módot a kiállított csekkekhez, a beérkezett csekkekhez és az adóelőleghez.</td>
</tr>
<tr class="even">
<td>Szállítónak kiállított, jövőben esedékes csekk regisztrálása és feladása</td>
<td>Jegyezze be a szállítónak feladni kívánt jövőben esedékes csekk adatait. A kifizetés feladásakor a szállítói felelősség elismerésre kerül, de a bankszámla jóváírása még nem történik meg. Ehelyett erre a célra elszámoló-számlát alkalmaznak. </td>
</tr>
<tr class="odd">
<td>Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása</td>
<td>Jegyezze fel a vevőtől érkezett, jövőben esedékes csekk adataid. A kifizetés feladásakor a vevő megkapja az értesítést arról, hogy a kifizetés megtörtént, azonban a bankszámla terhelése még nem történik meg. Ehelyett erre a célra elszámoló-számlát alkalmaznak.</td>
</tr>
<tr class="even">
<td>Szállítónak vagy vevőnek kiállított helyettesítő, jövőben esedékes csekk regisztrálása és feladása</td>
<td>
Ha a szállítónak vagy a vevőnek készült eredeti csekk elveszik vagy megsérül, helyettesítő, jövőben esedékes csekket bocsáthat ki. Amikor nyilvántartásba veszi a csekk részletes adatait, hivatkozzon az eredeti csekkre és jelezze, hogy az új csekk az eredetit helyettesíti. Fel is adhatja a helyettesítő csekket.</td>
</tr>
<tr class="odd">
<td>Vevő által kiállított, jövőben esedékes csekk átvitele szállítónak</td>
<td>Amikor egy jövőben esedékes csekket kap egy vevőtől, a csekket átadhatja egy szállítónak fizetésként.</td>
</tr>
<tr class="even">
<td>Vevő vagy szállítónak kiállított, jövőben esedékes csekk kiegyenlítése</td>
<td>Fizesse ki az áthidaló számlára (a vevőnek vagy a szállítónak kiállított) feladott csekket akkor, amikor az érvényessé válik. A csekk kifizetésekor a bank jóváírja vagy tartozást hagy a korábban használt elszámoló-számlával szemben.</td>
</tr>
<tr class="odd">
<td>Szállítónak kiállított, jövőben esedékes csekk érvénytelenítése</td>
<td>Érvénytelenítheti a könyvelt, jövőben esedékes csekket ezekben az esetekben: -A csekket visszaküldik a banknak.
- A csekket nem megfelelő számlához alkalmazták.
- Készpénzes fizetés történik a csekkel szemben.
</td>
</tr>
<tr class="even">
<td>Jövőben esedékes csekk kifizetésének leállítása</td>
<td>Leállíthatja egy szállítónak kiállított, jövőben esedékes csekk kifizetését különböző okokból, például elégtelen fedezet esetén, a szállítóval kötött szerződés feltételeinek megváltozásakor, a szállító által szállított hibás áruk, vagy a termékek szállítóhoz történő visszaküldése miatt. Csak olyan csekkek kifizetése állítható le, amelyek még nincsenek kiegyenlítve.</td>
</tr>
</tbody>
</table>



További információ a következő témakörökben olvasható:

[Jövőben esedékes csekkek beállítása](tasks/set-up-postdated-checks.md)

[Vevő részére kiállított, jövőben esedékes csekk regisztrálása és feladása](tasks/register-post-postdated-check-customer.md)

[Vevő által kiállított, jövőben esedékes csekk kiegyenlítése](tasks/settle-postdated-check-customer.md)

[Szállító részére kiállított, jövőben esedékes csekk regisztrálása és feladása](tasks/register-post-postdated-check-vendor.md) 

[Szállítónak kiállított, jövőben esedékes csekk kiegyenlítése](tasks/settle-postdated-check-vendor.md)




