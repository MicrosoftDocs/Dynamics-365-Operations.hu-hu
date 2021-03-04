---
title: Vevői feladási profilok
description: A vevői feladási profilok a vevői tranzakciók főkönyvbe történő feladását szabályozzák.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dff786d6e872e48f9605f9a472b7bffd409c5b3f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443840"
---
# <a name="customer-posting-profiles"></a>Vevői feladási profilok

[!include [banner](../includes/banner.md)]

A vevői feladási profilok a vevői tranzakciók főkönyvbe történő feladását szabályozzák.

<a name="customer-posting-profiles"></a>Vevői feladási profilok
-------------------------

Vevői feladási profilok lehetővé teszik az Ön számára, hogy a főkönyvi számlákat és dokumentumbeállításokat az összes vevőhöz, vevő csoporthoz vagy egyetlen vevőhöz rendelhesse. Ezeket a beállításokat akkor használják értékesítési rendelés, szabadszöveges számlák, készpénz kifizetések, fizetési felszólítások és kamatlevelek létrehozása során. Néhány tranzakcióhoz feladói profilt választhat ki, ami különböző és elsőbbséget élvez azokkal a feladói profilokkal szemben, amelyek a tranzakcióhoz be vannak állítva ezen az oldalon. 

Az alapértelmezett feladási profil a Főkönyv és Áfa gyorslapon a Kinnlevőségek paramétereinek lapján van megadva. Az alapértelmezett feladási profil automatikusan szerepel majd az új dokumentumok fejlécén, amelyen meg lehet változtatni egy másik feladási profilra, ha szükséges.

A tranzakció feladási definíciók lapon a a tranzakció feladási típussal társíthatja a feladásdefiníciókat. A feladásidefiníciók irányítják a a vevő tranzakciók feladását a főkönyvbe a feladói profilok helyett.

## <a name="creating-a-posting-profile"></a>Hozzon létre feladási profilt
Határozza meg a tranzakciók feladásában használt főkönyvet, ami a kijelölt feladási profilt használja. Válassza ki a kijelölt feladási profil számlakódját, és amennyiben lehetséges, számla- vagy csoportszámát. A feladási folyamat során a program kiválasztja a tranzakció legmegfelelőbb feladási profilját oly módon, hogy megkeresi a legspecifikusabb számlakód-, számlaszám-, illetve csoportszám-kombinációt az alábbi prioritás szerint:

| **Számla kód** mezőérték | **Számla/Csoport száma** mezőérték            | Keresési prioritás |
|------------------------------|-------------------------------------------------|-----------------|
| **Tábla**                    | Konkrét vevőkód                       | 1               |
| **Csoport**                    | Az a vevőcsoport, amelyet a vevőhöz rendeltek. | 2               |
| **Minden**                      | Üres                                           | 3               |

Ha azt szeretné, hogy a vevői tranzakciók feladási profiljai megegyezzenek, akkor csak egy feladási profilt állítson be az összes számla kód mezőben. Határozza meg a következő értékeket a feladási profil beállításához:

<table>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Feladási sablon</strong></td>
<td>Adjon meg egy kódot a feladási profilhoz. Például létrehozhat két feladói profilt, hogy létrehozzon egy fiókot a vevői egyenlegeknek, hogy lekérdezzen egy nemzeti pénznemet és egy külföldi valutát használó számlát a vevői egyenlegekhez. Hívhatja az egyik számlát "Nemzeti", a másikat "Külföldi" számlának.</td>
</tr>
<tr class="even">
<td><strong>Leírás</strong></td>
<td>Adja meg a feladói profil leírását. Ez csak a feladási profi pontosabb azonosítására szolgál, amikor ezen a lapon megtekinti.</td>
</tr>
<tr class="odd">
<td><strong>Számlakód</strong></td>
<td>Adja meg, hogy a feladási profil egyetlen vevőre, vagy egy vevőcsoportra vagy az összes vevőre vonatkozik:
<ul>
<li><strong>Asztal</strong>– A feladási profilok egyetlen vevőre vonatkoznak. Válassza ki a vevőszámlát a Számla/Csoport szám mezőben.</li>
<li><strong>Csoport</strong>– A feladási profilok vevő csoportra vonatkoznak. Válassza ki a vevő csoportot a Számla/Csoport szám mezőben.</li>
<li><strong>Összes</strong>– A feladási profilok az összes vevőre vonatkoznak. Hagyja üresen a Számla/Csoport száma mezőt.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Számla/csoport száma</strong></td>
<td>Ha az Asztal lehetőséget bejelölte a Számla kód mezőben, akkor adja meg annak a feladási profilhoz rendelt vevő számlaszámát. Ha a Csoport lehetőséget választotta, válassza ki a vevőcsoportot. Ha az Összes lehetőséget választotta, hagyja ezt a mezőt üresen.</td>
</tr>
<tr class="odd">
<td><strong>Összegzett számla</strong></td>
<td>Adja meg a főkönyvi számlát, amelyet a feladási profilban szereplő vevő(k) összesítési számlájaként kíván használni.</td>
</tr>
<tr class="even">
<td><strong>Számla kiegyenlítése</strong></td>
<td>Válassza ki a pénzforgalmi előrejelzéshez használt likviditási főkönyvi számlát. Ez a mező csak akkor jelenik meg, ha a készpénzforgalmi előrejelzések engedélyezettek.</td>
</tr>
<tr class="odd">
<td><strong>Áfaelőlegek</strong></td>
<td>Válassza ki az előre törlesztett kifizetések forgalmi adójának számlaszámát.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Bankjegy" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Megjegyzés</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Használja a Számla Kinnlevőségek paraméterei lapot a feladási profil meghatározásához, amikor a kifizetés előlegként van megjelölve.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Kötelezettségek az engedményszámlához</strong></td>
<td>Válassza ki a Főkönyvi számlát az engedmény kötelezettségeihez.</td>
</tr>
<tr class="odd">
<td><strong>Fizetésifelszólítás-sorozat</strong></td>
<td>Válassza ki a fizetési felszólítások sorozatának azonosítóját ahhoz a vevőhöz, akit a feladási profilhoz rendelt.</td>
</tr>
<tr class="even">
<td><strong>Kamatkód</strong></td>
<td>Válassza ki a feladási profiloz rendelt vevő kamatszámításához használni kívánt számla kódot.</td>
</tr>
</tbody>
</table>

### 

### <a name="table-restrictions"></a>**Táblakorlátozások**

Azokhoz a tranzakciókhoz, amelyeket a feladási profil kiválasztott, meghatározzák, hogy a tranzakció automatikusan ki van-e egyenlítve, a kamat ki van-e számítva, és a fizetési felszólítások ki vannak-e állítva. Kiválaszthatja a kijelölt feladási profillal rendelkező tranzakciók zárásakor használatos számlát.

Határozza meg a következő értékeket a feladási profil beállításához:

| Mező                 | Leírás                                                                                                                                                                                                                                        |
|-----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Elszámolás**        | Válassza ki a váltót a feladási profillal rendelkező tranzakciók automatikus elszámolásának engedélyezéséhez. Ha ez a váltó nincs bejelölve, manuálisan kell rendeznie a tranzakciókat a Nyitott tranzakciók kiegyenlítése oldalon vagy a Vevő kifizetések megadása oldalon. |
| **Érdeklődési terület**          | Válassza ki ezt a váltót, ha a kamatot ki kell számítani ezen profilt használó vevő számljának fennmaradó egyenlegei esetében. Ha a váltó nincs bejelölve, akkor az ilyen vevők esetében nem számít kamatot a program.                                           |
| **Fizetési felszólítás** | Válassza ki ezt a váltót, ha a fizetési felszólításokat ezen profilt használó vevő számljához kell létrehozni. Ha a váltó nincs bejelölve, a program nem számít fizetési felszóltásokat ezen vevők esetében.                                                 |
| **Zárás**             | Válasszon ki egy másik feladási profilt, amelyre váltani szeretne a jelen feladási profilt használó tranzakciók bezárásakor. Egy tranzakció akkor minősül bezártnak, ha a teljes kiegyenlítése megtörtént.                                                                           |



További információkért lásd: [Vevői kifizetések áttekintése](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]