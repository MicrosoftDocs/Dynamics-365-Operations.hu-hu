---
title: "Modern számla jóváhagyások"
description: "Mobil lehetőségek a Microsoft Dynamics 365 műveletek lehetővé teszik a hordozható elemek tervezése üzleti felhasználó. Speciális esetekben a platform most is a fejlesztők lehetőségeinek bővítésére, azok kívánják. A leghatékonyabb módszer, hogy megtudja, néhány új fogalom a mobile végigjárni a folyamat néhány forgatókönyvek tervezésekor is. Ez a témakör gyakorlati megközelítése tervezése mobil forgatókönyvek figyelembevételével szállítói számla jóváhagyások, használati eset Mobile célja. Ez a témakör segít az esetekben egyéb változatok tervezése és szállítói számlák nem kapcsolódnak más esetekben is alkalmazható."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 30229c0d24aed0bd927993b9af76b32d9bb073ee
ms.lasthandoff: 03/31/2017


---

# <a name="mobile-invoice-approvals"></a>Modern számla jóváhagyások

Mobil lehetőségek a Microsoft Dynamics 365 műveletek lehetővé teszik a hordozható elemek tervezése üzleti felhasználó. Speciális esetekben a platform most is a fejlesztők lehetőségeinek bővítésére, azok kívánják. A leghatékonyabb módszer, hogy megtudja, néhány új fogalom a mobile végigjárni a folyamat néhány forgatókönyvek tervezésekor is. Ez a témakör gyakorlati megközelítése tervezése mobil forgatókönyvek figyelembevételével szállítói számla jóváhagyások, használati eset Mobile célja. Ez a témakör segít az esetekben egyéb változatok tervezése és szállítói számlák nem kapcsolódnak más esetekben is alkalmazható.

<a name="prerequisites"></a>Előfeltételek
-------------

| Előfeltételek                                                                                            | Leírás                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mobil kézikönyvet előtti olvasása                                                                                |(/ dynamics365/műveletek/dev-IT-szakemberek/mobile-apps / mobile-platform.md)                                                                                                  |
| 365 Dynamics műveletek                                                                             | Olyan környezetben, amely a Microsoft Dynamics 365 1611 műveletek verziójához és a Microsoft Dynamics műveletek platform frissítése (November 2016) 3                   |
| KB 3204341 gyorsjavítást.                                                                              | A Feladatrögzítő tévesen rögzítheti a művelet platformfrissítés 3 (November 2016 frissítés) 365 Dynamics szerepel a legördülő párbeszédek két Bezárás parancs |
| KB 3207800 gyorsjavítást.                                                                              | Ez a gyorsjavítás lehetővé teszi, hogy a megtekinteni, a mobil ügyfél a művelet platformfrissítés 3 (November 2016 frissítés) 365 Dynamics szerepel a mellékleteket.           |
| KB 3208224 gyorsjavítást.                                                                              | Alkalmazás kódja szerepel a Microsoft Dynamics AX alkalmazás 7.0.1 (2016. május) mobil szállítói számla jóváhagyási kérelmet.                          |
| Egy Android vagy iOS vagy egy Windows-eszköz, amely a mobil app Dynamics 365 műveletek telepítve van | Keresse meg az alkalmazás a megfelelő app tárolóban.                                                                                                                     |

## <a name="introduction"></a>Bevezetés
A szállítói számlák mobil jóváhagyások "Előfeltételek" című szakaszában említett három gyorsjavítások van szükség. Ezeket a gyorsjavításokat a munkaterület nem biztosítanak a számla-jóváhagyási. Hogy megtudja, milyen munkaterület keretén belül mobil, olvasható a mobil kézikönyvet, amely az "Előfeltételek" című részben említett. A számla jóváhagyások munkaterületet kell kialakítani. 

Minden szervezet orchestrates, és eltérő módon határozza meg az üzleti folyamat, a szállítói számlák. A szállítói számla jóváhagyások mobil élmény tervez, előtt vegye figyelembe a következő szempontokat az üzleti folyamat. Az ötlet, ha ilyen adatponton, amennyire lehetséges, az eszköz a felhasználói élmény optimalizálásáról használják.

-   Milyen a számla fej mezőit a program a felhasználó szeretné megjeleníteni a mobil élmény, és milyen sorrendben?
-   A számlasorok mely mezői lesz a felhasználó szeretné megjeleníteni a mobil élmény, és milyen sorrendben?
-   Hány számlasorok vannak a számlán? Itt a 80-20 szabály alkalmazása, és optimalizálja a 80 %-át.
-   Felhasználók akarnak könyvelési felosztások (számla kódolás) lásd a mobileszközön szereplő ellenőrzések során? Ha erre a kérdésre a válasz Igen, gondolja át a következő kérdéseket:
    -   Hány könyvelési felosztások (kiterjesztett ár, áfa, vegyes költségek, megszakítások és így tovább) a számlasor van? A 80-20 szabály újra alkalmazni.
    -   A számlák is rendelkezik könyvelési felosztások a számla fejen? Ha igen, a könyvelési felosztások kell rendelkezésre állnia az eszköz?

> [!NOTE]
> Ez a témakör nem bemutatják, hogyan szerkesztheti a könyvelési felosztásokat, mert ez a funkció jelenleg nem támogatja a hordozható változatok.

-   Lesz felhasználókat szeretné megjeleníteni a számlához tartozó mellékleteket az eszközön?

A számla-jóváhagyási mobil élmény kialakítása a válaszaitól függően eltérőek. Célja, hogy a felhasználói élmény a mobil a szervezet üzleti folyamat optimalizálása. Ez a témakör a többi program közelebbről két forgatókönyv-változatok különböző az előző kérdésekre adott válaszok alapján. 

Iránymutatásként általános, a mobil designer való munka során győződjön meg arról, "közzétenni" a változások a frissítések elvesztésének megakadályozása érdekében.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>A Contoso egy egyszerű számla-jóváhagyási forgatókönyv tervezése
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Változatattribútum</th>
<th>Válasz</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Milyen a számla fej mezőit a program a felhasználó szeretné megjeleníteni a mobil élmény, és milyen sorrendben?</td>
<td><ol>
<li>Szállító neve</li>
<li>Számla összege</li>
<li>Számlafogadó</li>
<li>Számla száma</li>
<li>Számla dátuma</li>
<li>Számla leírása</li>
<li>Esedékes</li>
<li>Számla pénzneme</li>
</ol></td>
</tr>
<tr class="even">
<td>A számlasorok mely mezői lesz a felhasználó szeretné megjeleníteni a mobil élmény, és milyen sorrendben?</td>
<td><ol>
<li>Beszerzési kategória</li>
<li>Mennyiség</li>
<li>Egységár</li>
<li>Sor nettó összege</li>
<li>1099-es összeg</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hány számlasorok vannak a számlán? Itt a 80-20 szabály alkalmazása, és optimalizálja a 80 %-át.</td>
<td>1</td>
</tr>
<tr class="even">
<td>Felhasználók akarnak könyvelési felosztások (számla kódolás) lásd a mobileszközön szereplő ellenőrzések során?</td>
<td>Igen</td>
</tr>
<tr class="odd">
<td>Hány könyvelési felosztások (kiterjesztett ár, áfa, vegyes költségek és így tovább) a számlasor van? A 80-20 szabály újra alkalmazni.</td>
<td>Kiterjesztett ár: 2 áfa: 0 díj: 0</td>
</tr>
<tr class="even">
<td>A számlák is rendelkezik könyvelési felosztások a számla fejen? Ha igen, a könyvelési felosztások kell rendelkezésre állnia az eszköz?</td>
<td>Nincs használatban</td>
</tr>
<tr class="odd">
<td>Lesz felhasználókat szeretné megjeleníteni a számlához tartozó mellékleteket az eszközön?</td>
<td>Igen</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>A munkaterület létrehozása

1.  A böngészőben nyissa meg a Dynamics 365 műveletekhez, és jelentkezzen be.
2.  Hozzáfűzés után már bejelentkezett, **& mód = mobil** az URL-címet, ahogy az alábbi példa, és az oldal frissítése: https://&lt;yoururl&gt;/? cmp = usmf & mi = DefaultDashboard**& mód = mobil**
3.  Kattintson a **beállítások** (felszerelés) gombra a jobb felső sarkában az oldal, és kattintson a **Mobile alkalmazás**. A mobil app Tervező kell jelennek meg ugyanúgy, mint a tevékenység író jeleníti meg.
4.  Kattintson a **hozzáadása** új munkaterület létrehozása. Ebben a példában a neve a munkaterület **Jóváhagyásaim**.
5.  Adjon meg leírást.
6.  Munkaterület szín kiválasztása. A munkaterület szín lesz a mobil élmény ehhez a munkaterülethez, az általános stílus.
7.  Jelöljön ki egy ikont a munkaterületet.
8.  Kattintson a **végzett**
9.  Kattintson a **közzététele a munkaterület** menti a módosításokat

### <a name="vendor-invoices-assigned-to-me"></a>Hozzám rendelt szállítói számlák

Az első Mobil oldalon kell tervezéséhez, véleményezésre a felhasználóhoz rendelt számlák listájának. A mobil lapon tervez, használja a **VendMobileInvoiceAssignedToMeListPage** Dynamics 365 műveletek lap. Az eljárás végrehajtása előtt győződjön meg arról, hogy legalább egy szállítói számla Önhöz van rendelve, véleményezésre, és hogy a számlasor két felosztásokat. Ez a beállítás megfelel a forgatókönyv.

1.  Az URL-műveletek Dynamics 365, cserélje ki a menüelem neve **VendMobileInvoiceAssignedToMeListPage** mobil változatát nyitja meg, a **függő hozzám rendelt szállítói számlák** lista oldalra a **kötelezettségek** modul. Attól függően, hogy a rendszer rendelte meg számlák számát a lapon megjelenik a számlákhoz. A bal oldalon egy bizonyos számla keresésére használhatja a szűrőt. Azonban ebben a példában az adott számla nem kérünk. Kérünk csak néhány Önhöz rendelt számla, amely lehetővé teszi a mobil lap tervezése megy. A rendelkezésre álló új oldalak készített kifejezetten a szállítói számla mobil forgatókönyvek kidolgozása. Ezért ezeket az oldalakat kell használnia. Az URL-cím a következő URL-címet kell hasonlítson, és miután megadta, szerepelnie kell az oldalon, az ábrán látható: https://&lt;yourURL&gt;/? cmp = usmf & mi =**VendMobileInvoiceAssignedToMeListPage**& mód = mobil [![oldalon függő hozzám rendelt szállítói számlák](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
2.  Kattintson a **beállítások** (felszerelés) gombra a jobb felső sarkában az oldal, és kattintson a **Mobile alkalmazás**
3.  Jelölje ki a munkaterületet, és kattintson a **szerkesztése**
4.  Kattintson a **hozzáadása lap** az első mobil lap létrehozásához.
5.  Adja meg a nevet, például **a szállítói számlák**, és egy leírást, például a **véleményezésre hozzám rendelt szállítói számlák**.
6.  Click **Done**.
7.  A mobil-tervezőben meg a **mezők** fülre, kattintson a **mezők**. Az oszlopok a lista lapon az alábbi ábrán kell egyenlítődnie. [![Hozzám rendelt a függőben lévő szállítói számlák oszlopok lap](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
8.  Adja hozzá a szükséges oszlopokat meg kell jeleníteni a Mobil oldalon a felhasználók listája lapról. A rendelést ad hozzá a sorrend, amelyben a mezők jelenjenek meg a végfelhasználó. A mezők sorrendjének megváltoztatása csak úgy lesz újra az összes mező kijelölésével. A példánkban szereplő követelmények alapján, a következő nyolc mezők szükségesek. Azonban egyes felhasználók érdemes fontolóra venni a nyolc mező túl sok információ, hogy a mobil eszközön. Ezért bemutatjuk a legfontosabb mezők a mobil lista nézetben. A fennmaradó mezőket azt később fogja tervezési részletek nézetben jelenik meg. Most hozzáadunk a következő mezőket. Kattintson a plusz jelre (**+**) a mobil lapon hozzáadandó ezekben az oszlopokban.
    1.  Szállító neve
    2.  Számla összege
    3.  Számlafogadó
    4.  Számla száma
    5.  Számla dátuma

    A mezőket a felvétele után a mobil lapon az alábbi ábrán kell egyenlítődnie. [![Az Oldal mezők hozzáadása után](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)
9.  Fel kell vennünk a következő oszlopok, most, hogy azt lehetővé teszi munkafolyamat-műveletek.
    1.  Teljes tevékenység megjelenítése
    2.  Delegált feladat megjelenítése
    3.  Visszahívási tevékenység megjelenítése
    4.  Elutasítás tevékenység megjelenítése
    5.  Kérelem befejezését tevékenység megjelenítése
    6.  Újraküldése tevékenység megjelenítése

10. Kattintson a **végzett** Szerkesztés módból való kilépéshez.
11. Kattintson a **vissza** és **végzett** való kilépéshez a munkaterület
12. Kattintson a **közzététele a munkaterület** menteni a kiadványt.
13. Engedélyezze a **megjelenített számla végösszege függő szállítói számlák listájának** a Kötelezettségek paraméterei képernyő alatt **számla**. Vegye figyelembe, hogy, ez a paraméter csak engedélyezésével számlaösszegek nem jelennek meg a függőben lévő szállítói számlák listaoldalán számolja ki. Ez az új képesség előre szükséges gyorsjavítás 3208224 részeként.

### <a name="vendor-invoice-details"></a>Szállítói számla részletei

A számla Részletek lap Mobile tervez, használja a **VendMobileInvoiceHeaderDetails** Dynamics 365 műveletek lap. Fontos megjegyezni, hogy a rendszer számlájának számától függ, ezen a lapon megjelenik a legrégebbi számla (az első létrehozott számla). A bal oldalon egy bizonyos számla keresésére használhatja a szűrőt. Azonban ebben a példában az adott számla nem kérünk. Néhány számla adatait csak úgy, hogy azt is a mobil lap tervezése szükséges. [![Munkafolyamat-lap](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1.  Az URL-műveletek Dynamics 365, cserélje ki a menüelem neve **VendMobileInvoiceHeaderDetails** a képernyő megnyitásához
2.  A mobil designer nyissa meg a **beállítások** (felszerelés) gombra.
3.  Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmód.
4.  Válassza ki a ** a szállítói számlák ** korábban készített oldal, és kattintson a **Szerkesztés**.
5.  A a **mezők** fülre, kattintson a **rács** oszlop fejlécére.
6.  Kattintson a **tulajdonságok**&gt;**hozzáadása lap**. **Megjegyzés:** kattint a **rács** vámtarifaszám alá tartozó, és adjon hozzá egy oldalt, a Részletek lap automatikusan létrejön a kapcsolat.
7.  Adja meg a lap címét, például **a számla részletei**, és egy leírást, például a **számla fej és sor részleteinek megtekintése**.
8.  Kattintson a **mezők**. Ne feledje, hogy, a rendelést ad hozzá a sorrend, amelyben a mezők jelenjenek meg a végfelhasználó. A mezők sorrendjének megváltoztatása csak úgy lesz újra az összes mező kijelölésével.
9.  A fejből, ebben az esetben a követelmények alapján adja hozzá a következő mezőket:
    1.  Szállító neve
    2.  Számla összege
    3.  Számlafogadó
    4.  Számla száma
    5.  Számla dátuma
    6.  Számla leírása
    7.  Esedékes
    8.  Számla pénzneme

10. Az oldalon a sorok rácsból adja hozzá a következő mezőket:
    1.  Beszerzési kategória
    2.  Mennyiség
    3.  Egységár
    4.  Sor nettó összege
    5.  1099-es összeg

11. Az előző két lépést az összes mező hozzáadása után kattintson a **végzett**. A lap az alábbi ábrán kell egyenlítődnie. [![Az Oldal mezők hozzáadása után](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)
12. Kattintson a **végzett** Szerkesztés módból való kilépéshez.
13. Kattintson a **vissza** és **végzett** való kilépéshez a munkaterület
14. Kattintson a **közzététele a munkaterület** mentse a munkáját,

### <a name="workflow-actions"></a>Munkafolyamat-műveletek

Munkafolyamat-műveletek hozzáadásához használja a **VendMobileInvoiceHeaderDetails** Dynamics 365 műveletek lap. Nyissa meg a lapot, cserélje ki az URL-cím, a menüpont neve, mint korábban. Nyissuk meg a mobil designer a **beállítások** (felszerelés) gombra. Kövesse az alábbi lépéseket a munkafolyamat-műveletek hozzáadása a Részletek oldalon.

1.  Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmód.
2.  Válassza ki a **a számla részletei** korábban készített oldal, és kattintson a **szerkesztése**.
3.  A a **műveletek** fülre, kattintson a **művelet hozzáadása**.
4.  Adjon meg egy művelet címet, például a **jóváhagyás**, és egy leírást, például a **jóváhagyás számla**. Fontos megjegyezni, hogy a művelet cím itt a műveletet, amely akkor jelenik meg a felhasználónak a mobile alkalmazás neve lesz.
5.  Click **Done**.
6.  Kattintson a **mezők**.
7.  Munkafolyamat végigjárni a **VendMobileInvoiceHeaderDetails** oldalon, és a felvenni kívánt művelet végrehajtásához. Győződjön meg arról, hogy a folyamat során írja be a munkafolyamat megjegyzéseket, úgy, hogy a mobil élmény is szerepel a Megjegyzések mezőben.
8.  A munkafolyamat-művelet futtatása után kattintson a **végzett** a Mezőválasztás feladat elvégzéséhez.
9.  Kattintson a **végzett** Szerkesztés módból való kilépéshez.
10. Kattintson a **vissza** és **végzett** való kilépéshez a munkaterület
11. Kattintson a **közzététele a munkaterület** mentse a munkáját,
12. Ismételje meg a 3-11 a szükséges munkafolyamat-műveletek rögzítése. Ne feledje, hogy a követelmény, hogy az Önhöz rendelt számlákat, a munkafolyamat-műveletek számára elérhetővé szeretné tenni, hogy a tervezési kívánja állapotban vannak.
13. Nyissa meg a Jegyzettömb vagy a Microsoft Visual Studio, és illessze be a következő kódot. Mentse a fájlt egy .js fájlt. Ezt a kódot teszi két dolgot:
    1.  Elrejti azt korábban hozzáadott a mobil listaoldalán munkafolyamattal kapcsolatos további oszlopokat. Ezek az oszlopok kibővült, hogy az alkalmazás ezt az információt van összefüggésben, és teheti meg a következő lépés.
    2.  Aktív munkafolyamat-lépés alapul, csak azok a műveletek megjelenítéséhez logika vonatkozik.

Vegye figyelembe, hogy a lapok neve és más vezérlőelemek a JS kódot meg kell egyeznie a munkaterületről.

1.  Függvény fő (metadataService, dataService, cacheService, $q) {vissza {appInit: függvény (appMetadata) {/ /, csak a jelen, de nem látható metadataService.configureControl vezérlők elrejtése ("saját-szállító-számlák,"ShowAccept", {rejtett: igaz}); metadataService.configureControl (" saját-szállító-számlák, "ShowApprove", {rejtett: igaz}); metadataService.configureControl ("saját-szállító-számlák,"ShowReject", {rejtett: igaz}); metadataService.configureControl (" saját-szállító-számlák, "ShowDelegate", {rejtett: igaz}); metadataService.configureControl ("saját-szállító-számlák,"ShowRequestChange", {rejtett: igaz}); metadataService.configureControl (" saját-szállító-számlák, "ShowRecall", {rejtett: igaz}); metadataService.configureControl ("saját-szállító-számlák,"ShowComplete", {rejtett: igaz}); metadataService.configureControl (' {saját-szállító-számlák,"ShowResubmit", Rejtett: igaz}); }, pageInit: függvény (pageMetadata, "params") {Ha (pageMetadata.Name == "Számla-részletek") {/ / alapuló munkafolyamat munkafolyamat-műveletek megjelenítése lépés metadataService.configureAction ("Elfogadás", {látható: igaz}); metadataService.configureAction ("Jóváhagyás", {látható: igaz}); metadataService.configureAction ("Elutasítás", {látható: igaz}); metadataService.configureAction ("Meghatalmazott" {látható: igaz}); metadataService.configureAction ("módosításának kérése", {látható: igaz}); metadataService.configureAction ("Visszahívás", {látható: igaz}); metadataService.configureAction ("Teljes", {látható: igaz}); metadataService.configureAction ("Újraküldése", {látható: igaz});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                       var showRejectControl = Boolean(rejectControl == 1);
                      var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                     metadataService.configureAction('Resubmit', { visible: showResubmitControl });
                   }
                 },
           };
        }

2.  A munkaterület kiválasztásával a kód fájlt feltölteni a **logika** lap
3.  Kattintson a **végzett** Szerkesztés módból való kilépéshez.
4.  Kattintson a **vissza** és **végzett** való kilépéshez a munkaterület
5.  Kattintson a **közzététele a munkaterület** mentse a munkáját,

### <a name="vendor-invoice-attachments"></a>Szállítói számla mellékletek

1.  Kattintson a **beállítások** (felszerelés) gombra a jobb felső sarkában az oldal, és kattintson a **Mobile alkalmazás**
2.  Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmód.
3.  Válassza ki a ** számlaadatok ** korábban készített oldal, és kattintson a **szerkesztése**.
4.  Állítsa be a **Dokumentumkezelés** be **Igen** ahogy az lent látható. **Megjegyzés:** nincsenek követelmények mellékletek jelenjenek meg a mobileszközön, ha a beállítás értéke hagyhatja **nem**, amely az alapértelmezett beállítása.
5.  [![docmanagement](./media/docmanagement-216x300.png)](./media/docmanagement.png)
6.  Kattintson a **végzett** Szerkesztés módból való kilépéshez.
7.  Kattintson a **vissza** és **végzett** való kilépéshez a munkaterület
8.  Kattintson a **közzététele a munkaterület** mentse a munkáját,

### <a name="vendor-invoice-line-distributions"></a>Szállítói számla sor felosztások

A példánkban szereplő követelmények győződjön meg arról, hogy az csak sor szintű felosztás lesz, és, hogy a számla mindig lesz csak egy sor. Mivel ez a forgatókönyv egy egyszerű, a felhasználói élmény a mobil eszközön elég egyszerű, hogy a felhasználónak nem kell részletezni a felosztások megtekintése több szinten kell. Szállítói számlák Dynamics 365 műveletek például megjeleníthető az összes felosztott a számla fejen. A tapasztalat, mire van szükségünk a mobil eset. Ezért ezeket fogjuk használni a **VendMobileInvoiceAllDistributionTree** lap tervezésekor a mobil esetben ez a része. 

> [!NOTE] 
> A követelmények ismerete segít eldönteni, melyik adott oldalra, és hogyan pontosan a mobil a felhasználói élmény optimalizálása, ha azt az esetet. A második forgatókönyv azt használja egy másik oldalra a felosztásokat, mert az eset követelményei eltérőek.

1.  Az URL-cím a menüpont nevét cseréljük ki, mint előtt. A megjelenő lapon kell hasonlítanak az alábbi ábrán látható. [![Az összes felosztott oldal](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)
2.  A mobil designer nyissa meg a **beállítások** (felszerelés) gombra.
3.  Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmód. **Megjegyzés:** jelenik meg, hogy két új oldal automatikusan jöttek létre. A rendszer ezeket az oldalakat hoz létre, mert bekapcsolta az előző részben a Dokumentumkezelés. Ezek a lapok figyelmen kívül hagyhatja.
4.  Kattintson a **hozzáadása lap**.
5.  Adja meg a lap címét, például **nézet számviteli**, és egy leírást, például a **nézet számviteli számla**.
6.  Click **Done**.
7.  A a **mezők** fülre, kattintson a **mezők**, a felosztások lapon válassza a következő mezőket, és kattintson a **végzett**:
    1.  Összeg
    2.  Pénznem
    3.  Főkönyvi számla

> [!NOTE] 
> Nem jelölt ki, hogy a **leírás** a felosztások rácsból oszlop, mert ebben az esetben a követelmények megerősítik, hogy a kiterjesztett ár csak összeg, amely felosztásainak lesz. Ezért a felhasználónak nem kell egy másik mező, amely a terjesztési összeg típusának megállapításához. A következő esetekben azonban a Microsoft **fog** ezt az információt használja, mivel az eset követelményei ad meg, van-e egyéb összegtípusokat felosztások (például áfa).
8.  Kattintson a **végzett** Szerkesztés módból való kilépéshez.
9.  Kattintson a **vissza** és **végzett** való kilépéshez a munkaterület
10. Kattintson a **közzététele a munkaterület** mentse a munkáját,

**Megjegyzés:** a **nézet számviteli** hordozható lapon nincs csatolva a mobil oldalakon, amelyek eddig beállítottuk. Mert a felhasználó tud lépni a **nézet számviteli** a lap a **számla részletei** lap a mobileszközön, azt kell adnia a navigációs a **számla részletei** az oldal a **nézet számviteli** lap. A navigációs alakítsunk ki további logika keresztül JavaScript segítségével.

1.  Nyissa meg a korábban létrehozott .js fájlt, és a kiemelt sorok hozzáadása a következő kódban. Ezt a kódot teszi két dolgot:
    1.  Segít garantálni, hogy a felhasználók közvetlenül a munkaterületről nem léphetnek a **nézet számviteli** oldalon.
    2.  Navigációs vezérlő megállapítja a **a számla részletei** a lap a **nézet számviteli** lap.

> [!NOTE] 
> A lapok és más vezérlőelemek a JS kód neve azonos a munkaterületről kell lennie.

1.  Függvény fő (metadataService, dataService, cacheService, $q) {vissza {appInit: függvény (appMetadata) {/ /, csak a jelen, de nem látható metadataService.configureControl vezérlők elrejtése ("saját-szállító-számlák,"ShowAccept", {rejtett: igaz}); metadataService.configureControl (" saját-szállító-számlák, "ShowApprove", {rejtett: igaz}); metadataService.configureControl ("saját-szállító-számlák,"ShowReject", {rejtett: igaz}); metadataService.configureControl (" saját-szállító-számlák, "ShowDelegate", {rejtett: igaz}); metadataService.configureControl ("saját-szállító-számlák,"ShowRequestChange", {rejtett: igaz}); metadataService.configureControl (" saját-szállító-számlák, "ShowRecall", {rejtett: igaz}); metadataService.configureControl ("saját-szállító-számlák,"ShowComplete", {rejtett: igaz}); metadataService.configureControl (' {saját-szállító-számlák,"ShowResubmit", Rejtett: igaz}); Nem alkalmazható gyökér navigációs metadataService.hideNavigation('View-accounting'); lapok elrejtése Számviteli metadataService.addLink megtekintése hivatkozásra ("Számla-részletek," nézet-számviteli "," nézet-számviteli-nav-vezérlő ","Nézet számviteli", true); }, pageInit: függvény (pageMetadata, "params") {Ha (pageMetadata.Name == "Számla-részletek") {/ / alapuló munkafolyamat munkafolyamat-műveletek megjelenítése lépés metadataService.configureAction ("Elfogadás", {látható: igaz}); metadataService.configureAction ("Jóváhagyás", {látható: igaz}); metadataService.configureAction ("Elutasítás", {látható: igaz}); metadataService.configureAction ("Meghatalmazott" {látható: igaz}); metadataService.configureAction ("módosításának kérése", {látható: igaz}); metadataService.configureAction ("Visszahívás", {látható: igaz}); metadataService.configureAction ("Teljes", {látható: igaz}); metadataService.configureAction ("Újraküldése", {látható: igaz});

                       var entityContextParts = params.pageContext.split(':');
                       var data = dataService.getEntityData(entityContextParts[0], entityContextParts[1]);

                       var acceptControl = data.getPropertyValue('VendInvoiceInfoTable/showAccept');
                       var approveControl = data.getPropertyValue('VendInvoiceInfoTable/showApprove');
                       var rejectControl = data.getPropertyValue('VendInvoiceInfoTable/showReject');
                       var delegateControl = data.getPropertyValue('VendInvoiceInfoTable/showDelegate');
                       var requestChangeControl = data.getPropertyValue('VendInvoiceInfoTable/showRequestChange');
                       var recallControl = data.getPropertyValue('VendInvoiceInfoTable/showRecall');
                       var completeControl = data.getPropertyValue('VendInvoiceInfoTable/showComplete');
                       var resubmitControl = data.getPropertyValue('VendInvoiceInfoTable/showResubmit');

                       var showAcceptControl = Boolean(acceptControl == 1);
                       var showApproveControl = Boolean(approveControl == 1);
                     var showRejectControl = Boolean(rejectControl == 1);
                       var showDelegateControl = Boolean(delegateControl == 1);
                       var showRequestChangeControl = Boolean(requestChangeControl == 1);
                       var showRecallControl = Boolean(recallControl == 1);
                       var showCompleteControl = Boolean(completeControl == 1);
                       var showResubmitControl = Boolean(resubmitControl == 1);

                       metadataService.configureAction('Accept', { visible: showAcceptControl });
                       metadataService.configureAction('Approve', { visible: showApproveControl });
                       metadataService.configureAction('Reject', { visible: showRejectControl });
                       metadataService.configureAction('Delegate', { visible: showDelegateControl });
                       metadataService.configureAction('Request-change', { visible: showRequestChangeControl });
                       metadataService.configureAction('Recall', { visible: showRecallControl });
                       metadataService.configureAction('Complete', { visible: showCompleteControl });
                       metadataService.configureAction('Resubmit', { visible: showResubmitControl });
        }
                 },
           };
        }

2.  A munkaterület kiválasztásával a kód fájlt feltölteni a **logika** fülre, és felülírja az előző kódot
3.  Kattintson a **végzett** Szerkesztés módból való kilépéshez.
4.  Kattintson a **vissza** és **végzett** való kilépéshez a munkaterület
5.  Kattintson a **közzététele a munkaterület** mentse a munkáját,

### <a name="validation"></a>Ellenőrzés

A mobilkészülék nyissa meg az alkalmazás, és csatlakozzon a Dynamics 365 műveletek példány. Győződjön meg arról, hogy a bejelentkezést a vállalat adott szállítói számlák nincsenek Önhöz rendelt véleményezésre. Meg kell a következő műveleteket:

-   Lásd a **Jóváhagyásaim** munkaterület.
-   Feltárás a **a jóváhagyások** munkaterület és lásd: a **a szállítói számlák** oldalon.
-   Feltárás a **a szállítói számlák** oldalon, és nincsenek Önhöz rendelt számlák listájának megtekintéséhez.
-   A számlák feltárni, és a számlaadatok fej és sor részletei.
-   A részletek lapon mellékleteket mutató hivatkozást talál, és e hivatkozás segítségével keresse meg a mellékletek listája és a mellékletek megtekintése.
-   A jobb oldalon látható mutató hivatkozás a **számviteli megtekintése** oldal, és e hivatkozás segítségével nyissa meg a felosztások oldalát, és a felosztásokat megtekintése.
-   Kattintson a Részletek lap a **műveletek** menü alján, és alkalmazható a munkafolyamat-lépés a munkafolyamat műveleteket végrehajtó.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>A Fabrikam összetett számla jóváhagyási eset tervezése
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Változatattribútum</th>
<th>Válasz</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Milyen a számla fej mezőit a program a felhasználó szeretné megjeleníteni a mobil élmény, és milyen sorrendben?</td>
<td><ol>
<li>Szállító neve</li>
<li>Számlaösszeg</li>
<li>Számlafogadó</li>
<li>Számla száma</li>
<li>Számla dátuma</li>
<li>Számla leírása</li>
<li>Esedékes</li>
<li>Számla pénzneme</li>
</ol></td>
</tr>
<tr class="even">
<td>A számlasorok mely mezői lesz a felhasználó szeretné megjeleníteni a mobil élmény, és milyen sorrendben?</td>
<td><ol>
<li>Beszerzési kategória</li>
<li>Mennyiség</li>
<li>Egységár</li>
<li>Sor nettó összege</li>
<li>1099-es összeg</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hány számlasorok vannak a számlán? Itt a 80-20 szabály alkalmazása, és optimalizálja a 80 %-át.</td>
<td>5</td>
</tr>
<tr class="even">
<td>Felhasználók akarnak könyvelési felosztások (számla kódolás) lásd a mobileszközön szereplő ellenőrzések során?</td>
<td>Igen</td>
</tr>
<tr class="odd">
<td>Hány könyvelési felosztások (kiterjesztett ár, áfa, vegyes költségek és így tovább) a számlasor van? A 80-20 szabály újra alkalmazni.</td>
<td>Kiterjesztett ár: 2 áfa: 2 díjak: 2</td>
</tr>
<tr class="even">
<td>A számlák is rendelkezik könyvelési felosztások a számla fejen? Ha igen, a könyvelési felosztások kell rendelkezésre állnia az eszköz?</td>
<td>Nincs használatban</td>
</tr>
<tr class="odd">
<td>Lesz felhasználókat szeretné megjeleníteni a számlához tartozó mellékleteket az eszközön?</td>
<td>Igen</td>
</tr>
</tbody>
</table>

### <a name="exercise"></a>Gyakorlása

A következő változatok forgatókönyv 1, 2. forgatókönyv követelményei alapján lehet elvégezni. Ezen a szakaszon hajtható gyakorlat, a tanulás céljából.

1.  2. forgatókönyv több számlasorok várható, mert a terv a következő módosításokat segítenek a mobil eszközön a felhasználói élmény optimalizálása:
    1.  Számlasorok megjelenítése a Részletek oldalon (például 1. eset), helyett a felhasználók választhatnak megtekintéséhez külön Mobil oldalon.
    2.  Mivel több számla sor várható ebben az esetben, ha a **VendMobileInvoiceAllDistributionTree** lap szolgál a tervezéshez felosztások Mobile (például 1. eset), a felhasználó sorokat felosztások összehangolására összezavarhatja. Ezért használja a **VendMobileInvoiceLineDistributionTree** lap felosztások tervezéshez.
    3.  Ideális esetben a felosztásokat keretén belül egy számlasort, ebben az esetben kell feltüntetni. Ezért győződjön meg arról, hogy a felhasználó leáshat a BE felosztások oldalon a vonal. Használja létrehozásához a részletező hivatkozás oldal szolgáltatását, ugyanúgy mint a fej és a részletek lapok esetén 1.

2.  Egynél több összegtípus meg kell adni a felosztások 2. forgatókönyv (forgalmi adó, díj és így tovább), mert az összeg leírásának megjelenítése hasznos lesz. (Ezt az információt az 1. eset kihagyja azt.)

## <a name="conclusion"></a>Következtetés
A mobil platform és alkalmazási lehetőségeinek lehetővé teszik a felhasználó alap a szervezet optimalizált mobil forgatókönyvek tervezésekor. Az ebben a témakörben szereplő példák alapján, próbálja meg más változatok, és különböző elemek, amelyek megfelelnek az adott kell létrehozni.


