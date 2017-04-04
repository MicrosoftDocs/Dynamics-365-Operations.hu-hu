---
title: "A Warehousing app app mezőnevek konfigurálása"
description: "Ez a témakör ismerteti meghatározása és konfigurálása a raktári app mezőneveket és prioritások Dynamics 365 műveletekhez."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: ce8f6d6f7090995bc44db1ba0103a7d6c0416620
ms.lasthandoff: 03/31/2017


---

# <a name="configure-app-field-names-in-warehousing-app"></a>A Warehousing app app mezőnevek konfigurálása

Ez a témakör ismerteti meghatározása és konfigurálása a raktári app mezőneveket és prioritások Dynamics 365 műveletekhez. 

**Megjegyzés:** Ez a témakör a Raktárkezelés szolgáltatások vonatkozik. A Készletkezelés szolgáltatások nem vonatkozik. 365 Dynamics - műveletekhez raktározás raktározási feladatok végrehajtásához használt alkalmazás. Meg is határozza meg és állítsa be a mezőneveket, amelyeket az alkalmazás, valamint a mezőnevek hozzárendeli a prioritásának beállítása. Ez a témakör ismerteti az határozza meg, és a raktár app mezőneveket és a prioritások beállítása, és azok hogyan használhatók a Dynamics 365 raktározás - műveletekhez. Dynamics 365 műveletek - raktározás, a kapcsolat beállításával kapcsolatos részletes információkat lásd a tankönyv [telepítse és konfigurálja a Dynamics 365 műveletek - raktározás](install-configure-warehousing-app.md).

<a name="configure-warehouse-app-field-names"></a>Raktári app mezőnevek konfigurálása
===================================

Dynamics 365 - műveletekhez használja a mobileszközön raktározás konfigurálhatók metaadatok hogyan jelenjen meg az eszközön a **app mezőnevek raktár** oldalon. Új vállalat Dynamics 365 műveletekhez, jelölje ki **alapértelmezett beállításainak létrehozása** fogja használni a raktári mobil eszköz munkafolyamatokat, és egy elsődleges beviteli módot és Beviteltípus rendelje hozzá azokat mezőnevek létrehozásához. Miután a mezőnevek hozott létre, kijelölheti a következő beviteli beállítások.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lehetőség</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Preferált beviteli mód</td>
<td>Ez a beállítás meghatározza, hogy a keresési mezőbe, vagy a kézi betáplálási beviteli mező a kijelölt mező nevét kell feltüntetni. Ez akkor hasznos, mezők függően különbséget tenni a vonalkód mező használatakor. <strong>Megjegyzés:</strong> a mezőnevek elsődleges beviteli mód beállítása <strong>ellenőrzés</strong>, adatokat manuálisan adhat meg, ha a vonalkód nem olvasható vagy sérült.</td>
</tr>
<tr class="even">
<td>Beviteltípus</td>
<td>Ez a beállítás határozza meg, milyen beviteli típust kell használni a kiválasztott mező nevét. Négy lehetőségek állnak rendelkezésre:
<ul>
<li><strong>Kijelölés</strong> - a választható lehetőségek listáját tartalmazza. Ezzel a beállítással a mezőnevek nincsenek szerkeszthető.</li>
<li><strong>Dátum</strong> - mezőben megadott dátum jelenik meg a kívánt dátumformátumot a címkével ellátott nevek. Ez segít, lásd: Adja meg a dátumot, hogy a raktárosok. Ezzel a beállítással a mezőnevek nincsenek szerkeszthető.</li>
<li><strong>Alfa</strong> - ki, ha az eszköz billentyűzet során alkalmazandó adatok manuális bevitele az alkalmazás. A billentyűzet élmény eszköz használt függően módosítható.</li>
<li><strong>Numerikus</strong> - a mezőnevek, hogy csak bevitel használata numerikus, akkor válassza ezt az opciót egy egyéni numerikus billentyűzet segítségével az eszköz billentyűzet helyett a beviteli mező megjelenítéséhez.</li>
</ul></td>
</tr>
</tbody>
</table>

<a name="configure-warehouse-app-field-priority"></a>Raktári app mező prioritásának beállítása
======================================

A a **raktár mezőben prioritás app** lapon elhelyezhet mezőneveket különböző prioritási csoportokba. Ez lehetővé teszi annak eldöntésére, hogy milyen információkat kell megjelenítenie a fő feladat lapon az alkalmazás feladatok végrehajtásakor a raktárosok. Ha **alapértelmezett beállításainak létrehozása**, alapértelmezés szerinti prioritás csoportokat hoz létre. Szükség szerint tetszőleges számú kiemelt csoportok létrehozására, de csak három kiemelt csoportok jelennek meg a feladat lap. Dynamics 365 műveletek az alkalmazás metaadat küld, amikor azt fogja hozzárendelni az egyes mezők attól függően, hogy a prioritás csoport a relatív prioritását, és az alkalmazás jelenik meg az első három kiemelt csoportok a metaadatok, a feladat lapon található. A túlnyúló metaadatokat a többi másodlagos részletek lapon jelenik meg. A következő táblázat például öt kiemelt csoportok.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prioritás csoport</th>
<th>Hozzárendelt mezők</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> Prioritás 10</td>
<td><ul>
<li>Tétel</li>
<li>Mennyiség</li>
<li>Mértékegység</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioritás: 20</td>
<td><ul>
<li>Fürtpozíció</li>
<li>Fürt</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioritás: 30</td>
<td><ul>
<li>Cikk leírása</li>
</ul></td>
</tr>
<tr class="even">
<td> Prioritás: 40</td>
<td><ul>
<li>Konfiguráció</li>
<li>Szín</li>
<li>Méret</li>
<li>Stílus</li>
</ul></td>
</tr>
<tr class="odd">
<td> Prioritás: 50</td>
<td><ul>
<li>Tárolóhely</li>
<li>Azonosítótábla</li>
</ul></td>
</tr>
</tbody>
</table>

Például amikor a raktáros van valamilyen műveletet hajt végre egy mobil eszköz, ha megjelenik az alkalmazás metaadatok áll a következő mezőket:

-   Tétel
-   Mennyiség
-   Mértékegység
-   Cikk leírása
-   Méretét és helyét

A fenti táblában beállított raktár app mezőben prioritás alapján, a következő 3 sor információ jelenik meg a feladat lapon:

-   1. sor: Cikk, mennyiség, mértékegység
-   2. sor: Cikk leírása
-   3 sor: méret

A megmaradt metaadatait, például a hely nem fog megjelenni a feladat lapon, de a részletek lapon fog megjelenni. További és példák a felhasználói felület, olvassa el a blogbejegyzést [Dynamics 365 bejelentése műveletek - raktározás](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/).

<a name="see-also"></a>Lásd még
--------

[Telepítse és konfigurálja a Microsoft Dynamics 365 műveletekhez – raktározás](install-configure-warehousing-app.md)


