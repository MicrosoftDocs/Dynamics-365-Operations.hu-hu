---
title: A külső szállítókkal történő szállítói együttműködés
description: Ez a témakör azt magyarázza el, hogy a megbízott beszerzők hogyan tudják a Szállítói portált a külső szállítókkal való együttműködésre használni a beszerzési rendelés visszaigazolási folyamata alatt.
author: Henrikan
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, VendVendorPortalInvoicePart, PurchaseOrderResponseActionRemarks, PurchVendorPortalAllResponse, PurchOrderInExternalReview, PurchVendorPortalPendingResponsesPart, PurchVendorPortalResponses, PurchVendorPortalConfirmedOpenOrdersPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 221264
ms.assetid: dde49743-1541-4353-a030-63ca3069cd7d
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3b679f8daed1e09c832a5d138473cccba03552f6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576976"
---
# <a name="vendor-collaboration-with-external-vendors"></a>A külső szállítókkal történő szállítói együttműködés

[!include [banner](../includes/banner.md)]

A **Szállítói együttműködés** modul azokat a szállítókat célozza meg, akik nem rendelkeznek elektromos adatátviteli (EDI) integrációval a Microsoft Dynamics 365 Supply Chain Management rendszerhez. Segítségével a szállítók beszerzési rendelésekkel, számlákkal, bizományosi készlet adataival és ajánlatkérésekel dolgozhatnak, valamint hozzáférhetnek a szállítók alapadatainak részeihez. Ez a témakör bemutatja, hogyan működhet együtt a szállítói együttműködési felületet használó külső szállítókkal a beszerzési rendelések és a bizományosi készlet kezelésében. Bemutatja továbbá, hogyan engedélyezheti egy adott szállítónak a szállítói együttműködés használatát, valamint hogyan definiálja azokat az információkat, amelyeket minden szállító lát egy beszerzési rendelésre történő válaszolás során.

Ha többet szeretne megtudni arról, hogy milyen tevékenységeket végezhetnek a külső szállítók a szállítói együttműködési felületen, olvassa el a [Szállítói együttműködés vevőkkel](vendor-collaboration-work-customers-dynamics-365-operations.md) részt.

> [!NOTE]
> Az ebben a szállítói együttműködésről szóló témakörben található információk csak a Supply Chain Management jelenlegi verziójára érvényesek. A Microsoft Dynamics AX 7.0 (2016. február) és a Microsoft Dynamics AX 7.0.1 (2016. május) alkalmazásverziókban a **Szállítói portál** modul segítségével működhet együtt a szállítókkal. A **Szállítói portál** modullal kapcsolatos további tudnivalókat lásd: [Együttműködés a szállítókkal a Szállítói portálon keresztül](collaborate-vendors-vendor-portal.md).

Ha többet szeretne megtudni arról, hogyan használhatják a szállítók a szállítói együttműködést a számlázási folyamatokban, olvassa el a [Szállítói együttműködési számlázás munkaterület](../../finance/accounts-payable/vendor-portal-invoicing-workspace.md) részt. Az új szállítói együttműködési felhasználók létrehozásával kapcsolatos tudnivalókat lásd: [Szállítói együttműködés felhasználóinak kezelése](manage-vendor-collaboration-users.md).

## <a name="defining-the-information-that-is-shown-to-vendors-when-they-respond-to-pos"></a>Határozza meg, milyen információ jelenjen meg a szállítóknak a beszerzési rendelésekre történő válaszolás során

Amikor a szállítók reagálnak egy beérkezett beszerzési rendelésre, a három üzenetpanel egyike jelenik meg a számukra, amelyen meg kell erősíteniük, hogy elfogadják, elutasítják vagy módosításokkal fogadják el a beszerzési rendelést. Mivel a szállítónak az adott időpontban megjelenítendő adatok vállalatspecifikusak lehetnek, megadhatja a megerősítési üzenetek mindegyikén megjelenő szöveget. Például a szöveg tájékoztathatja a szállítót a folyamat következő lépéseivel vagy a szerződési feltételekkel kapcsolatban.

A beszerzési rendelésen megjelenő szöveg meghatározásához kövesse az alábbi lépéseket:

1. Az **Információ beszerzési rendelésekre válaszoló szállítóknak** oldalon válassza ki a választípust, és válassza a **Szerkesztés** lehetőséget.
2. Az **Információs üzenet** mezőben adja meg az információkat, amelyeket meg szeretne jeleníteni a szállítók számára az üzenetek mezőjében.

Ha egynél több nyelven kell üzeneteket hozzáadni, hozzon létre külön üzeneteket, és adja meg külön hozzájuk a megfelelő nyelvkódokat. Az egyes szállítóknak az üzenet az általuk használt nyelven jelenik meg.

## <a name="setting-the-vendor-collaboration-options-for-a-specific-vendor"></a>Szállítói együttműködési lehetőségek beállítása egy adott szállítóhoz

A rendszergazda konfigurálja a szállítói együttműködés általános beállításait, például a biztonsági szerepköröket, amelyek elérhetőek az összes Önnel együttműködő szállító számára. Vannak azonban olyan beállítások is, amelyek szállítói fiókonként eltérőek. A következő beállításokat kell konfigurálnia.

- Engedélyezze a szállítói együttműködést.
- Adja meg, hogy a szállító láthatja-e az árakkal kapcsolatos adatokat.

### <a name="enabling-vendor-collaboration"></a>Engedélyezze a szállítói együttműködést

Mielőtt felhasználói fiókokat hozna létre egy külső szállító számára, konfigurálnia kell a szállítókódot a szállítói együttműködés engedélyezése érdekében. Használja az **Együttműködés aktiválása** mezőt az **Általános** lapon, a **Szállítók** oldalon. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Aktív (beszerzési rendelés automatikus megerősítése)**– a rendszer automatikusan megerősíti a beszerzési rendeléseket, amikor a szállító módosítások nélkül fogadja el azokat.
- **Aktív (beszerzési rendelés nincs automatikusan megerősítve)**– A beszerzési rendeléseket szervezetének manuálisan kell jóváhagynia, miután a szállító elfogadta őket.

### <a name="specifying-whether-the-vendor-should-see-price-information"></a>Annak megadása, hogy a szállító láthatja-e az árakkal kapcsolatos adatokat

Ahhoz, hogy megossza a beszerzési rendelések árinformációit a szállítói együttműködési felületen keresztül, a **Beszerzési rendelés árai/összege** lehetőséget a **Beszerzési rendelés alapértelmezései** lapon a szállítói fiókra vonatkozóan **Igen** értékre kell állítani. Az áradatok között szerepel az egységár, az engedmények és a költségek.

## <a name="working-with-pos-when-vendor-collaboration-is-used"></a>Beszerzési rendelések kezelése szállítói együttműködési használata esetén

### <a name="sending-a-po-to-a-vendor"></a>Beszerzési rendelés küldése egy szállítónak

A beszerzési rendeléseket a Supply Chain Management szolgáltatásban hozzák létre. Amikor a beszerzési rendelés állapota **Jóváhagyva**, a szállítónak a **Elküldés visszaigazolásra** művelet használatával elküldheti a rendelést a **Beszerzési rendelés** lapon. A beszerzési rendelés állapota ekkor **Külső ellenőrzés alatt** státuszra változik. A beszerzési rendelés elküldése után a szállító megtekintheti azt a **Beszerzési rendelések ellenőrzésre** lapon a szállító együttműködési felületen. A szállító ezután elfogadhatja, elutasíthatja a beszerzési rendelést,vagy módosításokat javasolhat hozzá. A szállító hozzászólások hozzáadásával oszthat meg olyan információkat, mint a beszerzési rendelés módosítása. Ha fel szeretné hívni a szállító figyelmét az új beszerzési rendelésre, elküldheti azt egy e-mailben is a nyomtatáskezelő rendszer segítségével.

### <a name="confirmation-and-acceptance-of-a-po-by-a-vendor"></a>A beszerzési rendelés szállító általi visszaigazolása és elfogadása

Miután egy szállító elfogadja a beszerzési rendelést, a beszerzési rendelést automatikusan meg lehet erősíteni, illetve esetleg manuálisan kell megerősíteni. A viselkedés attól függ, hogy a **Szállító aktiválása** mező értéke **Aktív (beszerzési rendelés automatikus megerősítése)** vagy **Aktív (beszerzési rendelés nincs automatikusan megerősítve)** a szállító esetében.

Az alábbi táblázat bemutatja a tipikus információcserét attól függően, hogy hogyan reagál a szállító, amikor egy beszerzési rendelés visszaigazolást küld neki.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Szállítói válasz</th>
<th>Eredmény</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>A szállító <strong>elfogadja</strong> a rendelést, és a Supply Chain Management automatikusan úgy van konfigurálva, hogy automatikusan megerősítse azokat a beszerzési rendeléseket, amelyeket a szállító elfogad.</td>
<td>A rendelés állapota <strong>Visszaigazolva</strong> értékre frissül. Ha valami megakadályozza, hogy a rendelést frissítsék, a szállító válasza továbbra is <strong>Elfogadva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés</strong> alatt állapotú marad. 

A szállítónak elküldött és <strong>Külső ellenőrzés alatt</strong> állapotú beszerzési rendelés frissítése a sorok szállítási dátumainak visszaigazolása révén történik. Ez a frissítés egy új verziót indít el, amely automatikusan <strong>Megerősítve</strong> állapotra állítható. A beszerzési rendelés megerősítéskor megjelenik a szállítói együttműködési felületen.</td>
</tr>
<tr class="odd">
<td>A szállító <strong>elfogadja</strong> a rendelést, de a Supply Chain Management nincs úgy konfigurálva, hogy automatikusan megerősítse azokat a beszerzési rendeléseket, amelyeket a szállító elfogad.</td>
<td>A szállító válasza <strong>Elfogadva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad.

A szállítónak elküldött és <strong>Külső ellenőrzés alatt</strong> állapotú beszerzési rendelés frissítése a sorok szállítási dátumainak visszaigazolása révén történik. Ez a frissítés egy új verziót indít el, amely automatikusan <strong>Külső ellenőrzés alatt</strong> állapotra állítható. Ezt követően manuálisan erősítheti meg a beszerzési rendelést.</td>
</tr>
<tr class="even">
<td>A szállító <strong>elutasítja</strong> a rendelést.</td>
<td>A szállító válasza <strong>Elutasítva</strong> értékű lesz, de a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad. Az elutasítás az indoklással kerül kézbesítésre.</td>
</tr>
<tr class="odd">
<td>Az a szállító, aki <strong>módosításokkal</strong> <strong>fogadja el</strong> a rendelést. A módosításokat a sor szintjén javasolja a program. A szállító elfogadhatja vagy elutasíthatja az egyes sorokat. Az alábbiakban néhány további olyan módosítást láthat, melyeket a szállító javasolhat:
<ul>
<li>Módosíthatja a dátumokat vagy a mennyiségeket.</li>
<li>Feloszthatja a sorokat eltérő szállítási dátumok vagy mennyiségek alapján.</li>
<li>Helyettesíthet egy cikket.</li>
</ul>
A szállító nem módosíthatja az árinformációkat és a költségeket. Azonban a szállító felajánlhatja ezeket a módosításokat megjegyzések segítségével.</td>
<td>A szállító válasza <strong>Elfogadva módosításokkal</strong> értékű lesz, és a beszerzési rendelés <strong>Külső ellenőrzés alatt</strong> állapotú marad. Az állapotok megjelenítik, hogy milyen típusú módosításokat javasolt a szállító. A módosítások automatikus felhasználásáról lásd a következő, „A beszerzési rendelés frissítése, ha a szállító módosításokat javasol” című részt a beszerzési rendelés frissítéséről, amikor a szállító módosításokat javasol. </td>
</tr>
</tbody>
</table>

Használhatja a **Beszerzési rendelés előkészítése** munkaterületet, hogy nyomon kövesse, mely beszerzési rendelésekre válaszolt a szállító. A munkaterület két listát tartalmaz, amelyek felsorolják a **Külső ellenőrzés alatt** állapottal rendelkező beszerzési rendeléseket:

- Külső ellenőrzés alatt intézkedést igényel
- Külső ellenőrzés alatt, a szállító válaszára várva

### <a name="changing-a-po"></a>Beszerzési rendelés módosítása

Ha módosítani szeretne egy beszerzési rendelést, amire egy szállító már korábban reagált, új beszerzési rendelést kell elküldenie a szállítónak. Az új beszerzési rendelés rendelkezni fog egy verziószám-utótaggal, ami azt jelzi, hogy ez a korábban beküldött beszerzési rendelés módosított változata. A **Beszerzési rendelés szállítói visszaigazolásának előzményei** lap segítségével ön és szállítói nyomon követhetik az egyes rendelések előzményeit. A beszerzési rendelés már korábban jóváhagyott verziója a jóváhagyott beszerzési rendelések listáján marad addig, amíg egy új beszerzési rendelés nem lesz jóváhagyva.

### <a name="canceling-a-po"></a>Beszerzési rendelés visszavonása

A beszerzési rendelés visszavonásakor az állapot **Jóváhagyva** állapotú lesz. Vissza kell küldenie a beszerzési rendelést a szállítónak, hogy a szállító megerősíthesse vagy elutasíthassa az érvénytelenítést. Az érvénytelenítés jóváhagyása után a beszerzési rendelés a jóváhagyott beszerzési rendelések listáján **Érvénytelenítve** értékkel fog megjelenni.

### <a name="adding-attachments-to-a-po"></a>Mellékletek csatolása beszerzési rendeléshez

A dokumentumkezelő rendszer segítségével fájlokat, képeket és megjegyzéseket csatolhat a beszerzési megrendeléshez. A **Külső** típusú mellékleteket a szállító a beszerzési rendelés elküldése után tudja megtekinteni.

## <a name="updating-a-po-when-a-vendor-suggests-changes"></a>A beszerzési rendelés frissítése, ha a szállító módosításokat javasol

Ha egy szállító válaszolt a beszerzési rendelésre és módosításokat javasolt, a következő lépés a válasz feldolgozása.

A **Beszerzési rendelés előkészítése** munkaterületen a **Külső ellenőrzés alatt intézkedést igényel** listában azonosíthatja azt a beszerzési rendelést, amelyet a szállító módosításokkal fogadott el. Ebből a listából a szállítói válasz értékére is átnavigálhat.

A válaszban a szállító a következő adatokat módosíthatja a fejlécben:
 
- Szállítói bizonylat hivatkozása
- Szállítás módja
- Szállítási feltételek
- Visszaigazolt szállítási dátum

A szállító megjegyzést vagy mellékletet is fűzhet a válaszához.

A sorokban a szállító módosíthatja a mennyiséget és a szállítási dátumokat, jegyzeteket és mellékleteket fűzhet hozzá, elutasíthat egy sort, lecserélhet egy sort egy másik, szövegként megadott termékkel, valamint egy sort több kiszállításra oszthat fel. A sor állapota attól függően változik, hogy a szállító milyen változtatásokat javasolt:
    
- **Elfogadva módosításokkal**
- **Elutasítva**
- **Helyettesített** – Ebben az esetben egy újabb sor jelenik meg, amelynek állapota **Helyettesítő**.
- **Visszaigazolva**
- **Felosztás ütemezésbe** – Ebben az esetben további sorok jelennek meg, amelyek állapota **Sorok ütemezése**.

Ha a sorban nincs változás, a sor állapota **Elfogadva**.

A válaszon láthatja a sorállapotokat, amelyek jelzik a szállító által végrehajtott módosítások típusát. Ezenkívül minden módosított mező félkövér betűkkel jelenik meg a módosítások könnyebb azonosítása érdekében.

A beszerzési rendelést úgy frissítheti, hogy kiválasztja a **Beszerzési rendelés frissítésének feldolgozása** műveletet a válaszban vagy egyszerre egy sorban. A fejléc és a sorok jelölője, **Beszerzési rendelés frissítése feldolgozva?** mező segítségével megtekintheti, hogy a rendszer feldolgozta-e a fejlécet vagy a sorokat a beszerzési rendelésnek a válaszból eredő esetleges módosításokkal történő frissítése érdekében. A **Beszerzési rendelés frissítésének feldolgozása** műveletet egyszerre csak fejlécenként vagy soronként futtathatja.

Nem minden javasolt módosítást lehet frissíteni a beszerzési rendelésen. A beszerzési rendelésen csak a fejlécben, illetve a sorokban lévő dátum- és mennyiségfrissítéseket lehet automatikusan frissíteni. Egyéb módosításokhoz manuálisan kell frissítenie a beszerzési rendelést. Ebben az esetben a **Beszerzési rendelés frissítése feldolgozva?** mező a **Manuális frissítés** értéket jeleníti meg. Ha például egy szállító azt javasolja, hogy egy sort ütemezésre lehet felosztani, akkor ezt a módosítást manuálisan kell végrehajtani.

Minden **Elfogadott** állapotú sor rendelkezni fog visszaigazolt szállítási dátummal. Amikor futtatja a **Beszerzési rendelés frissítésének feldolgozása** műveletet, ez a dátum frissül a beszerzési rendelésen. A megjegyzések és mellékletek nem kerülnek át automatikusan az aktuális beszerzési rendelésre. Továbbá a **Beszerzési rendelés frissítésének feldolgozása** művelet frissítésekor a beszerzési rendelési sorokban a kereskedelmi megállapodásokat nem értékeli újra a rendszer.

## <a name="po-statuses-and-versions"></a>A beszerzési rendelés állapota és verziói

Ez a szakasz leírja a beszerzési rendelés különféle állapotait a megerősítés időpontjáig. Azt is leírja, hogy a beszerzési rendelés új verziói mikor érhetők el a szállító számára. A viselkedés attól függően változik, hogy használja-e a változáskezelést a beszerzési rendelésekhez. 

### <a name="versions-and-statuses-if-you-dont-use-change-management"></a>Verziók és állapotok, ha nem használja a változáskezelést

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést.

| Művelet | Állapot és verzió |
|--------|--------------------|
| A beszerzési rendelés eredeti verziója a Supply Chain Management rendszerben jön létre. | Az állapota **Jóváhagyva**. |
| A beszerzési rendelést a rendszer elküldi a szállítónak. | Egy verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul. |
| A szállító egy **Elfogadva módosításokkal** választ küld. | Az állapot továbbra is **Külső ellenőrzés alatt**. |
| Elvégezhet néhány módosítást, amelyeket a szállító kér. | Az állapot **Jóváhagyva** állapotra módosul. |
| A beszerzési rendelés új verzióját küldi el a szállítónak. | Egy új verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul. |
| A szállító elfogadja a beszerzési rendelés új verzióját. | Az állapot továbbra is **Külső ellenőrzés alatt** lesz kivéve, ha a szállító fiókjának beállítása automatikusan **Megerősítve** állapotra vált a beszerzési rendelés elfogadásakor. |

A szállítóknak nem kell jóváhagyniuk a beszerzési rendelést a szállítói együttműködési felületen. Küldhetnek e-mailt, illetve egyéb csatornákon keresztül is kommunikálhatják a beszerzési rendelés elfogadását. Ezt követően manuálisan erősítheti meg a rendelést. Ebben az esetben figyelmeztetést kap, ami jelzi, hogy a rendelés jóvá lesz hagyva annak ellenére is, hogy nincs válasz a szállítótól. A beszerzési rendelés ezután megjelenik a jóváhagyási előzményekben úgy, mint egy megnyitott rendelés, amelyre nem érkezett válasz. Ekkor a szállító többé nem tudja majd se elfogadni, se visszautasítani a beszerzési rendelést.

> [!NOTE]
> A Supply Chain Management rendszerben mindig a beszerzési rendelés legutolsó verziója érhető el a további folyamatok számára, még akkor is, ha ez a verzió nincs még regisztrálva a szállítói együttműködési felületen.

### <a name="versions-and-statuses-if-you-use-change-management"></a>Verziók és állapotok, ha használja a változáskezelést

Ha bekapcsolta a beszerzési rendelések számára a változáskezelést, a beszerzési rendelések egy jóváhagyási munkafolyamaton mennek keresztül, hogy az állapotuk **Jóváhagyva** legyen. Ezt a folyamatot a szállító nem látja.

Az alábbi táblázat szemlélteti azokat az állapot- és verzióváltozásokat, amik érinthetnek egy beszerzési rendelést, ha a változáskezelés be van kapcsolva. Ha be van kapcsolva a változáskezelés a beszerzési rendelésnél, a beszerzési rendelés egy verziója a jóváhagyás után lesz regisztrálva, nem pedig a megerősítés vagy a szállítónak való küldés után.

| Művelet | Állapot és verzió |
|--------|--------------------|
| A beszerzési rendelés eredeti verziója a Supply Chain Management rendszerben jön létre. | Az állapota **Vázlat**. |
| A beszerzési rendelést elküldik a jóváhagyási folyamatra. (A jóváhagyás folyamata egy belső folyamat, amelyben a szállító nem vesz részt.) | Az állapot **Vázlat** állapotról **Ellenőrzés alatt** állapotra, majd **Jóváhagyva** állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. A jóváhagyott beszerzési rendelés verzióként van regisztrálva. | 
| A beszerzési rendelést a rendszer elküldi a szállítónak. | Egy verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul. |
| Megteszi a szállító által igényelt módosításokat, kézzel vagy a válaszon lévő **Beszerzési rendelés frissítésének feldolgozása** művelet segítségével a beszerzési rendelés frissítése érdekében. | Az állapot újra **Vázlat** lesz |
| A beszerzési rendelést újra elküldik a jóváhagyási folyamatra. | Az állapot **Vázlat** állapotról **Ellenőrzés alatt** állapotra, majd **Jóváhagyva** állapotra módosul, ha a beszerzési rendelés nem kerül elutasításra a jóváhagyási folyamat alatt. Úgy is konfigurálhatja a rendszert, hogy a változás esetén ne legyen szükséges az adott mező ismételt jóváhagyása. Ebben az esetben az állapot **Vázlat** lesz, majd automatikusan frissül **Jóváhagyva** állapotra. A jóváhagyott beszerzési rendelés új verzióként lesz regisztrálva. |
| A beszerzési rendelés új verzióját küldi el a szállítónak. | Egy új verziót regisztrálnak a szállítói együttműködési felületen, és a rendelés állapota **Külső ellenőrzés alatt** állapotra módosul. |
| A szállító jóváhagyja a beszerzési rendelés új verzióját. | Az állapot vagy automatikusan változik **Visszaigazolva** állapotra, vagy akkor, amikor megkapja a szállító válaszát, és megerősíti a beszerzési rendelést. |

## <a name="sharing-information-about-consignment-inventory"></a>Bizományosi készlettel kapcsolatos adatok megosztása

Bizományosi készlet használatakor a szállító a szállítói együttműködési felület segítségével megtekintheti az adatokat a következő lapokon:

- **Bizományosi készletet használó beszerzési rendelések** – A bizományosi készletet használó beszerzési rendelések olyankor jönnek létre, amikor az ön vállalata lesz a készlet tulajdonosa. Ezzel egy időben egy termékbevételezési bizonylat is feladásra kerül. A bizományosi beszerzési rendelések csak a **Bizományosi készletet használó beszerzési rendelések** lapon jelennek meg. Nem szerepelnek **Az összes visszaigazolt beszerzési rendelés** lapon a **Szállító együttműködés** modulban.
- **Bizományosi készletből kapott termékek** – Ez a lap minden olyan tranzakciót listáz, amelynek során a termékek tulajdonjoga a szállítóról az ön vállalatára ruházódott át. A szállítók ezt az információt a vevői számlák kibocsátására használhatják.
- **Aktuális bizományosi készlet** – Ez a lap megjeleníti a szállító tulajdonában levő aktuális bizományosi készletet, amely beérkezett a raktárába.

## <a name="working-with-rfqs-when-you-use-vendor-collaboration"></a>Ajánlatkérések kezelése szállítói együttműködési használata esetén

Ez a szakasz a vevők és szállítók közötti interakciókat írja le az ajánlatkérési folyamat során. Azt is bemutatja, hogyan tájékoztatja a rendszer a szállítókat az információkról. Ha alapszintű áttekintést szeretne az ajánlatkérési folyamat támogatásáról, lásd a következő részt: [Ajánlatkérések (RFQ-k) áttekintése](request-quotations.md).

### <a name="alternates-attachments-amendments-and-returns"></a>Alternatívák, mellékletek, módosítások és visszáruk

- **Alternatívák** – az ajánlatkérési eset fejlécében megadhatja, hogy megengedettek-e az alternatívák a katalóguson kívüli cikkeknél. Ha az alternatívák engedélyezve vannak, a szállítók alternatívasort adhatnak minden egyes kért sorukhoz.
- **Mellékletek** – a mellékletek felvehetők a fejléc szintjén és a sor szintjén is az ajánlatkérési esetnél. A mellékletek belsőnek és külsőnek is minősíthetők. A belső mellékletek csak a vevő oldalán tekinthetők meg, míg a szállítók küldés után megtekinthetik a külső mellékleteket.

    A szállítók mellékleteket is csatolhatnak az ajánlatra adott válaszukhoz. Ezek a mellékletek megtekinthetők a vevő oldalán is, miután egy szállító elküldte az ajánlatra adott választ. A szállítók által hozzáadott mellékletek mindig külsőnek minősülnek. Ha olyan melléklethez szeretne hozzáférni, amelyet a szállító egy ajánlattal együtt küldött el, válassza ki az **Ajánlatmellékletek** vagy az **Ajánlatsor-mellékletek** lehetőséget.
    
    Az ajánlatkérési üggyel együtt küldött mellékletek megnyitásához használja a dokumentumkezelő papírkapocs szimbólumot a válasznál.

- **Módosítások** – Ha egy módosítást véglegesítenek, akkor a meglévő ajánlatválaszokat eltávolítja a rendszer, hogy azok helyére frissített értékek kerülhessenek. Az olyan információk, mint a sor ára és mennyisége a korábbi ajánlatválaszoknál, megtekinthetők a naplókon keresztül az ajánlatkérési ügynél.

    A módosítás feldolgozásának érvényesítéséhez a **Beszerzési és forrásparaméterek** oldal **Ajánlatkérések** gyorslapján állítsa az **Ajánlatkérések zárolása kiküldés után** beállítást **Igen** értékre. (Ez a lehetőség be van állítva és kötelező az állami szektor esetén.)

- **Visszaküldések** – Ha egy szállító már benyújtotta az ajánlatot, de további vagy módosított információ szükséges az ajánlatkérési esethez, akkor a vevő visszaküldheti az ajánlatot a szállítónak. A korábban benyújtott ajánlat adatai megmaradnak, és a szállító a kért módosításokat az ajánlattételi folyamat újraindítása nélkül is elvégezheti.

## <a name="public-sector-extensions"></a>Állami szektor kiterjesztései

Az állami szféra esetén a kibővített funkciók lehetővé teszik, hogy az ajánlatkérési eseteket elküldje a szállítóknak, illetve közzétegye őket. Amikor közzétesz egy ajánlatkérést, akkor az információt kérő minden személy megtekintheti a munkát, amely megfelel a közszféra legtöbb szabályozásának. Az összes elérhető munka a **Közzétett ajánlatkérések megnyitása** listaoldalon jelenik meg, a törölt, függőben lévő vagy odaítélt ajánlatkérések pedig a **Lezárt közzétett ajánlatkérések** listaoldalon láthatók. Ezeket a dokumentumokat a Supply Chain Management programon kívül is megtektinheti a következő adatentitásokkal való integrációk révén:

- Közzétett ajánlatkérések
- Közzétett ajánlatkéréssorok
- Közzétett ajánlatkérés-fejlécmellékletek

Ezek az entitások lehetővé teszik azon személyeknek, akiknél nincs telepítve a Supply Chain Management szolgáltatás, de névtelen hozzáféréssel rendelkeznek a külső webhelyhez, hogy megtekintsék a rendelkezésre álló és a lezárt munkákat. Ezenkívül a **Küldés és közzététel** kibővített funkciói lehetővé teszi az ajánlatkérési folyamat paramétereit beállító felhasználónak, hogy e-mail-sablont határozzon meg. Ezt követően, amikor a beszerző létrehozza az ajánlatkérési esetet, akkor ki kell választania az e-mail-sablont, hogy elküldje a szükséges információkat a szállítóknak az ajánlatkérési esetnél. 

A felhasználó, aki az ajánlatkérési folyamat paramétereit beállítja, több e-mail sablont is létrehozhat. Ezek az e-mail-sablonok statikus szöveget és a következő helyettesítő tokeneket is tartalmazhatják. A tokenek helyére kontextus szerinti értékek kerülnek e-mail létrehozása esetén.

- %RFQCase%
- %RFQCaseName%
- %bidType%
- %inviteOnly%
- %expiryDateTime%
- %requester%
- %requestingDepartment%
- %accountnum%
- %todaysdate%
- %createddate%

Ha módosítás szükséges, és elküldik az ajánlatkérés elküldését követően, az ajánlatkérés elküldése minden meghívott szállítónál ismét megtörténik. A közzétett dokumentum is frissül a **Közzétett ajánlatkérések megnyitása** lapon.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]