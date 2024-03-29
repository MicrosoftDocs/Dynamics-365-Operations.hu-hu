---
title: Szállítási alternatívák
description: Az értékesítési rendelések a Szállítási alternatívák lap használatával tájékozódhatnak az alternatív rendelésteljesítési beállításokról.
author: Henrikan
ms.date: 04/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: henrikan
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f58f7923d82f3aa371ba916352211195870f9a75
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572625"
---
# <a name="delivery-alternatives"></a>Szállítási alternatívák

[!include [banner](../includes/banner.md)]

Az értékesítési rendelések felvevői a **Szállítási alternatívák** oldalt használhatják arra, hogy alternatív lehetőségeket keressenek a rendelés teljesítéséhez.

A **Szállítási alternatívák** oldal elrendezése lehetővé teszi az alternatív lehetőségek áttekintését. Ezenkívül lehetővé teszi a rendelés végrehajtói számára, hogy az aktuális vállalaton túl keressenek teljesítési lehetőségeket. Megtekinthetik a vállalatközi lehetőségeket és a külső szállítók által biztosított lehetőségeket is. A beállítások szállítási dátum szerint történő rendezésével az értékesítési rendelés végrehajtói a szállítási alternatívák intelligens listáját tekinthetik meg. Ezenkívül a paraméterek segítségével jobban kezelhetik a javasolt szállításokat. Mivel a szállítási idő hatással lehet a szállítási dátumokra, az értékesítési rendelés végrehajtói tallózhatnak a szállítmányozók által megadott különböző szállítási beállítások között. Mivel minden javaslat mellett részletes információk jelennek meg, a rendelés végrehajtói megalapozott döntést hozhatnak közvetlenül a **Szállítási alternatívák** lap alapján.

## <a name="open-the-delivery-alternatives-page"></a>A Szállítási alternatívák lap megnyitása

Az értékesítési rendelés soráról megnyithatja a **Szállítási alternatívák** képernyőt.

1. Válassza a **Termékek és készlet \> Szállítási alternatívák** lehetőséget.
1. Válassza a **Sor adatai \> Szállítás \> Szállítási alternatívák** lehetőséget.

A **Szállítási alternatívák** lapot az **Értékesítési rendelés feldolgozása és lekérdezése** munkaterület megnyitásával is megnyithatja, ahol válassza a **Rendelések és kedvencek \> Késleltetett rendeléssorok \> Szállítási alternatívák** lehetőséget **Megjegyzés:** a **Szállítási alternatívák** lapot csak akkor nyithatja meg ha teljesül mindkét következő feltétel:

- Minden kötelező értékesítési sor adata ki van töltve.
- A **Szállítási dátum ellenőrzése** mező a **Nincs** értéktől eltérő értékre van állítva.

## <a name="delivery-date-control-methods"></a>Szállítási dátum ellenőrzési módszerei

A szállítási dátum ellenőrzési módszere határozza meg, a szállítási dátumok rendszer általi létrehozásának módját, a szállítási alternatívák kiszámításának a módját, valamint a megjelenő információkat. Vegye figyelembe, hogy a szállítási dátum ellenőrzése naptárakat vesz figyelembe. Emiatt a következő naptárak hatással lehetnek a javasolt bevételezési dátumra: a raktárhoz rendelt naptár, a szállítási naptár, a szállítóhoz rendelt naptár és a vevőhöz rendelt naptár. A következő táblázat leírja a szállítási dátum ellenőrzésének egyes módszereit.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Metódus</strong></td>
<td><strong>Leírás</strong></td>
</tr>
<tr class="even">
<td><strong>None</strong></td>
<td><ul>
<li>Az értékesítési sorok szállítási alternatívái nem támogatottak. Ez a beállítás kikapcsolja a szállítási dátum ellenőrzését.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Értékesítés átfutási ideje</strong></td>
<td><ul>
<li>A szállítási alternatívák kiszámítása az előre meghatározott értékesítési átfutási időn alapul. A szállítási napok kiszámítása a szállítási módon alapul.</li>
<li>A szállítási alternatívák tartalmazzák az aktuális készlettel rendelkező raktárak és a készlet- és igényrendelések kínálatát.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Ígérethez rendelkezésre áll</strong></td>
<td><ul>
<li>A szállítási alternatívák kiszámítása az ígérethez rendelkezésre álló logikán alapul. A rendszer a jelenlegi elérhetőséget és a várható jövőbeli elérhetőséget veszi figyelembe. A szállítási napok kiszámítása a szállítási módon alapul.</li>
<li>A szállítási alternatívák tartalmazzák az aktuális készlettel rendelkező raktárak és a készlet- és igényrendelések kínálatát.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Ígérethez rendelkezésre áll + kiadási időtartalék</strong></td>
<td><ul>
<li>A szállítási alternatívákat az ígérethez rendelkezésre állás metódus alapján számítja ki a rendszer, de a számításba belefoglalja a kiadási időtartalékot is.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Ígérhető (CTP)</strong></td>
<td><ul>
<li>A szállítási alternatívák kiszámítása az ígérhető logikán alapul. Az MRP-alábontás az elérhetőség meghatározására szolgál. Vegye figyelembe, az ígérhető minimálisan eltolja a szállítási dátumokat az értékesítés átfutási idejéhez. A szállítási napok kiszámítása a szállítási módon alapul.</li>
<li>A szállítási alternatívák a következő raktárakra vonatkozó javaslatokat tartalmazzák:
<ul>
<li>Aktuális raktár</li>
<li>Alapértelmezett raktár</li>
<li>Rendelkezésre álló aktuális készlettel rendelkező raktárak</li>
<li>Ellátási rendelésekkel rendelkező raktárak</li>
<li>Aktív anyagjegyzék-verziókkal rendelkező raktárak</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>Szállítási alternatívák adatainak megtekintése

Ez a szakasz bemutatja a szállítási alternatívák adatait, amelyeket a **Szállítási alternatívák** gyorslap egyes lapjain érhetők el.

### <a name="the-product-fasttab"></a>A Termék gyorslap

Ez a gyorslap megjeleníti a termék összegzését és az aktuális értékesítési sor részletes adatait.

### <a name="the-delivery-alternatives-fasttab"></a>A Szállítási alternatívák gyorslap

Ez a gyorslap a termékbevételezési dátumok szerint rendezett szállítási alternatívák listáját jeleníti meg. A lista fölött kiválaszthatja a javaslat alapját képező lehetőségeket. Kiválaszthatja a szállítási módot is, amely meghatározza a szállítási napokat is. Az alábbi lehetőségek közül választhat:

- **Egyéb termékváltozatok belefoglalása** – Ez a lehetőség a termékváltozatokkal rendelkező termékek esetében érhető el. Ez magában foglalja a termék többi változatának szállítási módszereit. Ez a beállítás nem érhető el az ígérhető verzió esetében.
- **Részleges mennyiség szerepeltetése** – Alapértelmezés szerint itt csak azok a javaslatok szerepelnek, amelyek megfelelnek az értékesítési sor teljes mennyiségének. Válassza ezt a lehetőséget az olyan javaslatok szerepeltetéséhez, amelyek csak részben felelnek meg a rendeléssornak. Ez akkor hasznos, amikor a vevő korábbi szállítási dátumot kér, és elfogadja a részleges szállítást.
- **Későbbi dátumok belefoglalása** – Alapértelmezett módon itt csak azon javaslatok jelennek meg, amelyek jobbak (korábbiak) az értékesítési sorban levő aktuális dátumnál. A későbbi dátumok belefoglalásához válassza ezt a lehetőséget. Ez a beállítás olyankor lehet hasznos, ahol a dátumtól eltérő paraméterek élveznek prioritást. Például ha egy adott szállítót vagy raktárt részesítene előnyben.
- **Szállítás módja** – Válassza ki az előnyben részesített szállítási módot a szállítási idő és költség optimalizálása érdekében. Azonnal láthatja a javasolt szállítási alternatívákra gyakorolt hatást. Ezért az alternatívák összevetése egyszerű.
- **Beszerzéssel együtt** – Ha a beszerzés be van jelölve, a javasolt szállítási alternatívák tartalmazzák mind a külső szállítóktól, mind a vállalaton belüli (vállalatközi) más vállalatoktól történő beszerzési lehetőségeket. A **Beszerzéssel együtt** lehetőséget az ígérethez rendelkezésre áll és az ígérethez rendelkezésre áll+ kiadási időtartalék szállításidátum-ellenőrzés is támogatja. Ebben szerepelnek a termék alapértelmezett beszerzési szállítójának beszerzési beállításai és a termék összes engedélyezett szállítója.
- Külső szállítók esetén a kiszámítás alapját a beszerzés átfutási ideje képezi.
- Vállalatközi szállítók esetén a számítás a forrásvállalatnál végzett szállításidátum-ellenőrzés alapján megvizsgálja, hogy mi érhető el a forrásvállalatnál.
- **Szállítás típusa** (A beszerzés szempontjából releváns)
  - **Készlet** – A termékeket a forrásraktárból az értékesítési soron az adott helyre/raktárba szállítják. Ezután a termékeket kiszállítják az adott raktárból a vevőnek.
  - **Közvetlen kiszállítás** – A termékeket a forrásraktárból közvetlenül a vevőnek szállítják ki.

### <a name="the-availability-information-fasttab"></a>Az Elérhetőség adatai gyorslap

Az ezen a gyorslapon található adatok a kijelölt alternatív kézbesítési sorhoz kapcsolódnak. A következő információk jelennek meg az értékesítési sor szállításidátum-ellenőrzésétől függően:

- **Értékesítés átfutási ideje**
  - **Elérhető ma** – A tényleges aktuális, a ténylegesen lefoglalt és a rendelkezésre álló tényleges készletet jeleníti meg.
  - **Paraméterek** – A készletegység és az értékesítés átfutási idejét jelenítik meg.

- **Ígérethez rendelkezésre áll és ígérethez rendelkezésre áll + kiadási időtartalék**
  - **Elérhető ma** – A tényleges aktuális, a ténylegesen lefoglalt és a rendelkezésre álló tényleges készletet jeleníti meg.
  - **Paraméterek** – A készletegység és az értékesítés átfutási idejét jelenítik meg.
  - **Jövőbeli elérhetőség** – A kiválasztott hely és raktár jelenlegi és jövőbeli elérhetőségének grafikus ábrázolását jeleníti meg a **Szállítási alternatívák** lapon. A diagram oszlopait kiválasztva részletesebb információkat tek‌inthet meg a termék jövőbeli elérhetőségéről. A csúszka az ígérethez rendelkezésre álló időkorláton belüli feltételnek megfelelő igény- és ellátási rendelések listáját jeleníti meg.

- **Ígérhető**
  - **Elérhető ma** – A tényleges aktuális, a ténylegesen lefoglalt és a rendelkezésre álló tényleges készletet jeleníti meg.
  - **Paraméterek** – A készletegység és az értékesítés átfutási idejét jelenítik meg.
  - **Alábontás** – Megjeleníti a kiválasztott szállítási alternatíva készlet alábontását. A **Beállítás** pontban módosíthatja az alábontásban megjelenített mezőket és készletdimenziókat.

### <a name="the-impact-of-selected-alternative-fasttab"></a>A Kiválasztott alternatív kézbesítés hatása gyorslap

Ez a gyorslap kiemeli a kiválasztott szállítási alternatíva hatását. Ha az **OK** gombot választja, az értékesítési sor a KIJELÖLT oszlopokban a kijelölt értékekkel frissül. Vegye figyelembe, hogy ha a kiválasztott szállítási alternatíva mennyisége kisebb, mint az értékesítési sorban szereplő mennyiség, szállítási ütemezés jön létre, és a rendelési sor két sorra oszlik: egy sor a kiválasztott mennyiséget, a másik pedig a fennmaradó mennyiséget jeleníti meg. Frissítheti a kereskedelmi sort is, hogy az megfeleljen az ütemezési soroknak, és befolyásolja az árképzést.

## <a name="additional-resources"></a>További erőforrások

[Rendelési ígéretek](delivery-dates-available-promise-calculations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]