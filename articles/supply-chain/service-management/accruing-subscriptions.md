---
title: Előfizetések könyvelése
description: A szolgáltatási előfizetésekkel manuálisan könyvelhető a bevétel a díjtranzakció kiszámlázását követő időszakokban.
author: sorenva
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ff184b24a264e37613b2302a3d92b74e870c5ac
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677338"
---
# <a name="accruing-subscriptions"></a>Előfizetések könyvelése 

[!include [banner](../includes/banner.md)]


A szolgáltatási előfizetésekkel manuálisan könyvelhető a bevétel a díjtranzakció kiszámlázását követő időszakokban.

Az előfizetési díjra vonatkozóan létrehozott számlázási időszakokra könyvelési időszakok jönnek létre, és a könyvelési időszakok az előfizetés időszakkódjára épülnek.

A bevételeket elhatárolhatja, illetve sztornírozhatja.

## <a name="reverse-accruals-of-credit-amounts"></a>Követel összegek könyvelésének sztornírozása

Ha meghitelezi a kiszámlázott előfizetési összeget, a könyvelt összegek sztornírozására két különböző módszert használhat:

  - Sztornírozhat minden egyes könyvelt bevételt külön-külön, mielőtt létrehozza a jóváírási javaslatot a tranzakcióhoz. Ez a manuális módszer. (manuális)

  - Vagy sztornírozhatja a könyvelt összegeket a jóváírási javaslat feladási dátumán vagy a könyvelés eredeti feladási dátumán.

További tudnivalókkal kapcsolatban lásd: [Subscription parameters (form)](/dynamicsax-2012//subscription-parameters-form).

## <a name="setup-requirements"></a>A beállítás előfeltételei

A bevételek elhatárolása előtt ellenőrizze, hogy teljesülnek-e a az adatokra vonatkozó követelmények:

## <a name="account-setup"></a>Számlabeállítás

A **Folyamatban lévő munka - előfizetés** és az **Elhatárolt bevétel - előfizetés** számlákat kell be kell állítani a **Projekt** modulban.

Amikor elhatárolt bevételeket ad fel, a **Folyamatban lévő munka - előfizetés** számlán az elhatárolt összeg tartozik tételként jelenik meg, az **Elhatárolt bevétel - előfizetés** számlán pedig követel tételként.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>Az előfizetési bevétel elhatárolására használt számlák beállítása

1.  Kattintson a **Projektvezetés és könyvelés** \> **Beállítás** \> **Feladás** \> **Főkönyvi feladás beállítása** lehetőségre.

2.  Kattintson a **Bevételi számlák** lapra, és válassza **Folyamatban lévő munka - előfizetés** vagy **Elhatárolt bevétel - előfizetés** lehetőségre a számlák beállításához.

## <a name="subscription-group-setup"></a>Előfizetési csoport beállítása

Ahhoz, hogy az előfizetések bevétele elhatárolható legyen, a **Bevétel elhatárolása** jelölőnégyzetet be kell jelölni. Ez annak a csoportnak az **Előfizetési csoportok** lapján található, amely az előfizetéshez kapcsolódik. Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok**.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>Bevételelhatárolás engedélyezése az előfizetéscsoportokban

Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok**.

## <a name="periods"></a>Időszakok

Be kell állítania egy számlázási időszakkódot. Hacsak nem szeretné a számlázási időszakkal megegyező időintervallumokban elhatárolni a bevételt, be kell állítania egy könyvelési időszakot is.

A következő táblázat áttekintést ad arról, hogy mely könyvelési időszakokat állíthatja be az egyes számlázási időszakokhoz.

<table>
<colgroup>
<col />
<col />
</colgroup>
<thead>
<tr class="header">
<th><p>Számlázási időszak</p></th>
<th><p>Könyvelési időszak</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>év</strong></p></td>
<td><ul>
<li><p><strong>év</strong></p></li>
<li><p><strong>Negyedév</strong></p></li>
<li><p><strong>Hónap</strong></p></li>
<li><p><strong>Nap</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Negyedév</strong></p></td>
<td><ul>
<li><p><strong>Negyedév</strong></p></li>
<li><p><strong>Hónap</strong></p></li>
<li><p><strong>Nap</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Hónap</strong></p></td>
<td><ul>
<li><p><strong>Hónap</strong></p></li>
<li><p><strong>Nap</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Hét</strong></p></td>
<td><ul>
<li><p><strong>Nap</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Nap</strong></p></td>
<td><ul>
<li><p><strong>Nap</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

A számlázási időszak beállítása a teljes előfizetési csoport beállításának kötelező részét képezi. Eldöntheti, hogy az előfizetési csoporthoz egy könyvelési időszakot is beállít-e. Ha beállít az előfizetési csoporthoz egy könyvelési időszakot, a rendszer ezt az időszakot javasolja az **Időszakkód** mezőben. Ez a mező az **Előfizetési bevétel könyvelése** oldalon található, amikor könyveli az előfizetési bevételt. A könyvelési időszak viszont csak opcionális információ az előfizetési csoportnál.


> [!NOTE]
> <P>A következő elérési utat használja az <STRONG>Előfizetési bevétel könyvelése</STRONG> oldal megnyitásához. Kattintson a következőkre: <STRONG>Szolgáltatáskezelés</STRONG>&gt;<STRONG>Időszakos</STRONG>&gt;<STRONG>Szolgáltatási előfizetések</STRONG>&gt;<STRONG>Előfizetési bevétel könyvelése</STRONG>.</P>


## <a name="transactions"></a>Tranzakciók

Megadhatja az elhatárolt bevétel feladása során létrehozott főkönyvi tranzakciók számát. Az előfizetésekkel kapcsolatban határozza meg, hogy a főkönyvi tranzakciók teljes összegként vagy soronként jöjjenek létre.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>A megjelenítendő feladási részletek szintjének meghatározása elhatárolt tranzakciók esetére

1.  Kattintson a **Projektvezetés és könyvelés** \> **Beállítás** \> **Projektvezetési és könyvelési paraméterek** lehetőségre.

2.  A **Pénzügyi** lapon, a **Számla** mezőben válassza ki az **Összesítés** vagy **Sor** lehetőséget.


## <a name="see-also"></a>Lásd még

[Előfizetési bevétel könyvelése](accrue-subscription-revenue.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]