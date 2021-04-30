---
title: A visszaadott cikkek kivezetési módjának megadása
description: A visszaadott cikkek kivezetési módjának megadása.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c827df81621346733953dc77e16e269f8c3767a8
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910113"
---
# <a name="specify-how-to-dispose-of-returned-items"></a>A visszaadott cikkek kivezetési módjának megadása 

[!include [banner](../includes/banner.md)]


Visszárurendelés kezelése esetén egy visszajuttatási okkóddal meg kell adnia, hogy a terméket miért küldték vissza. Emellett egy intézkedéskóddal és egy intézkedési művelettel meg kell határoznia, hogy mi történjen a visszaküldött termékkel.

Az intézkedési kód a visszárurendelés létrehozásakor, a cikkbeérkezés regisztrálásakor illetve a csomagjegyzék frissítésekor, valamint a karanténutasítás befejezésekor alkalmazható.

Az üzleti folyamatoknak megfelelően igény szerint bármilyen intézkedési kódot meghatározhat. A következő táblázatban néhány jellemzően használt kód szerepel, amely a visszárukra vonatkozó intézkedés kijelölésére használható.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Intézkedés típusa</p></th>
<th><p>Általános kód</p></th>
<th><p>Leírás</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Kivezetés</p></td>
<td><p>SC</p></td>
<td><p>Selejtezés/megsemmisítés</p></td>
</tr>
<tr class="even">
<td><p>Kivezetés</p></td>
<td><p>DC</p></td>
<td><p>Adományozás jótékony célra</p></td>
</tr>
<tr class="odd">
<td><p>Kivezetés</p></td>
<td><p>TD</p></td>
<td><p>Átadás külső félnek</p></td>
</tr>
<tr class="even">
<td><p>Kivezetés</p></td>
<td><p>SL</p></td>
<td><p>Megmentés</p></td>
</tr>
<tr class="odd">
<td><p>Kivezetés</p></td>
<td><p>TS</p></td>
<td><p>Eladás külső félnek (másodlagos piacok)</p></td>
</tr>
<tr class="even">
<td><p>Javítás/módosítás</p></td>
<td><p>RW</p></td>
<td><p>Átdolgozás</p></td>
</tr>
<tr class="odd">
<td><p>Javítás/módosítás</p></td>
<td><p>RF</p></td>
<td><p>Újragyártás/hasznosítás</p></td>
</tr>
<tr class="even">
<td><p>Javítás/módosítás</p></td>
<td><p>MD</p></td>
<td><p>Módosítás</p></td>
</tr>
<tr class="odd">
<td><p>Javítás/módosítás</p></td>
<td><p>RP</p></td>
<td><p>Javítás</p></td>
</tr>
<tr class="even">
<td><p>Javítás/módosítás</p></td>
<td><p>RV</p></td>
<td><p>Visszajuttatás a szállítóhoz</p></td>
</tr>
<tr class="odd">
<td><p>Egyéb</p></td>
<td><p>AI</p></td>
<td><p>Felhasználás változatlan formában</p></td>
</tr>
<tr class="even">
<td><p>Egyéb</p></td>
<td><p>RS</p></td>
<td><p>Viszontértékesítés</p></td>
</tr>
<tr class="odd">
<td><p>Egyéb</p></td>
<td><p>EX</p></td>
<td><p>Átváltás</p></td>
</tr>
<tr class="even">
<td><p>Egyéb</p></td>
<td><p>MS</p></td>
<td><p>Vegyes</p></td>
</tr>
</tbody>
</table>


Minden egyes intézkedési kódhoz választania kell egy intézkedési műveletet is. Az intézkedési művelet az intézkedési kód fizikai és pénzügyi vonatkozásait határozza meg. Az intézkedési művelet határozza meg többek között a visszáru fizikai kezelési módját, pénzügyi hatását, illetve azt, hogy kell-e cserecikket küldeni az ügyfélnek. Az üzleti igényeknek megfelelően korlátlan számú intézkedési kódot definiálhat, azonban mindössze hat előre definiált intézkedési művelet közül választhat. Az alábbi táblázatban az intézkedési műveletek és definícióik szerepelnek.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Intézkedési művelet</p></th>
<th><p>Leírás</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Jóváírás</strong></p></td>
<td><p>A cikk visszahelyezése a készletbe és a cikk értékének jóváírása a vevő számára.</p></td>
</tr>
<tr class="even">
<td><p><strong>Csak követelés</strong></p></td>
<td><p>A cikk értékének jóváírása a cikk visszaküldésének igénylése nélkül.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Selejt</strong></p></td>
<td><p>A cikk leselejtezése és értékének jóváírása a vevő számára.</p></td>
</tr>
<tr class="even">
<td><p><strong>Csere és jóváírás</strong></p></td>
<td><p>A cikk visszahelyezése a készletbe, csererendelés létrehozása és az összeg jóváírása a vevő számára.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Csere és selejtezés</strong></p></td>
<td><p>A cikk leselejtezése, csererendelés létrehozása és az összes jóváírása a vevő számára.</p></td>
</tr>
<tr class="even">
<td><p><strong>Vissza a vevőnek</strong></p></td>
<td><p>A visszáru elutasítása és visszaküldése a vevőnek.</p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a>Intézkedési kód választása karanténutasításhoz

1.  Kattintson ide: **Készletkezelés** \> **Időszakos** \> **Minőségkezelés** \> **Karanténutasítások**.

2.  Meglévő karanténutasításokhoz válasszon egy műveletet az **Áttekintés** lap **Intézkedési kód** mezőjében.



## <a name="see-also"></a>Lásd még

[Karanténutasítás (képernyő)](/dynamicsax-2012//quarantine-order-form)

[Intézkedési kódok (képernyő)](https://technet.microsoft.com/library/hh597113\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]