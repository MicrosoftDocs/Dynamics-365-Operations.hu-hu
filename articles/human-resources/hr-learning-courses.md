---
title: Tanfolyamok beállítása
description: Az emberi erőforrások-rendszergazdák és a vezetők a tanfolyamok szolgáltatások segítségével karbantartják a dolgozóknak nyújtott képzések információit.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 45466b8f52ddc261737da7474767c21f5bd331f8
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689887"
---
# <a name="set-up-training-courses"></a>Tanfolyamok beállítása


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Az emberi erőforrások-rendszergazdák és a vezetők a tanfolyamok szolgáltatások segítségével karbantartják a dolgozóknak nyújtott képzések információit.

##  <a name="set-up-prerequisites"></a> A telepítés előfeltételei

A következő adatokat kötelező megadni, és be kell állítani a tanfolyamok létrehozása előtt.
-   **Tanfolyamtípusok**

A következő adatokat nem kötelezően megadandó információt, amelyet meg lehet adni, a tanfolyamok. Ha tudja, hogy ki fogja bevinni tanfolyamok ezt az információt, akkor ezeket az adatokat kell beállítani, tanfolyam rekordok létrehozása előtt.
-   **Oktatótermi csoportok**
-   **Tanfolyami csoportok**
-   **Tanfolyami helyszínek**
-   **Oktatótermek**
-   **Oktatók**

## <a name="course-types"></a>Tanfolyamtípusok
Tanfolyamtípusok a tanfolyamok elosztását a szerkezetben, és a tanfolyam tartalma csoportosítására használhatók. Tanfolyam típusokat hozhat létre a **Kurzus típusok** oldalon. Tanfolyam rekord létrehozásakor ki kell választania egy tanfolyamtípus.

## <a name="course-setup-type"></a>Tanfolyamtípus - szakértelem
Az alábbi táblázat felsorolja azokat a tanfolyamok háromféle beállítása. Beállítási típusok határozzák meg, hogy a Tanfolyam felépítése.

<table>
<thead>
<tr class="header">
<th>Ellátási típus beállítása</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Normál</strong></td>
<td>Jelölje be ezt a típust, amelyet nem kell minden naphoz napirendet tanfolyamok. Új terv létrehozása esetén az alapértelmezett állapot Létrehozva.</td>
</tr>
<tr class="even">
<td><strong>Napirend</strong></td>
<td>Válassza ezt atípust egy kurzus minden egyes napjának részleteinek megtervezéséhez, amely több napon keresztül folyik le.</td>
</tr>
<tr class="odd">
<td><strong>Munkamenet + Napirend</strong></td>
<td>A tanfolyamok összetettebb típusának kiválasztása A tanfolyam napirendjét osztása például szekciókat és munkameneteket.
<ul>
<li><strong>Követés</strong>– A szekciók a tanfolyamhoz meghatározott tárgyterületek.</li>
<li><strong>Munakmenetek</strong> – A munkamenetek felosztják a szekciókat és segítenek a foglalkozhatnak az egyes szekciókhoz tartozó műveletek és technikák azonosításában.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>Tanfolyami tevékenységek
Például a következő műveleteket végezheti:
- Résztvevők regisztrálása
- A regisztráció határidejének beállítása
- A résztvevők minimális és maximális számának beállítása
- A tanfolyam helyszínének és tantermének kiválasztása
- Ajánlott szállodák a tanfolyam résztvevőinek
- A tanfolyamleírás létrehozása, amelyet közzé lehet tenni az **Alkalmazotti önkiszolgáló** rendszerben

  >**Megjegyzés** Csak akkor törölhet egy tanfolyamot, ha nincs hozzá regisztráció. 

## <a name="course-statuses"></a>Tanfolyam állapota
Az alábbi táblázat felsorolja a tanfolyam lehetséges állapotok és a műveleteket hajthatja végre, ha a tanfolyamhoz meghatározott állapota.

<table>
<thead>
<tr class="header">
<th>Állapot</th>
<th>Műveletek</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Létrehozva</strong></td>
<td><ul>
<li>Tanfolyami adatok megadása és szerkesztése.</li>
<li>Módosítsa a tanfolyam állapotát <strong>Nyitottra</strong> így a munkavállalók regisztrálhatnak a tanfolyamra.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Megnyitás</strong></td>
<td><ul>
<li>Résztvevő regisztrálása a tanfolyamra</li>
<li>A tanfolyam résztvevőinek eltávolítása.</li>
<li>Résztvevő regisztrálása a tanfolyamra</li>
<li>A tanfolyam<strong> Zárt</strong> vagy <strong>Törölt</strong>állapotra történő változtatása.</li>
<li>Kérdőívek tervezése <strong>Visszaigazolt</strong>állapotú résztvevők számára.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Lezárva</strong></td>
<td>A tanfolyam anyaga:</td>
</tr>
<tr class="even">
<td><strong>Érvénytelenítve</strong></td>
<td>A tanfolyam anyaga:</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>Tanfolyam résztvevői
A tanfolyam résztvevői olyan munkavállalók, akik részt vesznek egy tanfolyamon vagy eseményen. Csak nyitott tanfolyamok résztvevőinek is regisztrálható. A tanfolyamra regisztrálható résztvevők minimális és maximális számát az **Általános** gyorslapon a **Tanfolyamok** lapján határozhatja meg.

## <a name="workflow"></a>Munkafolyamat

Azok az alkalmazottak regisztrációja, akik a tanfolyamra az **Alkalmazotti önkiszolgáló rendszer** oldalán keresztül regisztrálnak, jóváhagyási munkafolyamaton mehet keresztül. Munkafolyamatot tanfolyamhoz a **Tanfolyamok** oldal **Általános** gyorslapján lehet hozzárendelni.







[!INCLUDE[footer-include](../includes/footer-banner.md)]
