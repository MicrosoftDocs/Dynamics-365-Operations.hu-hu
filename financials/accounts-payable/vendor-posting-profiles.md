---
title: "Szállítói feladási profilok"
description: "A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2dbb8874323631a9bddb226834adf87d014c1c2f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-posting-profiles"></a>Szállítói feladási profilok

[!include[banner](../includes/banner.md)]


A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák.

<a name="vendor-posting-profiles"></a>Szállítói feladási profilok
-----------------------

Szállítói feladási profilok lehetővé teszik az Ön számára, hogy a főkönyvi számlákat és dokumentumbeállításokat az összes szállítóhoz, vevő csoporthoz vagy egyetlen szállítóhoz rendelhesse. Ezek a beállítások a beszerzési rendelések, a szállítói számlák és a készpénzes fizetés létrehozásakor használalják. Néhány tranzakcióhoz feladói profilt választhat ki, ami különböző és elsőbbséget élvez azokkal a feladói profilokkal szemben, amelyek a tranzakcióhoz be vannak állítva ezen az oldalon. Az alapértelmezett feladási profil a Főkönyv és Áfa gyorslapon a Kötelezettségek paramétereinek lapján van megadva. Az alapértelmezett feladási profil automatikusan szerepel majd az új dokumentumok fejlécén, amelyen meg lehet változtatni egy másik feladási profilra, ha szükséges.

A tranzakció feladási definíciók lapon a a tranzakció feladási típussal társíthatja a feladásdefiníciókat. A feladásidefiníciók irányítják a a szállítói tranzakciók feladását a főkönyvbe a feladói profilok helyett.

## <a name="creating-a-posting-profile"></a>Hozzon létre feladási profilt
### <a name="setup"></a>**Beállítás**

Határozza meg a tranzakciók feladásában használt főkönyvet, ami a kijelölt feladási profilt használja. Válassza ki a kijelölt feladási profil számlakódját, és amennyiben lehetséges, számla- vagy csoportszámát. A feladási folyamat során a program kiválasztja a tranzakció legmegfelelőbb feladási profilját oly módon, hogy megkeresi a legspecifikusabb számlakód-, számlaszám-, illetve csoportszám-kombinációt az alábbi prioritás szerint:

| **Számla kód** mezőérték | **Számla/Csoport száma** mezőérték        | Keresési prioritás |
|------------------------------|---------------------------------------------|-----------------|
| **Tábla**                    | Konkrét szállítói számla                     | 1               |
| **Csoport**                    | Az a szállítócsoport, amelyhez a szállító van rendelve. | 2               |
| **Minden**                      | Üres                                       | 3               |

Ha azt szeretné, hogy a szállítói tranzakciók feladási profiljai megegyezzenek, akkor csak egy feladási profilt állítson be az összes számla kód mezőben. Határozza meg a következő értékeket a feladási profil beállításához:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Feladási sablon</strong></td>
<td>Adjon meg egy kódot a feladási profilhoz. Létrehozhat például két feladási profilt, hogy legyen egy nemzeti pénznemet és egy külföldi valutát használó számla a szállítói egyenlegekhez. Hívhatja az egyik számlát "Nemzeti", a másikat "Külföldi" számlának.</td>
</tr>
<tr class="even">
<td><strong>Leírás</strong></td>
<td>Adja meg a feladói profil leírását.</td>
</tr>
<tr class="odd">
<td><strong>Számlakód</strong></td>
<td>Adja meg, hogy a feladási profil egy adott szállítóra, egy szállítócsoportra vagy az összes szállítóra vonatkozzon-e:
<ul>
<li><strong>Asztal</strong>– A feladási profilok egyetlen szállítóra vonatkoznak. Válassza ki a szállító számlát a Számla/Csoport szám mezőben.</li>
<li><strong>Csoport</strong>– A feladási profilok szállító csoportra vonatkoznak. Válassza ki a szállító csoportot a Számla/Csoport szám mezőben.</li>
<li><strong>Összes</strong>– A feladási profilok az összes szállítóra vonatkoznak. Hagyja üresen a Számla/Csoport száma mezőt.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Számla/csoport száma</strong></td>
<td>Ha az Asztal lehetőséget bejelölte a Számla kód mezőben, akkor adja meg annak a feladási profilhoz rendelt szállító számlaszámát. Ha a Csoport lehetőséget választotta, válasszon egy szállítói csoportot. Ha az Összes lehetőséget választotta, hagyja ezt a mezőt üresen.</td>
</tr>
<tr class="odd">
<td><strong>Összegzett számla</strong></td>
<td>Válassza ki azt a főkönyvi sámlát, amit a szállító összegző számlajaként használ, amikhez a feladási profil kapcsolódik.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Megjegyzés</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A használt feladási definíciók váltóit választotta ki a főkönyvi paraméterek lapon, a tranzakció szállítói számlákra vonatkozó feladásdefiníciót használja az összegző számla helyett.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Számla kiegyenlítése</strong></td>
<td>Válassza ki a pénzforgalmi előrejelzéshez használt likviditási főkönyvi számlát. Ez a mező csak akkor érhető el, ha engedélyezve van a pénzforgalmi előrejelzés.</td>
</tr>
<tr class="odd">
<td><strong>Áfaelőlegek</strong></td>
<td>Válassza ki az előre törlesztett adó kifizetések számlaszámát.
<div class="alert">
<table>
<thead>
<tr class="header">
<th><img src="https://i-technet.sec.s-msft.com/areas/global/content/clear.gif" title="Note" alt="Note" id="alert_note" class="cl_IC101471" /><strong>Megjegyzés</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A feladási profil, amely akkor használatos, ha be van jelölve a kifizetés előlegként az előlegnapló-bizonylattal rendelkező Feladási profil mezőben a Főkönyvben és a Kötelezettségek paramétereinek áfa területén.</td>
</tr>
</tbody>
</table>
</div></td>
</tr>
<tr class="even">
<td><strong>Beérkezés</strong></td>
<td>Válassza ki a főkönyvi számlát, amelyre a nem jóváhagyott szállítói számlákkal kapcsolatos információkat feladja. Az adat a számlajegyzék-naplóban szerepel. Például, egy felhasználó alapvető adatokat ad meg szállítói számlákról, amikor megkapta a számlajegyzéket. A számlajegyzék feladásakor a tranzakciók az itt és az Ellenszámla mezőben megadott számlára kerülnek. A számlák jóváhagyását követően a kötelezettség átkerül a Beérkezés számláról a szállítói összegző számlára.</td>
</tr>
<tr class="odd">
<td><strong>Ellenszámla</strong></td>
<td>Válassza ki a számlajegyzék segítségével frissített, nem jóváhagyott szállítói számlák kiegyenlítéséhez használt főkönyvet. Az ellenszámla a beérkezés számlákra feladott tranzakciók ellenszámlájaként viselkedik. Ezért a számla tartalmazza a még nem jóváhagyott szállítói beszerzéseket.</td>
</tr>
</tbody>
</table>
 

### <a name="table-restrictions"></a>**Táblakorlátozások**

Azokhoz a tranzakciókhoz, amelyeket a feladási profil kiválasztott, meghatározzák, hogy a tranzakció automatikusan ki van-e egyenlítve, a kamat ki van-e számítva, és a fizetési felszólítások ki vannak-e állítva. Kiválaszthatja a kijelölt feladási profillal rendelkező tranzakciók zárásakor használatos számlát.

Határozza meg a következő értékeket a feladási profil beállításához:

| Mező          | Leírás                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Elszámolás** | Válassza ki ezt a lehetőséget a feladási profillal rendelkező tranzakciók automatikus elszámolásának engedélyezéséhez. Ha ez a lehetőség nincs bejelölve, manuálisan kell rendeznie a tranzakciókat a Nyitott tranzakciók kiegyenlítése oldalon vagy a Vevő kifizetések megadása oldalon. |
| **Mégse**     | Válassza ki ezt a lehetőséget, ha szeretné érvényteleníteni a feladási profillal rendelkező tranzakciókat.                                                                                                               |
| **Zárás**      | Válasszon ki egy másik feladási profilt, amelyre váltani szeretne a jelen feladási profilt használó tranzakciók bezárásakor. Egy tranzakció akkor minősül bezártnak, ha a teljes kiegyenlítése megtörtént.                                       |






