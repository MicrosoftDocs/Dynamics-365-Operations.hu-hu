---
title: Szállítói feladási profilok
description: A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák.
author: abruer
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.form: VendPosting
ms.openlocfilehash: 09f27ef510f38c10fc265b682a492ba5872b6d3e
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799599"
---
# <a name="vendor-posting-profiles"></a>Szállítói feladási profilok

[!include [banner](../includes/banner.md)]

A szállítói feladási profilok a szállítói tranzakciók főkönyvbe történő feladását szabályozzák.

## <a name="vendor-posting-profiles"></a>Szállítói feladási profilok

A szállítói feladási profilok lehetővé teszik, hogy a főkönyvi számlákat és dokumentumbeállításokat az összes szállítóhoz, egy szállítói csoporthoz vagy egyetlen szállítóhoz rendelhesse. Ezek a beállítások a beszerzési rendelések, a szállítói számlák és a készpénzes fizetések létrehozásakor használatosak. Néhány tranzakcióhoz feladói profilt választhat ki, és elsőbbséget élvez azokkal a feladói profilokkal szemben, amelyeket ezen az oldalon állít be a tranzakciókhoz, illetve különbözik tőlük. Az alapértelmezett feladási profil a **Főkönyv és áfa** gyorslapon, a **Kötelezettségek paraméterei** lapon van megadva. Az alapértelmezett feladási profil automatikusan szerepel majd az új dokumentumok fejlécén, ahol szükség esetén módosíthatja egy másik feladási profilra.

A **Tranzakció-feladásdefiníciók** oldalon a tranzakció feladási típusaihoz társíthatja a feladásdefiníciókat. A feladásidefiníciók irányítják a a szállítói tranzakciók feladását a főkönyvbe a feladói profilok helyett.

## <a name="creating-a-posting-profile"></a>Hozzon létre feladási profilt
### <a name="setup"></a>**Beállítás**

Határozza meg a tranzakciók feladásában használt főkönyvet, ami a kijelölt feladási profilt használja. Válassza ki a kijelölt feladási profil számlakódját, és amennyiben lehetséges, számla- vagy csoportszámát. A feladási folyamat során a program kiválasztja az egyes tranzakciók legmegfelelőbb feladási profilját oly módon, hogy megkeresi a legspecifikusabb számlakód-, számlaszám-, illetve csoportszám-kombinációt az alábbi prioritás szerint.

| **Számla kód** mezőérték | **Számla/Csoport száma** mezőérték        | Keresési prioritás |
|------------------------------|---------------------------------------------|-----------------|
| **Tábla**                    | Konkrét szállítói számla                     | 1               |
| **Csoport**                    | A szállítóhoz rendelt szállítócsoport | 2               |
| **Összes**                      | Üres                                       | 3               |

Ha azt szeretné, hogy a szállítói tranzakciók feladási profiljai megegyezzenek, akkor csak egy feladási profilt állítson be **Összes** értékkel a **Számlakód** mezőben. Adja meg a következő értékeket a feladási profil beállításához.

<table>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Feladási profil</strong></td>
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
<li><strong>Asztal</strong>– A feladási profilok egyetlen szállítóra vonatkoznak. Válassza ki a szállítói számlát a <strong>Számla/csoport száma</strong> mezőben.</li>
<li><strong>Csoport</strong>– A feladási profilok szállító csoportra vonatkoznak. Válassza ki a szállítói csoportot a <strong>Számla/csoport száma</strong> mezőben.</li>
<li><strong>Összes</strong>– A feladási profilok az összes szállítóra vonatkoznak. Hagyja üresen a <strong>Számla/csoport száma</strong> mezőt.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Számla/csoport száma</strong></td>
<td>Ha a <strong>Tábla</strong> lehetőséget választja ki a <strong>Számlakód</strong> mezőben, akkor válassza ki a feladási profilhoz társított szállító számlaszámát. Ha a <strong>Csoport</strong> lehetőséget választja, válasszon egy szállítói csoportot. Ha az <strong>Összes</strong> lehetőséget választja, hagyja ezt a mezőt üresen.</td>
</tr>
<tr class="odd">
<td><strong>Összegzett számla</strong></td>
<td>Válassza ki azt a főkönyvi sámlát, amit a szállító összegző számlajaként használ, amikhez a feladási profil kapcsolódik. A <strong>Manuális bevitel tiltása</strong> paraméter meg lesz jelölve ehhez a fő számlához. Ha ezt követően eltávolítja ezt a számlát a feladási profilból, ellenőrizze a <strong>Manuális bevitel tiltása</strong> beállítást a <strong>Fő számla</strong> oldalon. 
<p><strong>Megjegyzés:</strong> Ha a <strong>Feladásdefiníciók használata</strong> beállítást kiválasztja a <strong>Főkönyvi paraméterek</strong> oldalon, a rendszer a tranzakciók szállítói számlákhoz tartozó feladásdefinícióját használja majd, nem az összegző számlák definícióját.</p>
</td>
</tr>
<tr class="even">
<td><strong>Számla kiegyenlítése</strong></td>
<td>Válassza ki a pénzforgalmi előrejelzéshez használt likviditási főkönyvi számlát. Ez a mező csak akkor érhető el, ha engedélyezve van a pénzforgalmi előrejelzés.</td>
</tr>
<tr class="odd">
<td><strong>Áfaelőlegek</strong></td>
<td>Válassza ki az előre törlesztett adó kifizetések számlaszámát.
<p><strong>Megjegyzés:</strong> Azt a feladási profilt, amely akkor használatos, ha a fizetés előlegként van megjelölve, a <strong>Feladás</strong> profilban kell kiválasztani, a <strong>Kötelezettségek paraméterei</strong> oldal <strong>Főkönyv és áfa</strong> területének <strong>Előlegnapló-bizonylat</strong> mezőjében.</p>
</td>
</tr>
<tr class="even">
<td><strong>Beérkezés</strong></td>
<td>Válassza ki a főkönyvi számlát, amelyre a nem jóváhagyott szállítói számlákkal kapcsolatos információkat feladja. Az adatok a Számlajegyzék naplóba <strong>való beírása</strong>. Például, egy felhasználó alapvető adatokat ad meg szállítói számlákról, amikor megkapta a számlajegyzéket. A számlajegyzék feladásakor a tranzakciók az itt és az <strong>Ellenszámla</strong> mezőben megadott számlára kerülnek. A számlák jóváhagyását követően a kötelezettség átkerül a beérkezési számláról a szállítói összegző számlára.</td>
</tr>
<tr class="odd">
<td><strong>Ellenszámla</strong></td>
<td>Válassza ki a számlajegyzék segítségével frissített, nem jóváhagyott szállítói számlák kiegyenlítéséhez használt főkönyvet. Az ellenszámla a beérkezés számlákra feladott tranzakciók ellenszámlájaként viselkedik. Ezért a számla tartalmazza a még nem jóváhagyott szállítói beszerzéseket.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**Táblakorlátozások**

Azokhoz a tranzakciókhoz, amelyeket a feladási profil kiválasztott, meghatározzák, hogy a tranzakció automatikusan ki van-e egyenlítve, a kamat ki van-e számítva, és a fizetési felszólítások ki vannak-e állítva. Kiválaszthatja a kijelölt feladási profillal rendelkező tranzakciók zárásakor használatos számlát.

Adja meg a következő értékeket a feladási profil beállításához

| Mező          | Leírás             |
|----------------|--------------------------------------------------------------------------|
| **Kiegyenlítés** | Válassza ki ezt a lehetőséget a feladási profillal rendelkező tranzakciók automatikus elszámolásának engedélyezéséhez. Ha ez a lehetőség nincs bejelölve, manuálisan kell rendeznie a tranzakciókat a **Nyitott tranzakciók kiegyenlítése** oldalon. |
| **Mégse**     | Válassza ki ezt a lehetőséget, ha szeretné érvényteleníteni a feladási profillal rendelkező tranzakciókat.                              |
| **Zárás**      | Válasszon ki egy másik feladási profilt, amelyre váltani szeretne a jelen feladási profilt használó tranzakciók bezárásakor. Egy tranzakció akkor minősül bezártnak, ha a teljes kiegyenlítése megtörtént.                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
