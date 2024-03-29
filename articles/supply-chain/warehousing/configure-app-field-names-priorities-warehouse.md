---
title: A Warehouse Management mobilalkalmazás mezőinek konfigurálása
description: Ez a témakör leírja, hogyan lehet beállítani és beállítani a Raktárkezelés mobilalkalmazásban megjelenő mezők nevét és prioritását.
author: Mirzaab
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField, WHSMobileAppFieldPriority
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269434
ms.assetid: 6cf3d7da-29bb-4d3d-aaf5-544ca9cc2980
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 00a20faaa05a9d0891ee202951b1ca50d0176c83
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065958"
---
# <a name="configure-fields-for-the-warehouse-management-mobile-app"></a>A Warehouse Management mobilalkalmazás mezőinek konfigurálása

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan lehet beállítani és beállítani a Raktárkezelés mobilalkalmazásban megjelenő mezők nevét és prioritását.

> [!NOTE]
> Ez a cikk a Raktárkezelés funkcióira vonatkozik. A Készletkezelés funkciókra nem vonatkozik. A Raktárkezelés mobilalkalmazás egy raktározási feladatok végrehajtásához használt alkalmazás. Meghatározhatja és beállíthatja az alkalmazásban használt mezőneveket, és konfigurálhatja a prioritást, amelyhez a mezőneveket hozzá kell rendelni. Ez a cikk bemutatja a Raktárkezelés mobilalkalmazás e mezőnevének és prioritásának a beállítását, valamint használatukról.

## <a name="configure-warehouse-app-field-names"></a>A raktári alkalmazáson belüli mezőnevek konfigurálása

Amikor a Warehousing alkalmazást a mobileszközön használja, konfigurálható, hogyan jelenjenek meg az eszközön a metaadatok **A raktári alkalmazáson belüli mezőnevek** oldalon. Egy felvett új vállalatnál válassza az **Alapértelmezett beállítás létrehozása** elemet a raktármodul mobileszközön használt munkafolyamataiban használt összes mezőnév létrehozásához, majd rendeljen hozzájuk egy elsődleges beviteli módot és beviteltípust. Az összes mezőnév létrehozása után a következő beviteli beállításokat választhatja ki.

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
<td>Ez a beállítás határozza meg, hogy egy keresési mező vagy egy kézi beviteli mező jelenjen-e meg a kijelölt mezőnévnél. Ez hasznos a mezők megkülönböztetéséhez attól függően, hogy a mezőhöz vonalkódot használnak-e. <strong>Megjegyzés:</strong> Azon mezőnevek esetében, amelyeknél az előnyben részesített beviteli mód <strong>Beolvasás</strong> beállítása van megadva, manuálisan is megadhatja az adatokat, ha a vonalkód nem olvasható vagy sérült.</td>
</tr>
<tr class="even">
<td>Beviteltípus</td>
<td>Ez a beállítás határozza meg, milyen beviteli típus legyen használva a kiválasztott mezőnévnél. Négy lehetőség érhető el:
<ul>
<li><strong>Kiválasztás</strong> - választható lehetőségek listáját tartalmazza. Ezzel a beállítással a mezőnevek nem szerkeszthetők.</li>
<li><strong>Dátum</strong> - a dátumként megadott mezőnevek dátumformátumot jelenítenek meg a címkével. Ez segít a raktárosoknak látni, milyen formátumban adják meg a dátumot. Ezzel a beállítással a mezőnevek nem szerkeszthetők.</li>
<li><strong>Alfa</strong> - kiválasztása esetén az eszköz billentyűzetén kell adatokat manuálisan bevinni az alkalmazásban. A billentyűzet felülete módosítható a használt eszköztől függően.</li>
<li><strong>Numerikus</strong> - a csak numerikus bevitelt használó mezőneveknél ennek a lehetőségnek a kiválasztásával egyéni számbillentyűzet jeleníthető meg a beviteli mezőnél az eszköz billentyűzete helyett.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="configure-warehouse-app-field-priority"></a>A raktári alkalmazáson belüli mezőprioritások beállítása

**A raktári alkalmazáson belüli mezőprioritás** oldalon a mezőneveket különböző prioritási csoportokba rendezheti. Ez lehetővé teszi annak eldöntését, hogy milyen információk jelenjenek meg a fő feladatlapon, amikor a raktári dolgozók feladatokat végeznek az alkalmazás használatával. Ha az **Alapértelmezett beállítás létrehozása** elemre kattint, létrejön az alapértelmezés szerinti prioritáscsoportok sorozata. Szükség szerint tetszőleges számú prioritási csoport hozható létre, de a feladatlapon csak három prioritási csoport jelenik meg. Amikor a rendszer metaadatokat küld az alkalmazásnak, minden mezőhöz relatív prioritást rendel a prioritási csoportjától függően, és az alkalmazás a metaadatokban található első három prioritási csoportot jeleníti meg a feladatlapon. Az ezen felüli metaadatok a másodlagos részletek lapon jelennek meg. A következő táblázat öt prioritási csoportra mutat példát.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prioritási csoport</th>
<th>Hozzárendelt mezők</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> 10. prioritás</td>
<td><ul>
<li>Tétel</li>
<li>Mennyiség</li>
<li>Mértékegység</li>
</ul></td>
</tr>
<tr class="even">
<td> 20. prioritás</td>
<td><ul>
<li>Fürtpozíció</li>
<li>Fürt</li>
</ul></td>
</tr>
<tr class="odd">
<td> 30. prioritás</td>
<td><ul>
<li>Cikk leírása</li>
</ul></td>
</tr>
<tr class="even">
<td> 40. prioritás</td>
<td><ul>
<li>Konfiguráció</li>
<li>Szín</li>
<li>Méret</li>
<li>Stílus</li>
</ul></td>
</tr>
<tr class="odd">
<td> 50. prioritás</td>
<td><ul>
<li>Tárolóhely</li>
<li>Azonosítótábla</li>
</ul></td>
</tr>
</tbody>
</table>

Például amikor egy raktári dolgozó valamilyen műveletet hajt végre egy mobileszközön, ha az alkalmazásban megjelenő metaadatok a következő mezőkből állnak:

-   Tétel
-   Mennyiség
-   Mértékegység
-   Cikk leírása
-   Méret és hely

A raktári alkalmazás a fenti táblában beállított mezőprioritásai alapján a következő 3 sor információ jelenik meg a feladatlapon:

-   1. sor: Elem, Mennyiség, Mértékegysége
-   2. sor: Elem leírása
-   3. sor: méret

A fennmaradó metaadatok, például a Hely nem fog megjelenni a feladatlapon, de megjelenik a részletek lapon. További információért és a felhasználói felülettel kapcsolatos példákért olvassa el [A Dynamics 365 Supply Chain Management- Warehousing bejelentése](https://blogs.msdn.microsoft.com/dynamicsaxscm/2017/01/20/announcing-dynamics-365-for-operations-warehousing/) blogbejegyzést.

## <a name="additional-resources"></a>További erőforrások

[A Raktárkezelés mobilalkalmazás telepítése és csatlakoztatása](../warehousing/install-configure-warehouse-management-app.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
