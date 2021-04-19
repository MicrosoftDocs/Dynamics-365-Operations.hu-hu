---
title: Visszatérítés-kezelés feladási beállítása
description: Ez a témakör a feladási profilok beállítását ismerteti. A feladási profilok a visszatérítés-kezelés számítási soraiba vonatkozó feladási bejegyzések meghatározására használhatók.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: e79feb567a48d08a9063bf20cface3c5c7fe8ecc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831746"
---
# <a name="rebate-management-posting-setup"></a>Visszatérítés-kezelés feladási beállítása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A visszatérítés-kezelési feladási profilok a visszatérítés-kezelés számítási soraiba vonatkozó feladási bejegyzések meghatározására használhatók. Ha az ügylet fejlécében feladási profil van kiválasztva, akkor minden ügyletsorra vonatkozik.

Ez a funkció több vállalatnál (jogi személynél) működik. Megadhatja a vállalatot, amelynél a fedezetek elhatárolása és a követelések kifizetése történik. Forrásfeladási vállalatonként eltérő fedezetterhelési és leírási követelési számlákat is be lehet állítani.

A vevők és szállítók visszatérítés-kezelési feladási profiljainak beállításához kattintson a **Visszatérítés-kezelés \> Visszatérítés-kezelés feladási beállításai \> Visszatérítés-kezelés feladási profiljai** pontra. A **Visszatérítéskezelés feladási profiljai** lap egy listaablakot tartalmaz, amely minden meglévő profilt megjeleníti. A Műveleti panel gombjaival hozzáadhat profilokat a listához, illetve eltávolíthatja azokat.

A témakör további részei leírják, hogy hogyan használhatók a rendelkezésre álló mezők a profilok létrehozásakor és szerkesztésekor.

## <a name="posting-profile-header"></a>Feladási profil fejléce

A következő táblázat leírja az egyes visszatérítés-kezelési feladási profilok fejlécében elérhető beállításokat.

| Mező | Leírás |
|---|---|
| Feladási profil | Adjon meg egyedi nevet a profilhoz. |
| Leírás | Adja meg a profil leírását. |
| Modul | A profilhoz társított visszatérítések és jogdíjak típusának kiválasztása (*Vevő* vagy *Szállító*). |
| Típus | Válassza ki a profil típusát (*Visszatérítés* vagy *Jogdíj*). |
| Kifizetés típusa | <p>Ez a mező a feladott visszatérítés kimenetének formátumát határozza meg.<p><p>Ha a **Típus** mező *Visszatérítésre* van állítva, a következő értékek érhetők el:</p><ul><li>*Nincs* – nincs alapértelmezett feladási típus. Ezért a feldolgozás során meg kell határozni a típust.</li><li>*Fizetés kötelezettségek használatával* – A visszatérítés feladása esetén a rendszer létrehoz egy szállítói számlát az átutalási szállítóhoz, amely be van állítva a visszatérítésben szereplő vevőn.</li><li>*Vevői levonások* – a visszatérítés feladásakor a rendszer létrehoz egy vevői levonási naplót a visszatérítést kapó vevőhöz.</li><li>*Adószámlavevő levonásai* – a visszatérítés feladásakor a rendszer létrehoz egy szabadszöveges számlát a visszatérítést kapó vevőhöz.</li><li>*Kereskedelmi kiadás* – a visszatérítés feladásakor a rendszer létrehoz egy vevői levonási naplót a visszatérítést kapó vevőhöz.</li><li>*Jelentéskészítés* – a visszatérítés feladásakor a rendszer létrehoz egy vevői levonási naplót a visszatérítést kapó vevőhöz.</li></ul><p>Ha a **Típus** mező *Jogdíjra* van állítva, a következő értékek érhetők el:</p><ul><li>*Nincs* – nincs alapértelmezett feladási típus. Ezért a feldolgozás során meg kell határozni a típust.</li><li>*Fizetés kötelezettségek használatával* – A visszatérítés feladása esetén a rendszer létrehoz egy szállítói számlát a visszatérítésben szereplő szállítói számlához.</li><li>*Jelentéskészítés* – A visszatérítés feladása esetén a rendszer létrehoz egy szállítói számlát a visszatérítésben szereplő szállítói számlához.</li></ul><p>További információkat a következő [Fizetési típusok](#payment-types) szakaszban találhat. |
| Cég | Válassza ki a vállalatot (jogi személyt), amelynél a fedezetek elhatárolása és a követelések kifizetése történik. |

### <a name="payment-types"></a>Kifizetéstípusok

Az alábbi táblázat összefoglalja, hogy a **Kifizetés típusa** mező különböző beállításai hogyan hatnak a kifizetések feladására. A kifizetések a céltranzakciótól és a visszatérítés típusától függően vevői számlára, szállítói számlára vagy átutalási számlára is feladhatók.

| Kifizetés típusa | Céltranzakció típusa | Visszatérítés típusa | Kifizetés címzettje (számlafogadó) |
|---|---|---|---|
| Fizetés a Kötelezettségek használatával | Szállítói számla naplója | Vevői visszatérítés | Vevői átutalás szállítói számlája |
| Fizetés a Kötelezettségek használatával | Szállítói számla naplója | Vevői jogdíj | Szállítói számla |
| Fizetés a Kötelezettségek használatával | Szállítói számla naplója | Szállítói visszatérítés | Szállítói számla |
| Vevői levonások | Napi napló | Vevői visszatérítés | Vevőkód |
| Adószámla vevői levonásai | Szabadszöveges számla | Vevői visszatérítés | Vevőkód |
| Kereskedelmi kiadások | Napi napló | Vevői visszatérítés | Vevőkód |
| Jelentés | Napi napló | Vevői visszatérítés | Vevőkód |
| Jelentés | Szállítói számla naplója | Vevői jogdíj | Szállítói számla |
| Jelentés | Szállítói számla naplója | Szállítói visszatérítés | Szállítói számla |

> [!NOTE]
> Vegye figyelembe a következő pontokat a [Visszatérítés-kezelési ügyletek](rebate-management-deals.md) beállításakor:
>
> - Olyan ügyletekhez, amelyekben az **Egyeztetés a következő szerint:** mező értéke *Ügylet*, nem használhatja a dinamikus ügyletszámlát a feladás során. A megadott vevő- vagy szállítói számlát kell használnia.
> - Olyan ügyletekhez, amelyekben az **Egyeztetés a következő szerint:** mező értéke *Sor*, használhat olyan feladási profilt, amely dinamikus ügyletszámlára végez eltolást az ügyletsoron, mert a vevő beállítása ügyletsoronkénti.

## <a name="posting-fasttab"></a>Feladási gyorslap

A következő táblázat leírja az egyes visszatérítés-kezelési feladási profilok **Feladás** gyorslapján elérhető mezőket.

| Mező | Leírás |
|---|---|
| Hitelkeret típusa | Válassza ki, hogy főkönyvi számlára, vevőre vagy szállítóra kell-e jóváírást könyvelni. |
| Követel számla | Az a számla, amelyre a jóváírási összegeket feladja a visszatérítési fedezetek létrehozása esetén. Ezt a számlát használja a program tartozik számlaként is, amikor a visszatérítést feladja a vevői jóváírás céljából. |
| Napló neve<br>(A **Fedezet** szakaszban) | A feladott tartalék rögzítésére használt napló nevének kiválasztása. |
| Típus | Válassza ki, hogy főkönyvi számlára, vevőre vagy szállítóra kell-e visszatérítést feladni. Ha a fejléc **Kifizetés típusa** mezőjének beállítása *Adószámlavevő levonásai*, a jelen mező értéke *Vevő/szállító* lesz. |
| Számla forrásának használata | <p>Válasszon a következő értékek közül:</p><ul><li>*Nincs* – ha ezt az értéket választja, meg kell adnia egy számlát a **Visszatérítési számla** mezőben.</li><li>*Ügyletszámla* – A visszatérítési sorban megadott vevői vagy szállítói számla használata. Ez az érték csak olyan ügyleteknél választható, ahol az **Egyeztetés a következő szerint:** mező értéke *Sor*, és az olyan ügyletsoroknál, ahol a **Számlakód** mező értéke *Tábla*. Vevői jogdíjfeladási profilokra nem vonatkozik.</li></ul> |
| Visszatérítési számla | Erre a számlára lesz feladva a tényleges visszatérítési költség. |
| Napló neve<br>(A **Visszatérítés-kezelés** szakaszban) | Válassza ki annak a naplónak a nevét, amellyel a jóváírást adhat fel a visszatérítés összegére vonatkozóan a vevőnek. Ez a mező nem elérhető, ha a fejléc **Kifizetés típusa** mezőjének beállítása *Adószámlavevő levonásai*. |
| Cikkáfacsoport | Adja meg, hogy a visszatérítés adóköteles-e. |
| Napló neve<br>(A **Leírás** szakaszban) | Ha a feladott visszatérítés nem egyenlő a tartalékkal, le lehet írni a különbözetet. A feladott leírás rögzítésére használt napló nevének kiválasztása. |

## <a name="posting-by-company-fasttab"></a>Feladás vállalat szerint gyorslap

Az egyes visszatérítési feladási profilok **Feladás vállalat szerint** gyorslapjén megadhatja a feladási összeget, amelyet az egyes vállalatok (jogi személyek) használnak a rácsban.

Az eszköztár gombjaival hozzáadhat vállalatokat a rácshoz, illetve eltávolíthatja őket. Minden alkalommal, amikor sort ad hozzá a rácshoz, a **Vállalat** mezőben adja meg a sorhoz a jogi személyt. A **Név** mező beállítása ezután automatikus.

Válassza ki az egyes vállalat sorát, majd írja be a következő adatokat a rács alatti mezők segítségével:

- **Terhelés típusa** – Válassza ki, hogy főkönyvi számlára, vevőre vagy szállítóra kell-e terhelést könyvelni.
- **Tartozik számla** – Adja meg a számlát, amelyre a visszatérítési tartalékok létrehozásakor a terhelés összegét feladják.
- **Fő számla** – válassza ki a fő számlát a leírásokhoz.
