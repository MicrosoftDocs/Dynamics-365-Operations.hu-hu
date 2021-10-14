---
title: A mérnöki termékek módosításának kezelése
description: Ez a témakör a mérnöki változtatás kezeléséről nyújt tájékoztatást. A mérnöki változtatás kezelése strukturált folyamatokat biztosít a mérnöki termékek változásainak kezeléséhez, a javaslattételtől, a kéréstől és a módosítások végrehajtásától kezdve a módosítások áttekintésén és jóváhagyásán, valamint a meglévő tranzakciókra gyakorolt hatásuk felmérésén át, azok nyomon követéséig.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f362aef527272781464d5c1a17f0a382cfb8cacc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568135"
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

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>A módosítási kérelmek és az értesítésküldések üzleti hatásának kiértékelése

A módosítás iránti kérelem felülvizsgálatakor lehetőség van a függőségek megkeresésére. Ily módon mérhető a kért módosítás hatása a nyitott tranzakciókra, például az értékesítési rendelésekre, a termelési rendelésekre és az aktuális készletre. A módosítási kérelmek áttekintése során értesítést küldhet a kapcsolódó rendelések különböző típusainak teljesítéséért felelős személyeknek.

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>Az érintett tranzakciók áttekintése, a kijelölt tranzakciók blokkolása és értesítések küldése

Az érintett tranzakciók áttekintéséhez, a kijelölt tranzakciók blokkolásához és az értesítések küldéséhez hajtsa végre az alábbi lépéseket.

1. Lépjen a **Mérnöki változtatások kezelése \> Általános \> Mérnöki változtatások kezelése \> Mérnöki változtatási kérelmek** lehetőségre.
1. Nyisson meg egy meglévő módosítási kérést, vagy új módosítási kérés létrehozásához válassza az **Új** parancsot a műveleti ablaktáblán.
1. A műveleti ablak **Módosítási kérés** lapjának **Üzleti hatás** csoportjában válassza a következő gombok egyikét:

    - **Keresés** – az összes nyitott tranzakciót megvizsgálja, majd megnyitja az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanelt, amely felsorolja azokat a tranzakciókat, amelyekre a módosítás hatással lesz.
    - **Előző keresés megtekintése** – megnyitja az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanelt, amely felsorolja az előző keresés eredményét. (Az új keresés nem történt meg.)

1. Az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanelen lévő lapokon adott típusba tartozó érintett tranzakciók listája látható (**Értékesítési rendelések**, **Beszerzési rendelések**, **Termelési rendelések**, **Készlet**, stb.). Minden lapon látható, hogy hány érintett tranzakció tartozik az adott típusba. A megfelelő lista megtekintéséhez lépjen egy lapra.
1. A listán lévő tranzakció használatához jelölje ki az elemet, majd válassza ki az eszköztáron a következő gombok valamelyikét:

    - **Tranzakció megtekintése** – a kiválasztott tranzakciórekord megnyitása.
    - **Rendelés zárolása** – ez a gomb csak az **Értékesítési rendelések** lapon érhető el. A gombbal zárolhatja a kijelölt értékesítési rendelést.
    - **Sor zárolása** – ez a gomb csak a **Beszerzési rendelések** lapon érhető el. A gombbal zárolhatja a beszerzési rendelés kijelölt sorát.
    - **Felelős értesítése** – ez a gomb csak az **Értékesítési rendelések** lapon érhető el. A használatával értesítést küldhet a kiválasztott értékesítési rendelésnél felelősként beállított felhasználónak. További információt arról, hogy ki és hogyan láthatja az értesítéseket, a [Tranzakciókhoz tartozó módosítási értesítések áttekintése és feldolgozása](#review-notifications) című témakörben talál.
    - **Megrendelő értesítése** – ez a gomb csak az **Beszerzési rendelések** lapon érhető el. A használatával értesítést küldhet a kiválasztott beszerzési rendelésnél beállított megrendelőnek. További információt arról, hogy ki és hogyan láthatja az értesítéseket, a [Tranzakciókhoz tartozó módosítási értesítések áttekintése és feldolgozása](#review-notifications) című témakörben talál.
    - **Termelés értesítése** – ez a gomb csak a **Termelési rendelések** lapon érhető el. Az értékesítési és a beszerzési rendelésektől eltérően a termelési rendelések esetében nincsen egyetlen olyan felhasználó, aki be lenne állítva a teljes rendeléshez felelősként. Ehelyett általában a különböző felügyelők vagy tervezők tulajdonában van egy adott hely vagy a termelés adott része (például konkrét erőforrások vagy erőforráscsoportok). Ennek megfelelően a gombra kattintás után minden olyan felhasználó, aki felelős a kiválasztott termelési rendeléshez kapcsolódó valamelyik erőforrásért, értesítést kap a módosításról. További információt arról, hogy ki és hogyan láthatja az értesítéseket, a [Tranzakciókhoz tartozó módosítási értesítések áttekintése és feldolgozása](#review-notifications) című témakörben talál.
    - **Készítő értesítése** – ez a gomb csak az **Beszerzési igénylés** lapon érhető el. A használatával értesítést küldhet a kiválasztott beszerzési igénylésnél beállított készítőnek. További információt arról, hogy ki és hogyan láthatja az értesítéseket, a [Tranzakciókhoz tartozó módosítási értesítések áttekintése és feldolgozása](#review-notifications) című témakörben talál.
    - **Értékesítési felelős értesítése** – ez a gomb csak az **Árajánlatok** lapon érhető el. A használatával értesítést küldhet a kiválasztott értékesítési rendelésnél felelősként beállított felhasználónak. További információt arról, hogy ki és hogyan láthatja az értesítéseket, a [Tranzakciókhoz tartozó módosítási értesítések áttekintése és feldolgozása](#review-notifications) című témakörben talál.
    - **Selejt** – ez a gomb csak a **Készlet** lapon érhető el. A használatával a kiválasztott készletet selejtezheti le.
    - **Előzmények megtekintése** – a kijelölt tranzakcióval kapcsolatos műveletek előzményeinek megnyitása az **Üzleti hatások a nyitott tranzakciókra** párbeszédpanelen. (Az előzményekben például látható, hogy az értesítések el lettek-e küldve, vagy a tranzakciók zárolva lettek-e.) 
    - **Az összes tranzakció megjelenítése** – az összes tranzakciót (nem csak a nyitottakat) tartalmazó lista megnyitása.

> [!IMPORTANT]
> A **Termelés értesítése** gomb csak akkor érhető el, ha a *Tervezési értesítések termeléshez* funkció be van kapcsolva a rendszerben. További utasításokat a [Tervezési változtatáskezelés – áttekintés](product-engineering-overview.md) részben talál.

#### <a name="review-and-process-change-notifications-for-transactions"></a><a name="review-notifications"></a>A tranzakciók értesítéseinek áttekintése és feldolgozása

A kapott módosítási értesítéseket a következőképpen olvashatja át és dolgozhatja fel:

- A termelési rendelések kivételével az olyan módosítási értesítések, amelyek esetében Ön a felelős, a Műveletközpontban jelennek meg. A navigációs sáv jobb oldalán található **Üzenetek megjelenítése** gomb (harang szimbólum) jelzi, ha Műveletközpontban Önnek szóló üzenet látható. Az **Üzenetek megjelenítése** gombbal nyithatja meg a Műveletközpontot az üzenetek megtekintéséhez.
- Az összes olyan termelési rendelés, amelyhez tervezési értesítés lett kiküldve, a **Termelési rendelések \> Termelési rendelések \> Minden termelési rendelés** részen tekinthető meg. A Műveleti panel **Termelési rendelés** lapján lévő **Tervezési módosítási kérelem** csoportban válassza a **Tervezési értesítések** elemet a **Tervezési értesítések** oldal megnyitásához.
- Termelési rendelések esetén kiválaszthatja, hogy csak az Ön által kezelt termelési erőforrásokra vonatkozó módosítási értesítéseket szeretné-e áttekinteni. A Műveleti panel **Termelési szint kezelése** munkaterületén lévő **Munkaterület konfigurálása** lehetőség kiválasztásával úgy szűrheti az oldalt, hogy csak az Ön által kezelt termelési egységekre, csoportokra és/vagy erőforrásokra vonatkozó adatok jelenjenek meg. Az **Összegzés** szakaszban lévő **Módosított termékekkel rendelkező termelési rendelések** csempén látható a megadott szűrőbeállításoknak megfelelő értesítések száma. A csempe kiválasztásával megnyithatja a **Tervezési értesítések** lapot, amelyen megtekintheti a szűrő feltételeinek megfelelő tranzakciók teljes listáját.

A termelési rendelés értesítéseinek **Tervezési értesítések** oldalon történő áttekintése során követheti a kapcsolódó változási vagy termelési rendelésekre mutató hivatkozásokat. Ehhez válassza ki az oszlop értékeit vagy a kapcsolódó parancsokat a Művelet panelen. Miután befejezte a módosítások kiértékelét, és miután igény szerint visszavonta vagy módosította a termelési rendeléseket, az értesítéseket megjelölheti megoldottként. Válassza ki az értesítést, majd a Művelet panelen válassza a **Megoldás** lehetőséget. Az értesítést az összes felhasználó nézetéből eltávolítja a rendszer.

> [!IMPORTANT]
> A termelési rendelésekre vonatkozó értesítések küldésének lehetősége megköveteli, hogy a *Tervezési értesítések termeléshez* funkció be legyen kapcsolva a rendszerben. További utasításokat a [Tervezési változtatáskezelés – áttekintés](product-engineering-overview.md) részben talál.

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

- A *mérnöki vállalatok* mérnöki módosítási rendelései esetében alapvető változtatásokat lehet végezni a mérnöki adatokon. Létrehozhat például új termékverziókat, módosíthatja a termék szerkezetét az anyagjegyzéken keresztül, valamint módosíthatja a mérnöki attribútumok értékeit. Minden érintett terméknél válassza a következő értékek egyikét a **Hatás** mezőben:

    - **Nincs** – a létező termék verziójának frissítése (verzión belüli frissítés).
    - **Új verzió** – hozzon létre egy új verziót, amely a kiválasztott termékverzión alapul.
    - **Új termék** – hozzon létre egy teljesen új terméket, amely a kiválasztott termékverzión alapul.
    - **Új változat** – hozzon létre egy új változatot, amely a kiválasztott termékverzión alapul. Az anyagjegyzékre és útvonalra vonatkozó adatok át lesznek másolva.

- Egy *operatív vállalat* mérnöki módosítási rendeléseihez módosíthatja a termék logisztikai adatait. Bővítheti például a meglévő anyagjegyzéket a beszerzés, a helyi útvonalak és a helyi anyagjegyzékek hozzáadásával, valamint az anyagjegyzéket akár úgy is bővítheti, hogy új anyagjegyzék-sorokat ad hozzá a helyi csomagolási anyagok, kenőanyagok vagy a helyi nyelvű utasítások számára. Az operatív vállalat felhasználói által végzett bővítések megmaradnak, amikor a mérnöki vállalat új frissítéseket küld. További tájékoztatás: [Mérnöki vállalatok és az adatok tulajdonlásának szabályai](engineering-org-data-ownership-rules.md).

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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
