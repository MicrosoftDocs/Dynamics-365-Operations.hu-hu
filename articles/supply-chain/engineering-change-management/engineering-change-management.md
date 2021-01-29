---
title: A mérnöki termékek módosításának kezelése
description: Ez a témakör a mérnöki változtatás kezeléséről nyújt tájékoztatást. A mérnöki változtatás kezelése strukturált folyamatokat biztosít a mérnöki termékek változásainak kezeléséhez, a javaslattételtől, a kéréstől és a módosítások végrehajtásától kezdve a módosítások áttekintésén és jóváhagyásán, valamint a meglévő tranzakciókra gyakorolt hatásuk felmérésén át, azok nyomon követéséig.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 314563e083434832ee04d9c19deb17cec221ae02
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4429975"
---
# <a name="manage-changes-to-engineering-products"></a>A mérnöki termékek módosításának kezelése

[!include [banner](../includes/banner.md)]

A mérnöki változtatáskezelés strukturált folyamatokat biztosít a mérnöki termékek változtatásainak kezeléséhez. A *mérnöki módosítási kérelem* folyamat segítségével javasolhat és kérhet módosításokat, majd a *mérnöki módosítási rendelés* folyamatával ténylegesen végrehajthatja ezeket a módosításokat. A felhasználók létrehozhatnak mérnöki módosítási kérelmeket vagy mérnöki módosítási rendeléseket, majd van egy folyamat azok áttekintésére és jóváhagyására, a meglévő tranzakciókra gyakorolt hatásuk felmérésére és nyomon követésére.

## <a name="engineering-change-requests"></a>Tervezési módosítási kérelmek

A mérnöki módosítási kérelem folyamat lehetővé teszi a vállalat összes érintett részlegétől származó módosítási kérelmek rögzítését. Nem számít, hogy mérnökként, vagy a gyártási, beszerzési, raktári vagy értékesítési részlegen dolgozik: bárki használhatja a mérnöki módosítási kérelmet a módosítás kéréséhez. Ez a változtatás lehet egy új termék ötlete, egy már létező termékkel, egy létező termék tökéletesítésével vagy valami mással kapcsolatos javaslat.

Miután valaki elküldte a módosítás iránti kérelmet, a *felülvizsgálati és jóváhagyási* folyamatot egy munkafolyamat kezeli, amely azonosítja, hogy kinek kell jóváhagynia a módosítást (például a termék tulajdonosa).

Ha be szeretné állítani a mérnöki módosítási rendelések vagy a mérnöki módosítási kérelmek munkafolyamatát, nyissa meg a **Mérnöki módosítások kezelése \> Mérnöki munkafolyamatok** részt. Válassza az **Új** lehetőséget, válassza ki, hogy a munkafolyamatot a mérnöki módosítási rendelések vagy a mérnöki módosítási kérelmek áttekintésére használja-e, majd konfigurálja a munkafolyamatot.

További tájékoztatás a munkafolyamatok használatáról: [A munkafolyamat-rendszer áttekintése](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md). A terméktulajdonosokkal kapcsolatos további tudnivalókat lásd a [Terméktulajdonosok](product-owner.md) részben.

### <a name="create-a-new-engineering-change-request"></a>Új tervezési változáskezelési kérelem létrehozása

Egy mérnöki módosítási kérelem létrehozásához kövesse az alábbi lépéseket.

- Nyissa meg a **Mérnöki módosítások kezelése \> Általános \> Mérnöki módosítások kezelése \> Mérnöki módosítási kérelmek** elemet, majd válassza az **Új** parancsot a műveleti ablaktáblán.
- Nyissa meg egy létező mérnöki termék **Termék részletes adatai** oldalát. Ezután a művelet panel **Mérnök** lapjának **Mérnöki módosítások kezelése** csoportjában válassza a **Mérnöki módosítási kérés \> Új mérnöki módosítási kérés** lehetőséget.

Új módosítási kérelem jön létre. Ezután minden Gyorslapon beállíthatja a mezőket a következő alszakaszokban leírtaknak megfelelően.

#### <a name="general-fasttab"></a>Általános gyorslap

Az **Általános** gyorslap segítségével megadhatja a módosítási kérelem alapvető leírását. Az alábbi táblázat ismerteti az ezen a gyorslapon elérhető mezőket.

| Mező | Leírás |
|---|---|
| Módosítási kérelem | Adjon egy nevet a mérnöki módosítási kérésnek. |
| Megszólítás | Adja meg azt a szöveget, amely röviden leírja vagy azonosítja a kérelem változásait. |
| Prioritás | Egy érték kiválasztásával jelezze, hogy milyen magas a változás prioritása. Igény szerint testreszabhatja a vállalat számára elérhető értékeket. (További tájékoztatás: [Közös értékek meghatározása mérnöki módosításokhoz](engineering-change-management-setup.md).) |
| Kategória | Egy érték kiválasztásával ismertesse a kért módosítás típusát. Igény szerint testreszabhatja a vállalat számára elérhető értékeket. (További tájékoztatás: [Közös értékek meghatározása mérnöki módosításokhoz](engineering-change-management-setup.md).) |
| Súlyosság | Válassza ki azt az értéket, amely azt jelzi, hogy milyen súlyosságú probléma javítható ki a kérelem megvalósításával. Igény szerint testreszabhatja a vállalat számára elérhető értékeket. (További tájékoztatás: [Közös értékek meghatározása mérnöki módosításokhoz](engineering-change-management-setup.md).) |
| Kérelmező | A kérelmet létrehozó felhasználó neve. |
| Hely | A kérés létrehozásának dátuma. |
| Állapot | A kérelem állapota. A kérelem első létrehozásakor a *Létrehozva* állapot jön létre. A kérelem jóváhagyása után az állapot *Jóváhagyott* értékre változik. Ha a kérelemhez létrejön egy kapcsolódó módosítási rendelés, az állapot *Nyomon követett* értékre változik. |
| Módosítási utasítás | A módosítási rendelés száma, ha a módosítási kérelmet egy módosítási rendelésen keresztül követték. |

#### <a name="information-fasttab"></a>Információk gyorslap

Az **Információk** gyorslap a kérelemmel kapcsolatos további információk megadását teszi lehetővé.

Ha sort szeretne hozzáadni a rácshoz, válassza a rács fölötti eszköztár **Új** elemét, majd válasszon a következő lehetőségek közül:

- **Fájl** – Fájl feltöltése.
- **Kép** – Képfájl feltöltése.
- **Megjegyzés** – Megjegyzés beírása közvetlenül a rácsba.
- **URL** – URL beírása közvetlenül a rácsba.

Az alábbi táblázat ismerteti az egyes sorokban elérhető mezőket.

| Mező | Leírás |
|---|---|
| Létrehozás dátuma és időpontja | A sor létrehozásának dátuma és ideje. |
| Típus | Annak az információnak a típusa, amelyre sor jött létre (fájl, kép, megjegyzés vagy URL-cím). |
| Leírás | Írja be a sor leírását. |
| Korlátozás | Érték, amely azt jelzi, hogy a hozzáadott adatok belső vagy külső forrásból származnak-e. |
| Csatolt | A jelölőnégyzet bejelölése azt jelzi, hogy a sor tartalmaz egy mellékletet (fájl vagy kép). A melléklet letöltéséhez válassza ki a sort, majd válassza a **Megnyitás** lehetőséget a rács fölötti eszköztárból. |

#### <a name="products-fasttab"></a>Termékek gyorslap

A **Termékek** gyorslap a módosítás iránti kérelem által érintett valamennyi termék felsorolását teszi lehetővé. Az eszköztár gombjaival hozzáadhat termékeket a rácshoz, illetve eltávolíthatja a termékeket.

Ez a lista csak tájékoztatásra szolgál. Ezért tetszőleges mennyiségű kapcsolódó terméket hozzáadhat. Ha egy meglévő termék **Termék részletei** lapjáról hoz létre módosítási kérést, akkor a terméknek a **Termékek** gyorslapon felsorolva kell lennie, miután mentette a kérelem rekordját.

#### <a name="source-fasttab"></a>Forrás gyorslap

A **Forrás** gyorslap segítségével nyomon követheti a módosítási kérelem kezdőpontját. Ez például akkor lehet hasznos, ha látni szeretné, hogy a módosítás iránti kérelem egy értékesítési rendelésből jött-e létre, ki hozta létre, és melyik vállalatban jött létre.

### <a name="evaluate-the-business-impact-of-a-change-request"></a>Módosítási kérelem üzleti hatásának kiértékelése

A módosítás iránti kérelem felülvizsgálatakor lehetőség van a függőségek megkeresésére. Ily módon mérhető a kért módosítás hatása a nyitott tranzakciókra, például az értékesítési rendelésekre, a termelési rendelésekre és az aktuális készletre.

1. Lépjen a **Mérnöki változtatások kezelése \> Általános \> Mérnöki változtatások kezelése \> Mérnöki változtatási kérelmek** lehetőségre.
1. Nyisson meg egy meglévő módosítási kérést, vagy új módosítási kérés létrehozásához válassza az **Új** parancsot a műveleti ablaktáblán.
1. A műveleti ablak **Módosítási kérés** lapjának **Üzleti hatás** csoportjában válassza a következő gombok egyikét:

    - **Keresés** – az összes nyitott tranzakciót megvizsgálja, majd megnyitja az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanelt, amely felsorolja azokat a tranzakciókat, amelyekre a módosítás hatással lesz.
    - **Előző keresés megtekintése** – megnyitja az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanelt, amely felsorolja az előző keresés eredményét. (Az új keresés nem történt meg.)

1. Ha a módosítást igénylő kiadás kritikus, akkor zárolhatja a nyitott tranzakciókat, vagy az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanel eszközsávjának gombjaival értesítheti a felelős felhasználót.

### <a name="create-a-change-order-from-a-change-request"></a>Módosítási rendelés létrehozása módosítási kérelemből

A mérnöki módosítások iránti kérelem áttekintését végző mérnök egy mérnöki módosítási rendelést hozhat létre közvetlenül a **Mérnöki módosítási kérelmek** oldalról. A Művelet ablaktábla **Módosítási kérés** lapjának **Mérnöki módosítási rendelés** csoportjában válassza a **Hivatkozás és termékek másolása** elemet.

## <a name="engineering-change-orders"></a>Tervezési módosítási utasítások

A mérnöki módosítási rendelések strukturált folyamatot biztosítanak a mérnöki termékek változtatásainak kezeléséhez. A változtatásokat a mérnöki szempontból releváns adatok egy példányának használatával javasolhatja. A valódi alapadatok nem érintettek. A mérnöki szempontból releváns adatokkal kapcsolatos további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).

Létrehozhat egy mérnöki módosítási rendelést, amely a jóváhagyott mérnöki módosítási kérésen alapul. A mérnökök elölről is létrehozhatnak mérnöki módosítási rendeléseket. Több terméket is belefoglalhat egyetlen mérnöki módosítási rendelésbe a következő lépések bármelyikével:

- Termékek kézi kiválasztása.
- Az anyagjegyzék (AJ) használatával a termékstruktúrában alább elhelyezkedő termékek (azaz gyermekek) belefoglalásához.
- Egy használati hely keresés segítségével foglalhat bele a termékstruktúrában magasabban elhelyezkedő (azaz a szülő) termékeket.

A módosítási javaslat befejezése után egy munkafolyamat fogja kezelni a felülvizsgálati és jóváhagyási folyamatot. A különböző munkafolyamatok a prioritás és a súlyosság alapján állíthatók be.

Ha be szeretné állítani a mérnöki módosítási rendelések vagy a mérnöki módosítási kérelmek munkafolyamatát, nyissa meg a **Mérnöki módosítások kezelése \> Mérnöki munkafolyamatok** részt. Válassza az **Új** lehetőséget, válassza ki, hogy a munkafolyamatot a mérnöki módosítási rendelések vagy a mérnöki módosítási kérelmek áttekintésére használja-e, majd konfigurálja a munkafolyamatot.

További tájékoztatás a munkafolyamatok használatáról: [A munkafolyamat-rendszer áttekintése](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

Íme néhány tipikus érdekelt fél, akiknek előfordulhat, hogy a mérnöki módosítási rendelést jóvá kell hagyniuk:

- **Terméktulajdonosok** – A terméktulajdonosokkal kapcsolatos további tudnivalókat lásd a [Terméktulajdonosok](product-owner.md) részben.
- **Felelős csapatvezető** – Azt is vegye figyelembe, hogy a mérnöki módosítási rendelés **Fejléc** nézetének **Mérnök** mezőjében az a mérnök látható, aki létrehozta a mérnöku módosítási rendelést. Ha a mérnök a rendszerben definiált csapathoz tartozik, akkor a **Felelős** mező a csapat vezetőjét jeleníti meg.
- **Pénzügyi osztály** – Előfordulhat, hogy a pénzügyi osztálynak ellenőriznie kell azokat az eseteket, amelyekben a változás magas költségekkel jár.

Megadhatja, hogy a mérnöki módosítási rendelést közvetlenül a jóváhagyása után kell feldolgozni, a munkafolyamat részeként, illetve hogy a feldolgozást később, kézi lépésként kell végrehajtani. Egy mérnöki módosítási rendelés feldolgozásakor a program frissíti a tényleges termék műszaki adatait.

A módosítás iránti kérelem megtekintése közben a művelet ablaktáblán, a **Módosítási kérés** lap **Üzleti hatás** csoportjában válassza a **Keresés** lehetőséget, ha a javasolt módosítás hatását szeretné értékelni a nyitott tranzakciókra, például az értékesítési rendelésekre, a termelési rendelésekre és az aktuális készletre. Az eredmények az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanelen jelennek meg, ahol kiválaszthatja a kívánt tranzakciókat, majd az eszköztár parancsaival további információkat jeleníthet meg, értesítheti a felelős felhasználót vagy zárolhatja a tranzakciót.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Mérnöki vagy üzemeltetési vállalatok mérnöki változtatási rendelései

Amint az a [Mérnöki vállalatok és az adatok tulajdonlásának szabályai](engineering-org-data-ownership-rules.md) részben bemutatásra került, a módosítható termékadatok attól függően változnak, hogy milyen típusú jogi személyben dolgozik (egy mérnöki vállalat vagy egy üzemeltető vállalat). Az adattulajdonlási szabályok a mérnöki módosítási rendelésekre is vonatkoznak. Ennek megfelelően attól függően, hogy milyen jogi személyben hoz létre a mérnöki módosítási rendelés, különböző típusú változtatásokat lehet végrehajtani. Íme néhány példa:

- A **mérnöki vállalatok** mérnöki módosítási rendelései esetében alapvető változtatásokat lehet végezni a mérnöki adatokon. Létrehozhat például új termékverziókat, módosíthatja a termék szerkezetét az anyagjegyzéken keresztül, valamint módosíthatja a mérnöki attribútumok értékeit. Minden érintett terméknél válassza a következő értékek egyikét a **Hatás** mezőben:

    - **Nincs** – a létező termék verziójának frissítése (verzión belüli frissítés).
    - **Új verzió** – hozzon létre egy új verziót, amely a kiválasztott termékverzión alapul.
    - **Új termék** – hozzon létre egy teljesen új terméket vagy termékváltozatot, amely a kiválasztott termékverzión alapul.

- Egy **operatív vállalat** mérnöki módosítási rendeléseihez módosíthatja a termék logisztikai adatait. Bővítheti például a meglévő anyagjegyzéket a beszerzés, a helyi útvonalak és a helyi anyagjegyzékek hozzáadásával, valamint az anyagjegyzéket akár úgy is bővítheti, hogy új anyagjegyzék-sorokat ad hozzá a helyi csomagolási anyagok, kenőanyagok vagy a helyi nyelvű utasítások számára. Az operatív vállalat felhasználói által végzett bővítések megmaradnak, amikor a mérnöki vállalat új frissítéseket küld. További tájékoztatás: [Mérnöki vállalatok és az adatok tulajdonlásának szabályai](engineering-org-data-ownership-rules.md).

    Amikor a mérnöki rendeléseket a mérnöki vállalatban dolgozzák fel, a termékeket csak a mérnöki vállalatnál lehet létrehozni és/vagy frissíteni. Ha tehát a termék alapadatainak frissítésére is szükség van, akkor a termékeket az operatív vállalatok számára is ki kell adnia.

- A termékeket közvetlenül a mérnöki módosítási rendelésekből is kiadhatja. Nyissa meg a módosítási rendelést, majd a művelet ablaktábla **Módosítási rendelés** lapjának **Termékkiadások** csoportjában válassza ki a **Termékszerkezet kiadása lehetőséget**. A folyamat ugyanúgy működik, mint amikor a termékeket a **Kiadott termékek** lapról adja ki. További információért lásd: [Termékstruktúrák kiadása](release-product-structure.md)
- A termékeket a következő tényezők alapján lehet automatikusan kiadni a mérnöki módosítási rendelésekből:

    - Újbóli kiadás azoknak a vállalatoknak, amelyeknek a termékeket korábban kiadták. Válassza a **Keresés** parancsot az összes korábbi kiadás vizsgálatához, majd válassza a **Nézet** lehetőséget az eredmények megtekintéséhez. A **Nézet** oldal megjeleníti az előző termékkiadásokat, és kiválaszthatja, hogy mely termékeket kívánja újra kiadni. Ezt követően zárja be a **Nézet** oldalt, majd válassza a **Feldolgozás** lehetőséget a kiválasztott termékek ismételt kiadásához.
    - Automatikus kiadási beállítások a mérnöki termékkategória kiadási ellenőrzésében. Ezt a kiadást a munkafolyamat részeként teheti meg. A **kiadási javaslat összegyűjtése** blokk használatakor a kiadási javaslat újrakiadási javaslatokkal (lásd az előző listaelemet) kerül feltöltésre, és a termékek kiadásra kerülnek a vállalatoknak, ha az **Automatikus kiadás** jelölőnégyzet be van jelölve a mérnöki termékkategória kiadási szabályozásában. Az eredmények megtekintéséhez válassza ki a **Nézet** elemet az előző részben írt módon. A termékek a **kiadási javaslat feldolgozása** blokk használatakor is kiadja a program. Ha úgy dönt, hogy a kiadási javaslatot a munkafolyamat részeként csak begyűjti, akkor a kiadást manuálisan is indíthatja a **Feldolgozás** lehetőséget kiválasztva a korábbi listaelemben leírtak szerint.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Egy mérnöki módosítási kérelem nyomon követése egy mérnöki módosítási rendelésen keresztül

Amint a mérnöki módosítási kérelmet jóváhagyták, azonnal folytathatja egy mérnöki módosítási rendeléssel. Több mérnöki módosítási kérelmet egyesíthet egyetlen mérnöki módosítási rendelésben. Egyetlen mérnöki módosítási rendelés akár több terméket is tartalmazhat. (Ez a módszer általában akkor használatos, ha ugyanaz a módosítás több termékre is érvényes.) Azonban egyetlen mérnöki módosítási kérelemből nem lehet több mérnöki módosítási rendelést létrehozni.

Ha módosítási rendelésen keresztül szeretné nyomon követni a módosítási kérést, nyissa meg a módosítási kérést, majd a művelet ablak **Módosítási rendelés** lapjának **Mérnöki módosítási rendelés** csoportjában válassza a **Hivatkozás és termékek másolása** lehetőséget. Ezután ki lehet választani egy meglévő mérnöki módosítási rendelést a módosítási kérelem csatlakoztatásához, vagy új mérnöki módosítási rendelést hozhat létre a megadott kéréshez.

## <a name="engineering-change-order-report"></a>Tervezési módosításkérési jelentés

A mérnöki módosítási rendelés jelentései leírják a mérnöki módosítási rendelésben elvégzett változtatásokat. Ezek a felülvizsgálati és jóváhagyási folyamat során és azt követően egyaránt hasznosak.

Ha meg szeretné tekinteni egy mérnöki módosítási rendelés jelentését, nyissa meg a megfelelő módosítási rendelést, majd a művelet ablaktábla **Módosítási rendelés** lapjának **Nézet** csoportban válassza a **Mérnöki módosítási rendelés jelentése** lehetőséget.

## <a name="fields-on-an-engineering-change-order"></a>Mérnöki módosítási rendelés mezői

A mérnöki módosítási rendelések legtöbb mezője ugyanaz, mint a kiadott termékek, a mérnöki verziók, a dokumentumok, az anyagjegyzékek (sorok) és az útvonalak (műveletek) mezői. A következő táblázatban szereplő mezők azonban egyediek a módosítási rendelések esetében.

| Mező | Leírás |
|---|---|
| Tervezési módosítás okai | Válassza ki az érintett termék módosításának okát. |
| Módosítás leírása | Adja meg a módosítás leírását. |
| Szükséges speciális eszközök | Adja meg, hogy szükség van-e speciális szerszámozásra a módosítás alkalmazásához. |
| Mérnöki anyagok kiosztása | Válassza ki a módosítás alkalmazásakor termelt hulladékhoz tartozó anyagkiosztási kódot. |
| Az ügyfél jóváhagyása szükséges | Adja meg, hogy a módosítás alkalmazása előtt kötelező-e a vevői jóváhagyás. |
| Megszerzett ügyféljóváhagyás | Adja meg a vevői jóváhagyás állapotát. |
| Környezet-, egészség- és munkavédelem | Adja meg, hogy a módosításra vonatkozó környezet-, egészség- és munkavédelmi szabályok érvényesek-e. Ilyen esetben a megfelelő szabályokat is kiválaszthatja. |

A módosítási információk az érintett termékek között másolhatók a **Módosítás adatainak karbantartása és másolása** gomb segítségével.