---
title: Mobil számlajóváhagyások
description: Ez a témakör gyakorlati megközelítést biztosít mobilforgatókönyvek tervezéséhez használati esetként mobilos szállítóiszámla-jóváhagyások figyelembevételével.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 262034
ms.assetid: 9db38b3f-26b3-436e-8449-7ff243568a18
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 83d95ef6d9fcff060ac992b11ab5773af075fea5409e43430b4826dc097570c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737355"
---
# <a name="mobile-invoice-approvals"></a>Mobil számlajóváhagyások

[!include [banner](../includes/banner.md)]

Mobil lehetőségek lehetővé teszik az üzleti felhasználónak a mobilélmények tervezését. Speciális esetekben a platformon a fejlesztők is igényeik szerint bővíthetik lehetőségeiket. A leghatékonyabb módszer a mobilon elérhető új lehetőségek megismeréséhez a forgatókönyvek tervezési folyamatának többszöri végigjárása. Ez a témakör gyakorlati megközelítést biztosít mobilforgatókönyvek tervezéséhez használati esetként mobilos szállítóiszámla-jóváhagyások figyelembevételével. A témakör segít a forgatókönyvek egyéb változatainak megtervezésében, és szállítói számlákhoz nem kapcsolódó más forgatókönyvekhez is alkalmazható.

## <a name="prerequisites"></a>Előfeltételek

| Előfeltételek                                                                                            | Leírás                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mobil kézikönyv előzetes olvasás                                                                                |[Mobil platform](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md)                                                                                                  |
| Dynamics 365 Finance                                                                              | Egy környezet, amely 1611-os verzióval és Platform update 3 (2016. november) rendelkezik                   |
| Telepítse a 3204341 számú tudásbáziscikkhez tartozó gyorsjavítást.                                                                              | A Feladatrögzítő tévesen két Bezárás parancsot rögzíthet legördülő párbeszédpaneleknél - ez a 3. platformfrissítésében található (2016. novemberi frissítés). |
| Telepítse a 3207800 számú tudásbáziscikkhez tartozó gyorsjavítást.                                                                              | Ez a gyorsjavítás lehetővé teszi a mellékletek megtekintését mobil kliensen - - ez a 3. platformfrissítésében található (2016. novemberi frissítés).           |
| Telepítse a 3208224 számú tudásbáziscikkhez tartozó gyorsjavítást.                                                                              | Alkalmazáskód a szállítói számla jóváhagyására szolgáló mobilalkalmazáshoz - ez a 7.0.1 (2016. május) verzióban szerepel.                          |
| Android-, iOS- vagy Windows-eszköz, amelyre telepítve van a mobilalkalmazás. | Keresse meg az alkalmazást a megfelelő alkalmazásáruházban.                                                                                                                     |

## <a name="introduction"></a>Bevezetés
A szállítói számlák mobil jóváhagyásához az „Előfeltételek” című szakaszban említett három gyorsjavításra van szükség. Ezek a gyorsjavítások nem biztosítanak munkaterületet számlajóváhagyáshoz. A munkaterület mobil környezetben való jelentésének megismeréséhez olvassa el az „Előfeltételek” című részben említett mobil kézikönyvet. A számlajóváhagyások munkaterületét ki kell alakítani. 

Minden szervezet eltérő módon szervezi és határozza meg a szállítói számlákkal kapcsolatos üzleti folyamatát. Mielőtt szállítói számlák jóváhagyásához mobilfelületet tervezne, vegye figyelembe az üzleti folyamat következő szempontjait. Az elképzelés lényege, hogy ezen adatpontokat a lehető legjobban kihasználjuk a felhasználói élmény az eszközön való optimalizálására.

-   A számlafejléc mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?
-   A számlasorok mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?
-   Hány számlasor van a számlán? Itt alkalmazza a 80-20-as szabályt, és optimalizáljon 80%-ra.
-   A felhasználók akarnak könyvelési felosztásokat (számlakódolást) látni a mobileszközön ellenőrzések során? Ha erre a kérdésre a válasz Igen, gondolja át a következő kérdéseket:
    -   Hány könyvelési felosztás (kiterjesztett ár, áfa, költségek, megosztások stb.) van egy-egy számlasornál? Ismételten alkalmazza a 80-20-as szabályt.
    -   A számlák szintén rendelkeznek könyvelési felosztásokkal a számla fejlécében? Ha igen, e könyvelési felosztásoknak rendelkezésre kell állniuk a készüléken?

    > [!NOTE]
    > Ez a témakör nem magyarázza el, hogyan szerkeszthetők a könyvelési felosztások, mert ez a funkció jelenleg a mobilváltozatokban nem támogatott.

-   A felhasználók látni szeretnék a számlához tartozó mellékleteket az eszközön?

A számlajóváhagyási mobilfelület kialakítása az e kérdésekre adott válaszoktól függően eltérő lesz. A cél: optimalizálni a szervezet üzleti folyamatának felhasználói élményét a mobilon. A témakör többi részében két forgatókönyv-változatot vizsgálunk meg közelebbről, amelyek az előző kérdésekre adott különböző válaszokon alapulnak. 

Általános iránymutatásként a mobiltervezővel való munka során ügyeljen, hogy „tegye közzé” a módosításokat, nehogy elveszítse a frissítéseket.

## <a name="designing-a-simple-invoice-approval-scenario-for-contoso"></a>Egyszerű számlajóváhagyási forgatókönyv tervezése a Contoso számára
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
<td>A számlafejléc mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</td>
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
<td>A számlasorok mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</td>
<td><ol>
<li>Beszerzési kategória</li>
<li>Mennyiség</li>
<li>Egységár</li>
<li>Sor nettó összege</li>
<li>1099-es összeg</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hány számlasor van a számlán? Itt alkalmazza a 80-20-as szabályt, és optimalizáljon 80%-ra.</td>
<td>1</td>
</tr>
<tr class="even">
<td>A felhasználók akarnak könyvelési felosztásokat (számlakódolást) látni a mobileszközön ellenőrzések során?</td>
<td>Igen</td>
</tr>
<tr class="odd">
<td>Hány könyvelési felosztás (kiterjesztett ár, áfa, költségek stb.) van egy-egy számlasornál? Ismételten alkalmazza a 80-20-as szabályt.</td>
<td>Kiterjesztett ár: 2 áfa: 0 költség: 0</td>
</tr>
<tr class="even">
<td>A számlák szintén rendelkeznek könyvelési felosztásokkal a számla fejlécében? Ha igen, e könyvelési felosztásoknak rendelkezésre kell állniuk a készüléken?</td>
<td>Nincs használatban</td>
</tr>
<tr class="odd">
<td>A felhasználók látni szeretnék a számlához tartozó mellékleteket az eszközön?</td>
<td>Igen</td>
</tr>
</tbody>
</table>

### <a name="create-the-workspace"></a>Munkaterület létrehozása

1.  Egy böngészőben, majd jelentkezzen be az alkalmazásba.
2.  Miután bejelentkezett, fűzze hozzá a **&mode=mobile** karakterláncot az URL-címhez az alábbi példa alapján, és frissítse az oldalt: https://&lt;sajaturl&gt;/?cmp=usmf&mi=DefaultDashboard **&mode=mobile**
3.  Kattintson a **Beállítások** (fogaskerék) gombra az oldal jobb felső sarkában, majd kattintson a **Mobilalkalmazás** elemre. Megjelenik a mobilalkalmazás tervezője és a Feladatrögzítő.
4.  Kattintson a **Hozzáadás** elemre új munkaterület létrehozásához. Ebben a példában adja a munkaterületnek a **Jóváhagyásaim** nevet.
5.  Adjon meg leírást.
6.  Válasszon színt a munkaterületnek. A munkaterület színe adja a munkaterülethez tartozó mobilfelület általános stílusát.
7.  Válasszon ikont a munkaterülethez.
8.  Kattintson a **Kész** gombra.
9.  A **Munkaterület közzététele** gombra kattintva mentse a módosításokat.

### <a name="vendor-invoices-assigned-to-me"></a>Hozzám rendelt szállítói számlák

Az első mobiloldal, amelyet meg kell terveznie, a véleményezésre a felhasználóhoz rendelt számlák listája. A mobillap megtervezéséhez használja a **VendMobileInvoiceAssignedToMeListPage** lapját. Az eljárás végrehajtása előtt győződjön meg arról, hogy legalább egy szállítói számla Önhöz van rendelve véleményezésre, és hogy a számlasor két felosztást tartalmaz. Ez a beállítás megfelel a jelen forgatókönyv követelményeinek.

1.  Az URL-ben cserélje le a menüelem nevét arra, hogy **VendMobileInvoiceAssignedToMeListPage**, és így megnyílik a **Hozzám rendelt függőben levő szállítói számlák** listaoldal mobilváltozata a **Kötelezettségek** modulban. A rendszerben Önhöz hozzárendelt számlák számától függően a lapon megjelennek az érintett számlák. Adott számla megkereséséhez használja a bal oldali szűrőt. Ebben a példában viszont nincs szükségünk konkrét számlára. Csak arra van szükségünk, hogy legyen néhány Önhöz rendelt számla, ami lehetővé teszi a mobillap megtervezését. A rendelkezésre álló új oldalakat kifejezetten a szállítói számlákhoz kapcsolódó mobilforgatókönyvek kidolgozásához alakítottuk ki. Ezért ezeket az oldalakat kell használnia. Az URL-nek a következő URL-re kell hasonlítania, és miután megadta, meg kell jelennie az ábrán látható oldalnak: https://&lt;yourURL&gt;/?cmp=usmf&mi=**VendMobileInvoiceAssignedToMeListPage**&mode=mobile 

    [![Hozzám rendelt függőben levő szállítói számlák oldal.](./media/mobile-invoice-approvals01-1024x281.png)](./media/mobile-invoice-approvals01.png)
    
2.  Kattintson a **Beállítások** (fogaskerék) gombra az oldal jobb felső sarkában, majd kattintson a **Mobilalkalmazás** elemre
3.  Válassza ki a munkaterületet, és kattintson a **Szerkesztés** elemre
4.  Kattintson az **Oldal hozzáadása** elemre az első mobiloldal létrehozásához.
5.  Adjon meg egy nevet, például **Saját szállítói számlák**, és egy leírást, például **Véleményezésre hozzám rendelt szállítói számlák**.
6.  Kattintson a **Kész** gombra.
7.  A mobiltervezőben a **Mezők** fülön kattintson a **Mezők kijelölése** elemre. A listalapon látható oszlopoknak az alábbi ábrához kell hasonlítaniuk. 

    [![Hozzám rendelt függőben lévő szállítói számlák oldalának oszlopai.](./media/mobile-invoice-approvals02-1024x117.png)](./media/mobile-invoice-approvals02.png)
    
8.  A listaoldalról adja hozzá a szükséges oszlopokat, amelyeket a felhasználók látni fognak a mobiloldalon. A rendelés, amelyhez hozzáadja őket, az a rendelés, amelyben a mezők megjelennek a végfelhasználó számára. A mezők sorrendjének megváltoztatása csak az összes mező újbóli kijelölésével lehetséges. A példánkban szereplő követelmények alapján a következő nyolc mező szükséges. Azonban egyes felhasználók úgy vélhetik, hogy nyolc mező mobileszközön túl sok információt jelent. Ezért csak a legfontosabb mezőket mutatjuk a mobillista-nézetben. A fennmaradó mezők a részletes nézetben jelennek meg, amelyet később fogunk megtervezni. Egyelőre a következő mezőket adjuk hozzá. Kattintson ezekben az oszlopokban a plusz jelre (**+**) a mobiloldalhoz való hozzáadáshoz.
    - Szállító neve
    - Számla összege
    - Számlafogadó
    - Számla száma
    - Számla dátuma

    A mezők felvétele után a mobiloldalnak az alábbi ábrához kell hasonlítania. 
    
    [![Az oldal mezők hozzáadása után.](./media/mobile-invoice-approvals03.png)](./media/mobile-invoice-approvals03.png)

9.  Most a következő oszlopokat is hozzá kell adnia, hogy később engedélyezni lehessen munkafolyamat-műveleteket.
    - Befejezett feladat megjelenítése
    - Delegált feladat megjelenítése
    - Visszahívási feladat megjelenítése
    - Elutasítási feladat megjelenítése
    - Kérésteljesítési feladat megjelenítése
    - Újraküldési feladat megjelenítése

10. Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.
11. Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.
12. A **Munkaterület közzététele** gombra kattintva mentse el a munkáját.
13. Engedélyezze a **Számla végösszegének megjelenítése a függő szállítói számlák listájában** funkciót a kötelezettségek paraméterei képernyő **Számla** részében. Vegye figyelembe, hogy ezen paraméter engedélyezésével a rendszer kiszámítja a számlaösszegeket, és ezek megjelennek meg a függőben lévő szállítói számlák listaoldalán. Ezt az új képességet az előre szükséges 3208224-es gyorsjavítás biztosítja.

### <a name="vendor-invoice-details"></a>Szállítói számla részletei

A számla részletei lap mobilra való megtervezéséhez használja a **VendMobileInvoiceHeaderDetails** oldalt. Fontos megjegyezni, hogy a rendszerben található számlák számától függően ezen a lapon a legrégebbi számla (az első létrehozott számla) jelenik meg. Adott számla megkereséséhez használja a bal oldali szűrőt. Ebben a példában viszont nincs szükségünk konkrét számlára. Csak némi számlaadatra van szükség ahhoz, hogy meg tudjuk tervezni a mobilos oldalt. 

[![Munkafolyamat oldal.](./media/mobile-invoice-approvals04-1024x425.png)](./media/mobile-invoice-approvals04.png)

1. Az URL-ben cserélje ki a menüelem nevét a **VendMobileInvoiceHeaderDetails** karakterláncra a képernyő megnyitásához

2. Nyissa meg a mobiltervezőt a **Beállítások** (fogaskerék) gombbal.

3. Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához.

4. Válassza ki a korábban létrehozott **Saját szállítói számlák** oldalt, majd kattintson a **Szerkesztés** elemre.

5. A **Mezők** lapon kattintson a **Rács** oszlop fejlécére.

6. Kattintson a **Tulajdonságok &gt; Oldal hozzáadása** elemre. **Megjegyzés:** amikor a **Rács** fejlécre kattint, és hozzáad egy oldalt, a részletek oldallal való kapcsolat automatikusan létrejön.

7. Adja meg a lap címét, például: **Számla részletei**, és egy leírást, például: **Számlafejléc és sor részleteinek megtekintése**.

8. Kattintson a **Mezők kijelölése** elemre. Ne feledje, hogy a rendelés, amelyhez hozzáadja őket, az a rendelés, amelyben a mezők megjelennek a végfelhasználó számára. A mezők sorrendjének megváltoztatása csak az összes mező újbóli kijelölésével lehetséges. 

9. Adja hozzá a példánkban szereplő követelmények alapján a következő mezőket a fejlécből:
   - Szállító neve
   - Számla összege
   - Számlafogadó
   - Számla száma
   - Számla dátuma
   - Számla leírása
   - Esedékes
   - Számla pénzneme

10. Az oldalon szereplő sorrácsból adja hozzá a következő mezőket:
    - Beszerzési kategória
    - Mennyiség
    - Egységár
    - Sor nettó összege
    - 1099-es összeg

11. Miután az előző két lépésből az összes mezőt hozzáadta, kattintson a **Kész** elemre. Az oldalnak az alábbi ábrához kell hasonlítania.
    
    [![További hozzáadott mezőket megjelenítő ábra.](./media/mobile-invoice-approvals05.png)](./media/mobile-invoice-approvals05.png)

12. Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.

13. Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.

14. A **Munkaterület közzététele** gombra kattintva mentse el a munkáját

### <a name="workflow-actions"></a>Munkafolyamat-műveletek

Munkafolyamat-műveletek hozzáadásához használja a **VendMobileInvoiceHeaderDetails** oldalt. Az oldal megnyitásához cserélje ki a menüpont nevét az URL-címben, mint korábban. Ezután nyissa meg a mobiltervezőt a **Beállítások** (fogaskerék) gombbal. Kövesse az alábbi lépéseket munkafolyamat-műveletek hozzáadásához a részletek oldalon. Olyan Önhöz rendelt számlákkal kell rendelkeznie, amelyek olyan megfelelő állapotban vannak, ami elérhetővé teszi azon munkafolyamat-műveleteket, amelyekhez felületet kíván tervezni.

#### <a name="record-workflow-actions"></a>Munkafolyamat-műveletek rögzítése
1.  Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához.
2.  Válassza a korábban elkészített **Számla részletei** oldalt, majd kattintson a **Szerkesztés** elemre.
3.  A **Műveletek** lapon kattintson a **Művelet hozzáadása** elemre.
4.  Adjon meg egy műveletcímet, például **Jóváhagyás**, és egy leírást, például a **Számla jóváhagyása**. Fontos megjegyezni, hogy a művelet itt megadott címe lesz a művelet neve, amit a felhasználó a mobilalkalmazásban látni fog.
5.  Kattintson a **Kész** gombra.
6.  Kattintson a **Mezők kijelölése** elemre.
7.  Menjen végig a munkafolyamaton a **VendMobileInvoiceHeaderDetails** oldalon, és végezze el a rögzíteni kívánt műveletet. Ügyeljen, hogy e folyamat során írjon be megjegyzéseket a munkafolyamathoz annak érdekében, hogy a megjegyzések mező is bekerüljön a mobilfelületre.
8.  A munkafolyamat-művelet futtatása után kattintson a **Kész** elemre a Mezőválasztás feladat elvégzéséhez.
9.  Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.
10. Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.
11. A **Munkaterület közzététele** gombra kattintva mentse el a munkáját
12. Ismételje meg az előző lépéseket az összes szükséges munkafolyamat-művelet rögzítéséhez. 

#### <a name="create-a-js-file"></a>.js fájl létrehozása
1. Nyissa meg a Jegyzettömböt vagy a Microsoft Visual Studio programot, és illessze be a következő kódot. Mentse a fájlt .js fájlként. Ez a kód a következőket hajtja végre:
    - Elrejti a korábban a mobil listaoldalon hozzáadott, a munkafolyamattal kapcsolatos további oszlopokat. Ezeket az oszlopokat azért adtuk hozzá, hogy az alkalmazás összefüggésben rendelkezzen az információkkal, és meg tudjuk tenni a következő lépést.
    - Az aktív munkafolyamat-lépés alapján logikát alkalmazva csak az érintett műveleteket jeleníti meg.

    > [!NOTE]
    > Az oldalak és más vezérlőelemek nevének a JS-kódban és a munkaterületen egyeznie kell.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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
    ```

2.  Töltse fel a kódfájlt a munkaterületre a **Logika** lap kiválasztásával
3.  Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.
4.  Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.
5.  A **Munkaterület közzététele** gombra kattintva mentse el a munkáját

### <a name="vendor-invoice-attachments"></a>Szállítói számlamellékletek

1. Kattintson a **Beállítások** (fogaskerék) gombra az oldal jobb felső sarkában, majd kattintson a **Mobilalkalmazás** elemre

2. Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához.

3. Válassza a korábban elkészített <strong>Számla részletei **oldalt, majd kattintson a Szerkesztés**</strong> elemre.

4. Állítsa a **Dokumentumkezelés** lehetőséget **Igen** értékre, ahogy az lent látható. **Megjegyzés:** ha a mellékleteket nem muszáj megjeleníteni a mobileszközön, a beállítást az alapértelmezett **Nem** értéken hagyhatja.
   
   ![Dokumentumkezelés.](./media/docmanagement-216x300.png)

5. Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.

6. Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.

7. A **Munkaterület közzététele** gombra kattintva mentse el a munkáját

### <a name="vendor-invoice-line-distributions"></a>Szállítói számlasorok felosztásai

E forgatókönyv követelményei megerősítik, hogy csak sorszintű felosztások lesznek jelen, és hogy a számláknak mindig csak egy soruk lesz. Mivel ez a forgatókönyv egyszerű, a felhasználói felületnek a mobileszközön szintén elég egyszerűnek kell lennie ahhoz, hogy a felhasználónak ne kelljen számos szinten végigásnia magát a felosztások megtekintéséhez. A szállítói számláknál az összes felosztás megjeleníthető a számlafejlécből. A mobilfelülethez erre a funkcióra van szükségünk. Ezért a **VendMobileInvoiceAllDistributionTree** lapot fogjuk használni a mobilfelület ezen részének megtervezéséhez. 

> [!NOTE] 
> A követelmények ismerete segít eldönteni, melyik adott oldalt használjuk, és pontosan hogyan optimalizáljuk a mobil felhasználói élményt a felület megtervezése során. A második forgatókönyv szerint másik oldalt fogunk használni a felosztások megjelenítésére, mivel ennek a forgatókönyvnek a követelményei eltérőek.

1.  Az URL-ben cserélje ki a menüpont nevét, mint korábban. A megjelenő lapnak az alábbi ábrához kell hasonlítania.

    [![Összes eloszlás oldal.](./media/mobile-invoice-approvals06.png)](./media/mobile-invoice-approvals06.png)

2.  Nyissa meg a mobiltervezőt a **Beállítások** (fogaskerék) gombbal.

3.  Kattintson a **Szerkesztés** gombra a munkaterület szerkesztési üzemmódjának elindításához. **Megjegyzés:** látni fogja, hogy két új oldal jön létre automatikusan. A rendszer ezeket az oldalakat azért hozza létre, mert az előző részben bekapcsolta a Dokumentumkezelést. Ezeket az új oldalakat figyelmen kívül hagyhatja.

4.  Kattintson az **Oldal hozzáadása** elemre.

5.  Adja meg az oldal címét, például **Könyvelés megtekintése**, és egy leírást, például a **Számla könyvelésének megtekintése**.

6.  Kattintson a **Kész** gombra.

7.  A **mezők** lapon kattintson a **Mezők kiválasztása** elemre, a felosztások lapon válassza a következő mezőket, és kattintson a **Kész** elemre:
    1.  Összeg
    2.  Pénznem
    3.  Főkönyvi számla

    > [!NOTE] 
    > A **Leírás** oszlopot nem választottuk ki a felosztások rácsból, mert ebben az esetben a követelmények megerősítik, hogy a kiterjesztett ár az egyetlen összeg, amelyhez felosztások lesznek elérhetők. Ezért a felhasználónak nem lesz másik mezőre szüksége ahhoz, hogy lássa, milyen típusú összegre vonatkozik a felosztás. A következő forgatókönyvben azonban **használni fogjuk** ezt az információt, mivel annak a forgatókönyvnek a követelményei azt mondják, hogy egyéb összegtípusokhoz (például áfához) is lesznek felosztások.

8.  Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.

9.  Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.

10. A **Munkaterület közzététele** gombra kattintva mentse el a munkáját

#### <a name="adding-navigation-to-view-accounting-page"></a>Navigálás hozzáadása a "Könyvelés megtekintése" oldalra

A **Könyvelés megjelenítése** mobillap jelenleg nem hivatkozik az általunk eddig megtervezett egyik mobillapra sem. Mivel a felhasználónak a mobilkészüléken el kell tudnia navigálnia a **Könyvelés megtekintése** oldalra a **Számla részletei** oldalról, navigációs lehetőséget kell biztosítanunk a **Számla részletei** oldalról a **Könyvelés megtekintése** oldalra. Ezt a navigációs lehetőséget további logika használatával hozzuk létre JavaScript segítségével.

1.  Nyissa meg a korábban létrehozott .js fájlt, és adja hozzá a következő kódban kiemelt sorokat. Ezt a kódot két dolgot tesz:
    1.  Ez segít garantálni, hogy a felhasználók közvetlenül a munkaterületről nem léphetnek a **Könyvelés megtekintése** oldalra.
    2.  Ez létrehoz egy navigációs vezérlőt a **Számla részletei** oldalról a **Könyvelés megtekintése** oldalra.

    > [!NOTE] 
    > Az oldalak és más vezérlőelemek nevének a JS-kódban és a munkaterületen egyeznie kell.

    ```javascript
    function main(metadataService, dataService, cacheService, $q) {
           return {
               appInit: function (appMetadata) {
                   // Hide controls that need to be present, but not visible
                   metadataService.configureControl('My-vendor-invoices', 'ShowAccept', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowApprove', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowReject', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowDelegate', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowRequestChange', { hidden: true });
                 metadataService.configureControl('My-vendor-invoices', 'ShowRecall', { hidden: true });
                   metadataService.configureControl('My-vendor-invoices', 'ShowComplete', { hidden: true });
               metadataService.configureControl('My-vendor-invoices', 'ShowResubmit', { hidden: true });
                   // Hide pages not applicable for root navigation
                   metadataService.hideNavigation('View-accounting');
                   //Link to view accounting
                   metadataService.addLink('Invoice-details', 'View-accounting', 'View-accounting-nav-control', 'View accounting', true);
               },
               pageInit: function (pageMetadata, params) {
        if (pageMetadata.Name == 'Invoice-details') {
                       // Show/hide workflow actions based on workflow step
                       metadataService.configureAction('Accept', { visible: true });
                       metadataService.configureAction('Approve', { visible: true });
                       metadataService.configureAction('Reject', { visible: true });
                       metadataService.configureAction('Delegate', { visible: true });
                       metadataService.configureAction('Request-change', { visible: true });
                       metadataService.configureAction('Recall', { visible: true });
                       metadataService.configureAction('Complete', { visible: true });
                       metadataService.configureAction('Resubmit', { visible: true });

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
    ```
    
2.  Az előző kód felülírásához töltse fel a kódfájlt a munkaterületre a **Logika** lap kiválasztásával
3.  Kattintson a **Kész** elemre a szerkesztés módból való kilépéshez.
4.  Kattintson a **Vissza**, majd a **Kész** elemre a munkaterületről való kilépéshez.
5.  A **Munkaterület közzététele** gombra kattintva mentse el a munkáját

### <a name="validation"></a>Ellenőrzés

A mobilkészüléken nyissa meg az alkalmazást, és csatlakozzon saját példányához. Ügyeljen, hogy abba a vállalatba jelentkezzen be, amelynél vannak szállítói számlák Önhöz rendelve véleményezésre. Ekkor elvileg el tudja elvégezni a következő műveleteket:

-   Nézze meg a **Jóváhagyásaim** munkaterület.
-   Jusson el a **Jóváhagyásaim** munkaterületre, és nézze meg a **Saját szállítói számlák** oldalt.
-   Jusson el a **Saját szállítói számlák** oldalra, és nézze meg az Önhöz hozzárendelt számlák listáját.
-   Lépjen be az egyik számlába, és nézze meg a számla fejlécadatait és a sor részleteit.
-   A részletek oldalon nézze meg a mellékletekre mutató hivatkozást, e hivatkozás segítségével lépjen a mellékletek listájára, és nézze meg a mellékleteket.
-   A részletek oldalon nézze meg a **Könyvelés megtekintése** oldalra mutató hivatkozást, e hivatkozás segítségével lépjen a felosztások oldalára, és nézze meg a felosztásokat.
-   A részletek oldalon kattintson a **Műveletek** menüre a lap alján, és hajtsa végre a munkafolyamat-lépésre vonatkozó munkafolyamat-műveleteket.

## <a name="designing-a-complex-invoice-approval-scenario-for-fabrikam"></a>Összetett számlajóváhagyási forgatókönyv tervezése a Gyár számára
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
<td>A számlafejléc mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</td>
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
<td>A számlasorok mely mezőit szeretné a felhasználó látni a mobil felületen, és milyen sorrendben?</td>
<td><ol>
<li>Beszerzési kategória</li>
<li>Mennyiség</li>
<li>Egységár</li>
<li>Sor nettó összege</li>
<li>1099-es összeg</li>
</ol></td>
</tr>
<tr class="odd">
<td>Hány számlasor van a számlán? Itt alkalmazza a 80-20-as szabályt, és optimalizáljon 80%-ra.</td>
<td>5</td>
</tr>
<tr class="even">
<td>A felhasználók akarnak könyvelési felosztásokat (számlakódolást) látni a mobileszközön ellenőrzések során?</td>
<td>Igen</td>
</tr>
<tr class="odd">
<td>Hány könyvelési felosztás (kiterjesztett ár, áfa, költségek stb.) van egy-egy számlasornál? Ismételten alkalmazza a 80-20-as szabályt.</td>
<td>Kiterjesztett ár: 2 áfa: 2 költség: 2</td>
</tr>
<tr class="even">
<td>A számlák szintén rendelkeznek könyvelési felosztásokkal a számla fejlécében? Ha igen, e könyvelési felosztásoknak rendelkezésre kell állniuk a készüléken?</td>
<td>Nincs használatban</td>
</tr>
<tr class="odd">
<td>A felhasználók látni szeretnék a számlához tartozó mellékleteket az eszközön?</td>
<td>Igen</td>
</tr>
</tbody>
</table>

### <a name="next-steps"></a>További lépések

A következő változatok elvégezhetők az 1. forgatókönyvhöz a 2. forgatókönyv követelményei alapján. Ez a szakasz a mobilalkalmazás felhasználói élményének fokozására használható.

1.  Mivel a 2. forgatókönyvben több számlasor szükséges, a terv következő módosításai segítenek a mobileszközön a felhasználói élmény optimalizálásában:
    1.  Számlasorok a részletek oldalon történő megjelenítése helyett (mint az 1. forgatókönyvben), a felhasználók itt dönthetnek úgy, hogy a sorokat külön mobiloldalon tekintik meg.
    2.  Mivel ebben a forgatókönyvben több számlasor szükséges, ha a **VendMobileInvoiceAllDistributionTree** oldalt használjuk a felosztási oldal megtervezéséhez a mobilon (mint az 1. forgatókönyvnél), a felhasználó számára a sorok és a felosztások megfeleltetése nehéz feladat lehet. Ezért használja a **VendMobileInvoiceLineDistributionTree** oldalt a felosztások oldalának megtervezéshez.
    3.  Ideális esetben ennél a forgatókönyvnél a felosztások egy számlasor kontextusában jelennek meg. Ezért győződjön meg arról, hogy a felhasználó eljuthat a kívánt sorig a felosztások oldal megtekintéséhez. Hivatkozzon az oldalra az útvonal létrehozásához, mint ahogyan a fejlécnél és a részletező oldalnál tette az 1. forgatókönyvben.

2.  Mivel a 2. forgatókönyvben egynél több összegtípus várható a felosztások között (áfa stb.), hasznos lesz megjeleníteni az összeg leírását. (Ezt az információt az 1. esetben kihagytuk.)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
