---
title: "A külső szállítókkal történő szállítói együttműködés"
description: "Ez a témakör bemutatja, hogy a megbízott beszerzők hogyan tudják a Szállítói portált a külső szállítókkal való együttműködésre használni a beszerzési rendelés visszaigazolási folyamata alatt."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 9036b7f9863871915f9ad39d76bf027ae4c2f4bf
ms.openlocfilehash: aee8db8ddaeac135ed1f9d8b1b8a621609c6d358
ms.contentlocale: hu-hu
ms.lasthandoff: 10/05/2017

---

# <a name="vendor-collaboration-with-external-vendors"></a>A külső szállítókkal történő szállítói együttműködés

[!include[banner](../includes/banner.md)]


Ez a témakör bemutatja, hogy a megbízott beszerzők hogyan tudják a Szállítói portált a külső szállítókkal való együttműködésre használni a beszerzési rendelés visszaigazolási folyamata alatt.

A **Szállítói együttműködés** modul azokat a szállítókat célozza meg, akik nem rendelkeznek elektromos adatátviteli (EDI) integrációval a Microsoft Dynamics 365 for Finance and Operations rendszerhez. Lehetővé teszi a szállítók számára a beszerzési rendelés, a számla és a bizományosi készlet adatainak kezelését. Ez a témakör leírja, hogyan működhet együtt a szállítói együttműködési felületet használó külső szállítókkal a beszerzési rendelések és a bizományosi készlet kezelésében. Bemutatja, hogyan engedélyezheti egy adott szállítónak a szállítói együttműködés használatát, valamint hogyan definiálja azokat az információkat, amelyeket minden szállító lát egy beszerzési rendelésre történő válaszolás során. Ha többet szeretne megtudni arról, hogy milyen tevékenységeket végezhetnek a külső szállítók a szállítói együttműködési felületen, olvassa el a [Szállítói együttműködés vevőkkel](vendor-collaboration-work-customers-dynamics-365-operations.md) részt.  

Ha többet szeretne megtudni arról, hogyan használhatják a szállítók a szállítói együttműködést a számlázási folyamatokban, olvassa el a [Szállítói együttműködési számlázás munkaterület](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md) részt. Az új szállítói együttműködési felhasználók létrehozásával kapcsolatos tudnivalókat lásd: [Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md).

Ha többet szeretne megtudni arról, hogyan használhatják a szállítók a szállítói együttműködést a számlázási folyamatokban, olvassa el a [Szállítói együttműködési számlázás munkaterület](../../financials/accounts-payable/vendor-portal-invoicing-workspace.md) részt. 

Az új szállítói együttműködési felhasználók létrehozásával kapcsolatos tudnivalókat lásd: [Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md).

## <a name="define-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Határozza meg, milyen információ jelenjen meg a szállítóknak a beszerzési rendelésekre történő válaszolás során
Amikor a szállítók reagálnak egy beérkezett beszerzési rendelésre, egy üzenetpanel jelenik meg a számukra, amelyen meg kell erősíteniük, hogy elfogadják, elutasítják vagy módosításokkal fogadják el a beszerzési rendelést. Mivel a szállítónak az adott időpontban megjelenítendő adatok vállalatspecifikusak lehetnek, megadhatja a három megerősítési üzenet mindegyikén megjelenő szöveget. Például a szöveg tájékoztathatja a szállítót a folyamat következő lépéseivel vagy a szerződési feltételekkel kapcsolatban.  

A beszerzési rendelésen megjelenő szöveg meghatározásához:

1.  Nyissa meg az **Információ beszerzési rendelésekre válaszoló szállítóknak** lapot.
2.  A következő választípusok választhatók:
3.  Kattintson a **Szerkesztés** lehetőségre.
4.  Adja meg a szállítók megjelenítéséhez a kívánt adatokat az **Információs üzenet** mezőben.

Ha egynél több nyelven kell üzeneteket hozzáadni, hozzon létre külön üzeneteket, és adja meg külön hozzájuk a megfelelő nyelvkódokat. A szállítónak az üzenet az általa használt nyelven jelenik meg.

## <a name="set-the-vendor-collaboration-options-for-a-specific-vendor"></a>Szállítói együttműködési lehetőségek beállítása egy adott szállítóhoz
A szállítói együttműködés általános beállításait a Dynamics 365 for Finance and Operations rendszerben rendszergazda konfigurálja. A rendszergazda például meghatározza, hogy milyen biztonsági szerepkörök érhetők el az együttműködésben részt vevő szállítók számára. Van néhány olyan beállítás is, amelyek szállítókódként eltérőek lehetnek, ezeket be kell állítania:
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

A beszerzési rendeléseket a Finance and Operations rendszerben kell elkészíteni. Amikor a beszerzési rendelés állapota **Jóváhagyva**, a szállítónak a **Elküldés visszaigazolásra** művelet segítségével elküldheti a rendelést a **Beszerzési rendelés** lapon. A beszerzési rendelés állapota **Külső ellenőrzés alatt** státuszra változik. A beszerzési rendelés elküldése után a szállító megtekintheti azt a **Beszerzési rendelések ellenőrzésre** lapon a szállító együttműködési felületen. A szállító ezután elfogadhatja, elutasíthatja a rendelést,vagy módosításokat javasolhat hozzá. A szállító hozzászólások hozzáadásával oszthat meg olyan információkat, mint a beszerzési rendelés módosítása. Ha fel szeretné hívni a szállító figyelmét az új beszerzési rendelésre, elküldheti azt egy e-mailben is a nyomtatáskezelő rendszer segítségével.

### <a name="confirmation-and-acceptance-of-the-po-by-the-vendor"></a>A beszerzési rendelés szállító általi visszaigazolása és elfogadása

Amikor a szállító elfogadja a beszerzési rendelést, a beszerzési rendelés automatikusan vagy manuálisan erősíthető meg. Ez attól függ, hogy a **Szállító aktiválása** mező értéke **Aktív (beszerzési rendelés automatikus megerősítése)** vagy **Aktív (beszerzési rendelés nincs automatikusan megerősítve)** a szállító esetében.  

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
<td>A szállító <strong>elfogadja</strong> a rendelést. A Finance and Operations rendszer a beszerzési rendelések automatikus visszaigazolására van konfigurálva, abban az esetben, ha a szállító elfogadja a rendelést.</td>

<td>A rendelés állapota <strong>Visszaigazolva</strong> értékre frissül. Ha valami megakadályozza, hogy a rendelést frissítsék, a szállító válasza továbbra is <strong>Elfogadva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad. 

A szállítónak elküldött és **Külső ellenőrzés alatt** állapotú beszerzési rendelés frissítése a sorok szállítási dátumainak visszaigazolása révén történik. A frissítés egy új verziót indít el, amely automatikusan frissíthető **Megerősítve** állapotra. A beszerzési rendelés megerősítéskor megjelenik a szállítói együttműködési felületen.</td>
</tr>
<tr class="odd">
<td>A szállító <strong>elfogadja</strong> a rendelést. A Finance and Operations rendszer nincs a beszerzési rendelések automatikus visszaigazolására konfigurálva, abban az esetben, ha a szállító elfogadja a rendelést.</td>
<td>A szállító válasza <strong>Elfogadva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad.

A szállítónak elküldött és **Külső ellenőrzés alatt** állapotú beszerzési rendelés frissítése a sorok szállítási dátumainak visszaigazolása révén történik. A frissítés egy új verziót indít el, amely **Külső ellenőrzés alatt** állapotra áll át. Ezután manuálisan megerősítheti a beszerzési rendelést.</td>

</tr>
<tr class="even">
<td>A szállító <strong>elutasítja</strong> a rendelést.</td>
<td>A szállító válasza <strong>Elutasítva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad. Az elutasítás a szállítói indoklással kerül kézbesítésre.</td>
</tr>
<tr class="odd">
<td>Az a szállító, aki <strong>módosításokkal fogadja el a rendelést</strong>. A módosításokat a sor szintjén javasolja a program. Lehetőség van az egyes sorok elfogadására vagy elutasítására. Egyéb lehetséges módosítások a következők:
<ul>
<li>Módosíthatja a dátumokat vagy a mennyiségeket.</li>
<li>Feloszthatja a sorokat eltérő szállítási dátumok vagy mennyiségek alapján.</li>
<li>Helyettesíthet egy cikket.</li>
</ul>
Az árinformáció és a költségek a szállító által nem módosítható értékek. Ezekhez megjegyzések segítségével javasolhat módosításokat.</td>
<td>A szállító válasza <strong>Elfogadva módosításokkal</strong> értékű lesz, és a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad. Az állapotok megjelenítik, hogy milyen típusú módosításokat javasolt a szállító. A módosítások automatikus felhasználásáról lásd a következő részt a beszerzési rendelés frissítéséről, amikor a szállító módosításokat javasol. </td>
</tr>
</tbody>
</table>

Használhatja a **Beszerzési rendelés** **előkészítése** munkaterületet, hogy nyomon kövesse, mely beszerzési rendelésekre válaszolt a szállító. A munkaterület két listát tartalmaz, amelyek felsorolják a **Külső ellenőrzés alatt** állapotú beszerzési rendeléseket:

-   Külső ellenőrzés alatt, intézkedést igényel.
-   Külső ellenőrzés alatt, a szállító válaszára várva.

### <a name="changing-a-po"></a>Beszerzési rendelés módosítása

Ha módosítani szeretne egy beszerzési rendelést, amire már korábban reagáltak, új beszerzési rendelést kell elküldenie a szállítónak. Az új beszerzési rendelés rendelkezni fog egy verziószám-utótaggal, ami azt jelzi, hogy ez a korábban közölt beszerzési rendelés módosított változata. A **Beszerzési rendelés szállítói visszaigazolásának előzményei** lap segítségével ön és szállítói nyomon követhetik az egyes rendelések előzményeit. A beszerzési rendelés már korábban jóváhagyott verziója a jóváhagyott beszerzési rendelések listáján marad addig, amíg egy új beszerzési rendelés nem lesz jóváhagyva.

### <a name="cancelling-a-po"></a>Beszerzési rendelés visszavonása

A beszerzési rendelés visszavonásakor az állapot **Jóváhagyva** állapotú lesz. Vissza kell küldenie a beszerzési rendelést a szállítónak, hogy a szállító megerősíthesse vagy elutasíthassa az érvénytelenítést. Az érvénytelenítés jóváhagyása után a beszerzési rendelés a szállító jóváhagyott beszerzési rendeléseinek listáján **Érvénytelenítve** értékkel fog megjelenni.

### <a name="adding-attachments-to-a-po"></a>Mellékletek csatolása beszerzési rendeléshez

A dokumentumkezelő rendszer segítségével fájlokat, képeket és megjegyzéseket csatolhat a beszerzési megrendeléshez. A **Külső** típusú mellékleteket a szállító a beszerzési rendelés elküldése után tudja megtekinteni.

## <a name="update-the-po-when-a-vendor-suggests-changes"></a>A beszerzési rendelés frissítése, ha a szállító módosításokat javasol
Ha a szállító válaszolt a beszerzési rendelésre és módosításokat javasolt, a következő lépés a válasz feldolgozása.
A **Beszerzési rendelés előkészítése munkaterületen** a Külső ellenőrzés alatt intézkedést igényel listában azonosíthatja azt a beszerzési rendelést, amelyet a szállító módosításokkal fogadott el. A Külső ellenőrzés alatt intézkedést igényel listán megtekintheti a szállító válaszát is. A válaszban a szállító a következő adatokat módosíthatja a fejlécben.
 
-   Szállítói bizonylat hivatkozása
-   Szállítás módja
-   Szállítási feltételek
-   Visszaigazolt szállítási dátum

A szállító megjegyzést vagy mellékletet is fűzhet a válaszához

A sorokban a szállító módosíthatja a mennyiséget és a szállítási dátumokat, jegyzeteket és mellékleteket fűzhet hozzá, elutasíthat egy sort, lecserélhet egy sort egy másik, szövegként beírt termékkel, valamint egy sort több kiszállításra oszthat fel. Attól függően, hogy milyen módosításokat javasol a szállító, a sor állapota eltérő lesz:
    
-   **Elfogadva módosításokkal**
-   **Elutasítva**
-   **Helyettesített** Ebben az esetben egy újabb sor jelenik meg, amelynek állapota **Helyettesítő**.
-   **Visszaigazolva** Felosztás ütemezésbe Ebben az esetben további sorok jelennek meg, amelyek állapota **Sorok ütemezése**.

Ha a sorban nincs változás, a sor állapota **Elfogadva**.

A válaszon láthatja az előzőleg említett sorállapotokat, amelyek jelzik a szállító által végrehajtott módosítások típusát. Ezenkívül minden módosult mező félkövér betűkkel jelenik meg a módosítások könnyebb azonosítása érdekében.

A beszerzési rendelést a **Beszerzési rendelés frissítésének feldolgozása** műveletre kattintva frissítve a válaszban vagy egyszerre egy sorban. A fejléc és a sorok jelölője, **Beszerzési rendelés frissítése feldolgozva?** segítségével megtekintheti, hogy a rendszer feldolgozta-e a fejlécet vagy a sorokat a beszerzési rendelésnek a válaszból eredő esetleges módosításokkal történő frissítése érdekében. A **Beszerzési rendelés frissítésének feldolgozása** folyamatot egyszerre csak fejlécenként vagy soronként futtathatja.

Nem minden javasolt módosítást lehet frissíteni a beszerzési rendelésen. A beszerzési rendelésen csak a fejlécben, illetve a sorokban levő dátum- és mennyiségfrissítéseket lehet automatikusan frissíteni. Egyéb módosításokhoz manuálisan kell frissítenie a beszerzési rendelést. Ebben az esetben a **Beszerzési rendelés frissítése feldolgozva?** mutató a **Manuális frissítés** értéket jeleníti meg. A manuálisan kezelendő módosításra példa, ha a szállító azt javasolja, hogy egy sort ütemezésre osszanak fel.

Az **Elfogadva** állapotú sor visszaigazolt szállítási dátummal rendelkezik, amely frissül a beszerzési rendelésen a **Beszerzési rendelés frissítésének feldolgozása** végrehajtásakor. A megjegyzések és mellékletek nem kerülnek át automatikusan az aktuális beszerzési rendelésre. Vegye figyelembe, hogy az aktuális beszerzési rendelés frissítésekor a **Beszerzési rendelés frissítésének feldolgozása** művelet révén a beszerzési rendelési sorokban a kereskedelmi megállapodásokat nem értékeli újra a rendszer.


## <a name="po-statuses-and-versions"></a>A beszerzési rendelés állapota és verziói
Ez a szakasz leírja a beszerzési rendelés különféle állapotait a megerősítés időpontjáig. Azt is leírja, hogy a beszerzési rendelés új verziói milyen időpontban érhetőek el a szállító számára. A viselkedés attól függően változik, hogy használja-e a változáskezelést a beszerzési rendelésekhez. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Verziók és állapotok, ha nem használja a változáskezelést

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                                                               | **Állapot és verzió**                                                                                                                                       |
| A beszerzési rendelés eredeti verziója a Finance and Operations rendszerben jön létre. | Az állapota **Jóváhagyva**.                                                                                                                                  |
| A beszerzési rendelést a rendszer elküldi a szállítónak.                                            | Egy verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.                                          |
| A szállító egy **Elfogadva módosításokkal** választ küld.                  | Az állapot továbbra is **Külső ellenőrzés alatt**.                                                                                                                  |
| Elvégezhet néhány módosítást, amit a szállító kér.                  | Az állapot **Jóváhagyva** állapotra módosul.                                                                                                                        |
| A beszerzési rendelés új verzióját küldi el a szállítónak.                        | Egy új verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.                                      |
| A szállító elfogadja a beszerzési rendelés új verzióját.                            | Az állapot továbbra is **Külső ellenőrzés alatt** lesz kivéve, ha szállító fiókjának beállítása automatikusan **Megerősítve** állapotra vált a beszerzési rendelés elfogadásakor. |


A szállítóknak nem kell jóváhagyniuk a beszerzési rendelést a szállítói együttműködési felületen. Küldhetnek email üzenetet, illetve egyéb csatornákon keresztül is kommunikálhatják a beszerzési rendelés elfogadását. Ezután a rendelést manuálisan is jóváhagyhatja a Finance and Operations rendszerben. Ebben az esetben egy figyelmeztetést fog kapni, ami jelzi, hogy a rendelés jóvá lesz hagyva annak ellenére is, hogy nincs válasz a szállítótól. A beszerzési rendelés ezután megjelenik a jóváhagyási előzményekben úgy, mint egy megnyitott rendelés, amelyre nem érkezett válasz. A szállító többé nem tudja majd se elfogadni, se visszautasítani a beszerzési rendelést.  


>[!NOTE]
>A Dynamics 365 for Finance and Operations rendszerben mindig a beszerzési rendelés legutolsó verziója érhető el a további folyamatok számára, még akkor is, ha ez a verzió nincs még regisztrálva a szállítói együttműködési felületen.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Verziók és állapotok, ha használja a változáskezelést

Ha bekapcsolta a beszerzési rendelés számára a változáskezelést, a beszerzési rendelés egy jóváhagyási munkafolyamaton megy majd keresztül, hogy az állapota **Jóváhagyva** legyen. Ezt a folyamatot a szállító nem látja.  

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést, ha a változáskezelés be van kapcsolva. Ha be van kapcsolva a változáskezelés a beszerzési rendelésnél, a beszerzési rendelés verziója a jóváhagyás után lesz regisztrálva, nem pedig a megerősítés vagy a szállítónak való küldés után.

|                                                                          |                                                                                                                                                              |
|--------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Művelet**                                                               | **Állapot és verzió**                                                                                                                                       |
| A beszerzési rendelés eredeti verziója a Finance and Operations rendszerben jön létre.      | Az állapota **Vázlat**.  |
| A beszerzési rendelést elküldik a jóváhagyási folyamatra. (A jóváhagyás folyamata egy belső folyamat, amelyben a szállító nem vesz részt.)                                                           | Az állapot **Vázlat** állapotról **Ellenőrzés alatt** állapotra, majd **Jóváhagyva** állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. A jóváhagyott beszerzési rendelés verzióként van regisztrálva.           | 
| A beszerzési rendelést a rendszer elküldi a szállítónak.                                                            | Egy verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.      |
| Megteszi a szállító által igényelt módosításokat, kézzel vagy a válaszon levő művelet segítségével a beszerzési rendelés frissítése érdekében.                                                            | Az állapot újra **Vázlat** lesz     |
|A beszerzési rendelést újra elküldik a jóváhagyási folyamatra.                                                |  Az állapot **Vázlat** állapotról **Ellenőrzés alatt** állapotra, majd **Jóváhagyva** állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. Úgy is konfigurálhatja a rendszert, hogy a változás esetén ne legyen szükséges az adott mező ismételt jóváhagyása. Ebben az esetben az állapot **Vázlat** lesz, majd automatikusan frissül **Jóváhagyva** állapotra. A jóváhagyott beszerzési rendelés új verzióként lesz regisztrálva.                                         |
|A beszerzési rendelés új verzióját küldi el a szállítónak.                                                |  Egy új verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul.                                         |
|A szállító jóváhagyja a beszerzési rendelés új verzióját.                                                |  Az állapot vagy automatikusan változik **Visszaigazolva** állapotra, vagy akkor, amikor megkapja a szállító válaszát, és megerősíti a beszerzési rendelést. |

## <a name="share-information-about-consignment-inventory"></a>Bizományosi készlettel kapcsolatos adatok megosztása
Bizományosi készlet használatakor a szállító a szállítói együttműködési felület segítségével megtekintheti az adatokat a következő lapokon:

-   **Bizományosi készletet használó beszerzési rendelések** – A bizományosi készletet használó beszerzési rendelések akkor jönnek létre, amikor az ön vállalata lesz a készlet tulajdonosa. Ezzel egy időben egy termékbevételezési bizonylat is feladásra kerül. A bizományosi beszerzési rendelések csak a **Bizományosi készletet használó beszerzési rendelések** lapon jelennek meg. Nem szerepelnek **Az összes visszaigazolt beszerzési rendelés** lapon a **Szállító együttműködés** modulban.
-   **Bizományosi készletből kapott termékek** – Ez a lap minden olyan tranzakciót listáz, amelynek során a termékek tulajdonjoga a szállítóról az ön vállalatára ruházódott át. A szállítók ezt az információt a vevői számlák kibocsátására használhatják.
-   **Aktuális bizományosi készlet** – Ez a lap megjeleníti a szállító tulajdonában levő aktuális bizományosi készletet, amely beérkezett a raktárába.





