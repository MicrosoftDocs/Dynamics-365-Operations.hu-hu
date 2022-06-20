---
title: Vevői feladási profilok
description: Ez a témakör a vevői feladási profilokat írja le, amelyek a vevői tranzakciók főkönyvbe való feladását szabályják.
author: JodiChristiansen
ms.date: 12/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0563040590eefab57706b183281c47a82e46076
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891695"
---
# <a name="customer-posting-profiles"></a>Vevői feladási profilok

[!include [banner](../includes/banner.md)]

Ez a témakör a vevői feladási profilokat írja le, amelyek a vevői tranzakciók főkönyvbe való feladását szabályják.

## <a name="customer-posting-profiles"></a>Vevői feladási profilok

A vevői feladási profilok segítségével főkönyvi számlákat és dokumentumbeállításokat rendelhet minden vevőhöz, vevőcsoporthoz vagy egyetlen vevőhöz. Ezeket a beállításokat használja a program, amikor értékesítési rendelési számlákat, szabadszöveges számlákat, projektszámlákat, fizetési naplókat, fizetési leveleket és kamatleveleket hoz létre. 

Az alapértelmezett feladási profil a Kinnlevőségek **paraméterei** oldal Főkönyv és Áfa **lapján határozható** meg. Ez a mező automatikusan megjelenik az új dokumentumok fejlécében. Ha más feladási profil szükséges, akkor itt módosíthatja. 

A vevőktől előlegeket elfogadó szervezetek gyakran konfigurálnak egy második feladási profilt az előlegek számára, és az előlegek alapértelmezett feladási profiljaként csatolják a paraméterekhez. A további tudnivalókat lásd [a Vevői előlegek](customer-prepayments.md).

A **Tranzakció-feladásdefiníciók** oldalon a tranzakció feladási típusaihoz társíthatja a feladásdefiníciókat. A feladásdefiníciók a feladási profilok helyett a vevői tranzakciók főkönyvbe való feladását szabályják. További információkért lásd: [A feladási típusok](../general-ledger/posting-definitions.md).

## <a name="creating-a-posting-profile"></a>Hozzon létre feladási profilt
Határozza meg a tranzakciók feladásában használt főkönyvet, ami a kijelölt feladási profilt használja. Válassza ki a kijelölt feladási profil számlakódját, és amennyiben lehetséges, számla- vagy csoportszámát. A feladási folyamat során a program kiválasztja a tranzakció legmegfelelőbb feladási profilját oly módon, hogy megkeresi a legspecifikusabb számlakód-, számlaszám-, illetve csoportszám-kombinációt az alábbi prioritás szerint:

| Számla kód mezőérték | Számla/Csoport száma mezőérték                | Keresési prioritás |
|--------------------------|-------------------------------------------------|-----------------|
| Táblázat                    | Konkrét vevőkód                       | 1               |
| Csoport                    | Az a vevőcsoport, amelyet a vevőhöz rendeltek. | 2               |
| Minden                      | Üres                                           | 3               |

Ha azt szeretné, hogy minden vevői tranzakció ugyanazt a feladási profilt tartalmazza, csak egy feladási profilt állítson be, **·** **és mindegyiket a Számlakód mezőben adja** meg. Adja meg a következő értékeket a feladási profil beállításához.

<table>
<thead>
<tr>
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr>
<td>Feladási profil</td>
<td>Adjon meg egy kódot a feladási profilhoz. Például létrehozhat két feladói profilt, hogy létrehozzon egy fiókot a vevői egyenlegeknek, hogy lekérdezzen egy nemzeti pénznemet és egy külföldi valutát használó számlát a vevői egyenlegekhez. Hívhatja az egyik számlát "Nemzeti", a másikat "Külföldi" számlának.</td>
</tr>
<tr>
<td>Leírás</td>
<td>Adja meg a feladói profil leírását. Ez csak a feladási profi pontosabb azonosítására szolgál, amikor ezen a lapon megtekinti.</td>
</tr>
<tr>
<td>Számlakód</td>
<td>Adja meg, hogy a feladási profil egyetlen vevőre, vagy egy vevőcsoportra vagy az összes vevőre vonatkozik:
<ul>
<li><b>Asztal</b>– A feladási profilok egyetlen vevőre vonatkoznak. Válassza ki a vevőt a <b>Számla/csoport száma mezőben</b>.</li>
<li><b>Csoport</b>– A feladási profilok vevő csoportra vonatkoznak. Válassza ki a vevőcsoportot <b>a Számla/csoport száma mezőben</b>.</li>
<li><b>Összes</b>– A feladási profilok az összes vevőre vonatkoznak. Hagyja üresen a <b>Számla/csoport száma</b> mezőt.</li>
</ul>
</td>
</tr>
<tr>
<td>Számla/csoport száma</td>
<td>Ha <b>a</b> Számlakód mezőben <b></b> a Tábla beállítás van megjelölve, válassza ki annak a vevőnek a számlaszámát, aki a feladási profilhoz van társítva. Ha a <b>Csoport</b> lehetőséget választotta, válassza ki a vevőcsoportot. Ha az <b>Összes</b> lehetőséget választja, hagyja ezt a mezőt üresen.</td>
</tr>
<tr>
<td>Összegzett számla</td>
<td>Válassza ki azt a fő számlát, amely a kinnlevőségek kereskedelmi számlája lesz a feladási profilhoz társított vevők esetében. Ez a számla a vevői egyenleg feladási <b></b> típusának számlája.</td>
</tr>
<tr>
<td>Likviditási számla a kifizetésekhez</td>
<td>Válassza ki a pénzforgalmi előrejelzéshez használt likviditási főkönyvi számlát. Ez a mező csak akkor jelenik meg, ha engedélyezve vannak a pénzforgalmi előrejelzések.</td>
</tr>
<tr>
<td>Áfaelőlegek</td>
<td><p>Válassza ki az előre törlesztett kifizetések forgalmi adójának számlaszámát.</p>
<p><strong>Megjegyzés:</strong> A Kinnlevőségek<b></b> paraméterei lapon lehet megadni az előlegként megjelölt kifizetésekhez használt feladási profilt.</p>
</td>
</tr>
<tr>
<td>Kötelezettségek az engedményszámlához</td>
<td>Válassza ki a Főkönyvi számlát az engedmény kötelezettségeihez.</td>
</tr>
<tr>
<td>Fizetésifelszólítás-sorozat</td>
<td>Válassza ki a fizetési felszólítások sorozatának azonosítóját ahhoz a vevőhöz, akit a feladási profilhoz rendelt.</td>
</tr>
<tr>
<td>Kamatkód</td>
<td>Válassza ki a feladási profiloz rendelt vevő kamatszámításához használni kívánt számla kódot.</td>
</tr>
</tbody>
</table>

## <a name="posting-examples"></a>Feladási példák

Az alábbi táblázat példákat mutat be az alapértelmezett feladási típusokra a minta fő számlákkal és leírásokkal. A **Tartozik/Követel** oszlop jelzi, hogy a tranzakciót általában tartozik vagy követel tételekként, vagy bizonyos esetekben fel lehet-e adni. Az **Elszámolószámla** oszlopban a feladás típusa elszámolószámla. Ez azt jelenti, hogy egy későbbi tranzakció feladása során a program automatikusan sztornírozi az erre a számlára feladott összeget. 

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|--------------|------------------|-------------|
| Vevői egyenleg | 130100 | Kinnlevőségek – kereskedelem | Eszközök | Mindkettő | Nem | Adja meg a számlát az Összegző számla **mezőben**.|
| Nincs | 110110 | Bankszámla | Eszközök | Mindkettő | Nem | Adja meg a kifizetésekhez a **Likviditási számla mezőben a fő számlát**. Ez a számla nem használatos feladásra. Csak a pénzforgalmi előrejelzéshez használatos. |
| Áfaelőlegek | 202900 | Áfa elszámolása | Kötelezettség | Mindkettő | Igen | Válassza ki az előre törlesztett kifizetések forgalmi adójának számlaszámát. |
| Kötelezettségek az engedményszámlához | 250600 | Halasztott bevétel és engedmények | Kötelezettség | Mindkettő | Igen | Válassza ki az engedmények kötelezettségeinek főkönyvi számláját.|     

### <a name="table-restrictions"></a>Táblakorlátozások

Azokhoz a tranzakciókhoz, amelyeket a feladási profil kiválasztott, meghatározzák, hogy a tranzakció automatikusan ki van-e egyenlítve, a kamat ki van-e számítva, és a fizetési felszólítások ki vannak-e állítva. Kiválaszthatja a kijelölt feladási profillal rendelkező tranzakciók zárásakor használatos számlát.

Határozza meg a következő értékeket a feladási profil beállításához:

| Mező                 | Leírás                                           |
|-----------------------|-------------------------------------------------------|
| Kiegyenlítés        | Válassza ki a váltót a feladási profillal rendelkező tranzakciók automatikus elszámolásának engedélyezéséhez. Ha a váltás nincs beszámítható, **akkor** manuálisan kell rendeznie a tranzakciókat a Nyitott tranzakciók kifizetése lapon vagy **a Vevői kifizetések beírása lapon**. |
| Érdeklődési terület          | Válassza ki ezt a váltót, ha a kamatot ki kell számítani ezen profilt használó vevő számljának fennmaradó egyenlegei esetében. Ha a váltó nincs bejelölve, akkor az ilyen vevők esetében nem számít kamatot a program.                                           |
| Fizetési felszólítás | Válassza ki ezt a váltót, ha a fizetési felszólításokat ezen profilt használó vevő számljához kell létrehozni. Ha a váltó nincs bejelölve, a program nem számít fizetési felszóltásokat ezen vevők esetében.                                                 |
| Bezár             | Válasszon ki egy másik feladási profilt, amelyre váltani szeretne a jelen feladási profilt használó tranzakciók bezárásakor. Egy tranzakció akkor minősül bezártnak, ha a teljes kiegyenlítése megtörtént.             |



További információkért lásd: [Vevői kifizetések áttekintése](../cash-bank-management/tasks/customer-payment-overview.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
