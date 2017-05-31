---
title: "A külső szállítókkal történő szállítói együttműködés"
description: "Ez a témakör bemutatja, hogy a megbízott beszerzők hogyan tudják a Szállítói portált a külső szállítókkal való együttműködésre használni a beszerzési rendelés visszaigazolási folyamata alatt."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b141ed78306504949eae641377b5c5a2b0599572
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="vendor-collaboration-with-external-vendors"></a>A külső szállítókkal történő szállítói együttműködés

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja, hogy a megbízott beszerzők hogyan tudják a Szállítói portált a külső szállítókkal való együttműködésre használni a beszerzési rendelés visszaigazolási folyamata alatt.

A **Szállítói együttműködés** modul azokat a szállítókat célozza meg, akik nem rendelkeznek elektromos adatátviteli (EDI) integrációval a Microsoft Dynamics 365 for Operations rendszerhez. Lehetővé teszi a szállítók számára a beszerzési rendelés, a számla és a bizományosi készlet adatainak kezelését. Ez a témakör leírja, hogyan működhet együtt a szállítói együttműködési felületet használó külső szállítókkal a beszerzési rendelések és a bizományosi készlet kezelésében. Bemutatja, hogyan engedélyezheti egy adott szállítónak a szállítói együttműködés használatát, valamint hogyan definiálja azokat az információkat, amelyeket minden szállító lát egy beszerzési rendelésre történő válaszolás során. Ha többet szeretne megtudni arról, hogy milyen tevékenységeket végezhetnek a külső szállítók a szállítói együttműködési felületen, olvassa el a [Szállítói együttműködés vevőkkel](vendor-collaboration-work-customers-dynamics-365-operations.md) részt.  

Ha többet szeretne megtudni arról, hogyan használhatják a szállítók a szállítói együttműködést a számlázási folyamatokban, olvassa el a [Szállítói együttműködési számlázás munkaterület](/dynamics365/operations/financials/accounts-payable/vendor-portal-invoicing-workspace) részt. Az új szállítói együttműködési felhasználók létrehozásával kapcsolatos tudnivalókat lásd: [Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md).

## <a name="define-the-information-shown-to-vendors-when-they-respond-to-pos"></a>Határozza meg, milyen információ jelenjen meg a szállítóknak a beszerzési rendelésekre történő válaszolás során
Amikor a szállítók reagálnak egy beérkezett beszerzési rendelésre, egy párbeszédpanel jelenik meg a számukra, amelyen meg kell erősíteniük, hogy elfogadják, elutasítják vagy módosításokkal fogadják el a beszerzési rendelést. A szállítónak az adott időpontban megjelenítendő adatok vállalatspecifikusak lehetnek, így megadhatja a három megerősítési üzenet mindegyikén megjelenő szöveget. Például a szöveg tájékoztathatja a szállítót a folyamat következő lépéseivel vagy a szerződési feltételekkel kapcsolatban.  

A beszerzési rendelésen megjelenő szöveg meghatározásához:

1.  Nyissa meg az **Információ beszerzési rendelésekre válaszoló szállítóknak** lapot.
2.  A következő választípusok választhatók:
3.  Kattintson a **Szerkesztés** lehetőségre.
4.  Adja meg a szállítók megjelenítéséhez a kívánt adatokat az **Információs üzenet** mezőben.

Ha egynél több nyelven akar üzeneteket hozzáadni, hozzon létre külön üzeneteket a megfelelő nyelvkóddal. A szállítónak az üzenet az általa használt nyelven jelenik meg.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Szállítói együttműködési lehetőségek beállítása egy adott szállítóhoz
A szállítói együttműködés általános beállításait a Dynamics 365 for Operations rendszerben rendszergazda konfigurálja. Például meghatározza, hogy milyen biztonsági szerepkörök érhetők el az együttműködésben részt vevő szállítók számára. Van néhány olyan beállítás is, amelyeket szállítókódként eltérőek lehetnek, ezeket be kell állítania:

-   Engedélyezze a szállítói együttműködést.
-   Eldöntheti, hogy engedélyezi-e a szállítónak az árakkal kapcsolatos adatok megtekintését.

### <a name="enable-vendor-collaboration"></a>Engedélyezze a szállítói együttműködést

Mielőtt felhasználói fiókokat hozna létre egy külső szállító számára, konfigurálnia kell a szállítókódot a szállítói együttműködés engedélyezése érdekében. Ehhez állítsa az **Együttműködés aktiválása** mezőt aktívra a **Szállítók** lap **Általános** lapján. Két lehetőség közül választhat:

-   **Aktív (beszerzési rendelés automatikus megerősítése)**– A rendszer automatikusan megerősíti a beszerzési rendeléseket, amikor a szállító módosítások nélkül fogadja el azokat.
-   **Aktív (beszerzési rendelés nincs automatikusan megerősítve)**– A beszerzési rendeléseket szervezetének manuálisan kell jóváhagynia, miután a szállító elfogadta azokat.

### <a name="decide-whether-you-want-the-vendor-to-see-price-information"></a>Eldöntheti, hogy engedélyezi-e a szállítónak az árakkal kapcsolatos adatok megtekintését.

Ha meg szeretné osztani az árakkal kapcsolatos adatokat, például az egységárat, az engedményeket és a költségeket az együttműködési felületen keresztül, a **Beszerzési rendelés árai/összege** lehetőséget **Igen** állásba kell állítania a szállítói számlán. Ez a beállítás a **Beszerzési rendelés alapértelmezései** lapon érhető el.

## <a name="work-with-pos-when-using-vendor-collaboration"></a>Beszerzési rendelések kezelése szállítói együttműködési használatakor
### <a name="sending-a-po-to-the-vendor"></a>Beszerzési rendelés küldése a szállítónak

A beszerzési rendeléseket a Dynamics 365 for Operations rendszerben kell elkészíteni. Amikor a beszerzési rendelés állapota **Jóváhagyva**, a szállítónak a **Elküldés visszaigazolásra** művelet segítségével elküldheti a rendelést a **Beszerzési rendelés** lapon. A beszerzési rendelés állapota **Külső ellenőrzés alatt** státuszra változik. A beszerzési rendelés elküldése után a szállító megjelenik a **Beszerzési rendelések véleményezésre** lapon a szállítói együttműködési felületen, ahol elfogadhatja, elutasíthatja és módosításokat javasolhat a rendeléshez. A szállító hozzászólások hozzáadásával oszthat meg olyan információkat, mint a beszerzési rendelés módosítása. Ha fel szeretné hívni a szállító figyelmét az új beszerzési rendelésre, elküldheti azt egy e-mailben is a nyomtatáskezelő rendszer segítségével.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>A beszerzési rendelés szállító általi visszaigazolása és elfogadása

Amikor a szállító elfogadja a beszerzési rendelést, a beszerzési rendelés automatikusan vagy manuálisan erősíthető meg. Ez attól függ, hogy a **Szállító aktiválása** mező értéke **Aktív (beszerzési rendelés automatikus megerősítése)** vagy **Aktív (beszerzési rendelés nincs automatikusan megerősítve)**.  

Az alábbi táblázat bemutatja a tipikus információcserét attól függően, hogy hogyan reagál a szállító, amikor egy beszerzési rendelés visszaigazolást küld nekik.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Szállítói válasz</strong></td>
<td><strong>Eredmény</strong></td>
</tr>
<tr class="even">
<td>A szállító <strong>el</strong>fogadja a rendelést. A Dynamics 365 for Operations rendszer a beszerzési rendelések automatikus visszaigazolására van konfigurálva, abban az esetben, ha a szállító elfogadja a rendelést.</td>
<td>A rendelés állapota <strong>Visszaigazolva</strong> értékre frissül. Ha valami megakadályozza, hogy a rendelést frissítsék, a szállító válasza továbbra is <strong>Elfogadva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad.</td>
</tr>
<tr class="odd">
<td>A szállító <strong>el</strong>fogadja a rendelést. A Dynamics 365 for Operations rendszer nincs a beszerzési rendelések automatikus visszaigazolására konfigurálva abban az esetben, ha a szállító elfogadja a rendelést.</td>
<td>A szállító válasza <strong>Elfogadva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad.</td>
</tr>
<tr class="even">
<td>A szállító <strong>elutasítja</strong> a rendelést.</td>
<td>A szállító válasza <strong>Elutasítva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad. Az elutasítás az indoklással kerül kézbesítésre.</td>
</tr>
<tr class="odd">
<td>Az a szállító, aki <strong>módosításokkal fogadja el a rendelést</strong>. A módosításokat a sor szintjén javasolja a program. Lehetőség van az egyes sorok elfogadására vagy elutasítására. Egyéb lehetséges módosítások a következők:
<ul>
<li>Módosíthatja a dátumokat vagy a mennyiségeket.</li>
<li>Feloszthatja a sorokat eltérő szállítási dátumok vagy mennyiségek alapján.</li>
<li>Helyettesíthet egy cikket.</li>
</ul>
Az árinformáció és a költségek a szállító által nem módosítható értékek. Ezekhez megjegyzések segítségével javasolhat módosításokat.</td>
<td>A szállító válasza <strong>Elfogadva módosításokkal</strong> értékű lesz, <strong></strong> és a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad.</td>
</tr>
</tbody>
</table>

Használhatja a **Beszerzési rendelés** **előkészítése** munkaterületet, hogy nyomon kövesse, mely beszerzési rendelésekre válaszolt a szállító. A munkaterület két listát tartalmaz, amelyek felsorolják a **Külső ellenőrzés alatt** állapotú beszerzési rendeléseket:

-   Külső ellenőrzés alatt, intézkedést igényel.
-   Külső ellenőrzés alatt, a szállító válaszára várva.

### <a name="changing-a-po"></a>Beszerzési rendelés módosítása

Ha módosítani szeretne egy beszerzési rendelést, amire már korábban reagáltak, elküldhet egy új beszerzési rendelést a szállítónak. Az új beszerzési rendelés rendelkezni fog egy verziószám-utótaggal, ami azt jelzi, hogy ez a korábban közölt beszerzési rendelés módosított változata. A **Beszerzési rendelés szállítói visszaigazolásának előzményei** lap segítségével ön és szállítói nyomon követhetik az egyes rendelések előzményeit. A beszerzési rendelés már korábban jóváhagyott verziója a jóváhagyott beszerzési rendelések listáján marad addig, amíg egy új beszerzési rendelés nem lesz jóváhagyva.

### <a name="cancelling-a-po"></a>Beszerzési rendelés visszavonása

A beszerzési rendelés visszavonásakor az állapot **Jóváhagyva** állapotú lesz. Vissza kell küldenie a beszerzési rendelést a szállítónak a Szállítói portálon keresztül, hogy a szállító megerősíthesse vagy elutasíthassa az érvénytelenítést. Az érvénytelenítés jóváhagyása után a beszerzési rendelés a szállító jóváhagyott beszerzési rendeléseinek listáján **Érvénytelenítve** értékkel fog megjelenni.

### <a name="adding-attachments-to-a-po"></a>Mellékletek csatolása beszerzési rendeléshez

A dokumentumkezelő rendszer segítségével fájlokat, képeket és megjegyzéseket csatolhat a beszerzési megrendeléshez. A **Külső** típusú korlátozással rendelkező mellékleteket a szállító a beszerzési rendelés elküldése után tudja megtekinteni.

## <a name="purchase-order-statuses-and-versions"></a>Beszerzési rendelés állapotai és verziói
Ez a szakasz bemutatja a beszerzési rendelés megerősítés előtti különböző állapotait, valamint azt, hogy mikor a beszerzési rendelés új verziói mikor válnak elérhetővé a szállító számára. Az eltérések attól függnek, hogy használja-e a beszerzési rendelések változáskezelését. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Verziók és állapotok, ha nem használja a változáskezelést

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                                                               | **Állapot és verzió**                                                                                                                                       |
| A beszerzési rendelés eredeti verziója a Dynamics 365 for Operations rendszerben jön létre. | Az állapota **Jóváhagyva**.                                                                                                                                  |
| A beszerzési rendelést a rendszer elküldi a szállítónak.                                            | Egy verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.                                          |
| A szállító egy **Elfogadva módosításokkal** választ küld.                  | Az állapot továbbra is **Külső ellenőrzés alatt**.                                                                                                                  |
| Elvégezhet néhány módosítást, amit a szállító kér.                  | Az állapot **Jóváhagyva** állapotra módosul.                                                                                                                        |
| A beszerzési rendelés új verzióját küldi el a szállítónak.                        | Egy új verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.                                      |
| A szállító elfogadja a beszerzési rendelés új verzióját.                            | Az állapot továbbra is **Külső ellenőrzés alatt** lesz kivéve, ha szállító fiókjának beállítása automatikusan **Megerősítve** állapotra vált a beszerzési rendelés elfogadásakor. |

A szállítóknak nem kell jóváhagyniuk a beszerzési rendelést a szállítói együttműködési felületen. Küldhetnek email üzenetet, illetve egyéb csatornákon keresztül is kommunikálhatják a beszerzési rendelés elfogadását. Ezután a rendelést manuálisan is jóváhagyhatja a Dynamics 365 for Operations rendszerben. Ebben az esetben egy figyelmeztetést fog kapni, ami jelzi, hogy a rendelés jóvá lesz hagyva annak ellenére is, hogy nincs válasz a szállítótól. A beszerzési rendelés ezután megjelenik a jóváhagyási előzményekben úgy, mint egy megnyitott rendelés, amelyre nem érkezett válasz. A szállító többé nem tudja majd se elfogadni, se visszautasítani a beszerzési rendelést.  

**Megjegyzés:** A Dynamics 365 for Operations rendszerben mindig a beszerzési rendelés legutolsó verziója érhető el a további folyamatok számára, még akkor is, ha ez a verzió nincs még regisztrálva a szállítói együttműködési felületen.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Verziók és állapotok, ha használja a változáskezelést

Ha bekapcsolta a beszerzési rendelés számára a változáskezelést, a beszerzési rendelés egy jóváhagyási munkafolyamaton megy majd keresztül, hogy az állapota **Jóváhagyva** legyen. Ezt a folyamatot a szállító nem látja.  

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést, ha a változáskezelés be van kapcsolva. Ha be van kapcsolva a változáskezelés a beszerzési rendelésnél, a beszerzési rendelés verziója a jóváhagyás után lesz regisztrálva, nem pedig a megerősítés vagy a szállítónak való küldés után.

|                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                                                                                                    | **Állapot és verzió**                                                                                                                                                                                                                                                                                                                                                                      |
| A beszerzési rendelés eredeti verziója a Dynamics 365 for Operations rendszerben jön létre.                                      | Az állapota **Vázlat**.                                                                                                                                                                                                                                                                                                                                                                    |
| A beszerzési rendelést elküldik a jóváhagyási folyamatra. (Ez egy belső folyamat, amelyben a szállító nem vesz részt.) | Az állapot **Vázlat** állapotról **Ellenőrzés alatt** állapotra, majd **Jóváhagyva** állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. A jóváhagyott beszerzési rendelés verzióként van regisztrálva.                                                                                                                                                                                                                     |
| A beszerzési rendelést a rendszer elküldi a szállítónak.                                                                                  | Egy verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.                                                                                                                                                                                                                                                                       |
| Elvégezhet néhány módosítást, amit a szállító kér.                                                       | Az állapot újra **Vázlat** lesz                                                                                                                                                                                                                                                                                                                                                    |
| A beszerzési rendelést újra elküldik a jóváhagyási folyamatra.                                                            | Az állapot **Vázlat** állapotról **Ellenőrzés alatt** állapotra, majd **Jóváhagyva** állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. Úgy is konfigurálhatja a rendszert, hogy a változás esetén ne legyen szükséges az adott mező ismételt jóváhagyása. Ebben az esetben az állapot **Vázlat** lesz, majd automatikusan frissül **Jóváhagyva** állapotra. A jóváhagyott beszerzési rendelés új verzióként lesz regisztrálva. |
| A beszerzési rendelés új verzióját küldi el a szállítónak.                                                             | Egy új verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.                                                                                                                                                                                                                                                                   |
| A szállító jóváhagyja a beszerzési rendelés új verzióját.                                                                | Az állapot vagy automatikusan változik **Visszaigazolva** állapotra, vagy akkor, amikor megkapja a szállító válaszát, és megerősíti a beszerzési rendelést.                                                                                                                                                                                                                                                     |

## <a name="share-information-about-consignment-inventory"></a>Bizományosi készlettel kapcsolatos adatok megosztása
Bizományosi készlet használatakor a szállító a szállítói együttműködési felület segítségével megtekintheti az adatokat a következő lapokon:

-   **Bizományosi készletet használó beszerzési rendelések** – A bizományosi készletet használó beszerzési rendelések akkor jönnek létre, amikor az ön vállalata lesz a készlet tulajdonosa. Ezzel egy időben egy termékbevételezési bizonylat is feladásra kerül. A bizományosi beszerzési rendelések csak a **Bizományosi készletet használó beszerzési rendelések** lapon jelennek meg. Nem szerepelnek **Az összes visszaigazolt beszerzési rendelés** lapon a **Szállító együttműködés** modulban.
-   **Bizományosi készletből kapott termékek** – Ez a lap minden olyan tranzakciót listáz, amelynek során a termékek tulajdonjoga a szállítóról az ön vállalatára ruházódott át. A szállítók ezt az információt a vevői számlák kibocsátására használhatják.
-   **Aktuális bizományosi készlet** – Ez a lap megjeleníti a szállító tulajdonában levő aktuális bizományosi készletet, amely beérkezett a raktárába.





