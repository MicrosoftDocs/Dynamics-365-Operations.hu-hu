---
title: Beérkezés áttekintése
description: Ez a témakör a Beérkezés áttekintése funkcióival kapcsolatban tartalmaz tájékoztatást. A funkció része a Beérkezés áttekintése lap, és minden, várhatóan beérkező cikk áttekintését nyújtja.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 89f885cbbe6a5001b507cd9fb1516733f8faee0f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005277"
---
# <a name="arrival-overview"></a>Beérkezés áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör a Beérkezés áttekintése funkcióival kapcsolatban tartalmaz tájékoztatást. A funkció része a Beérkezés áttekintése lap, és minden, várhatóan beérkező cikk áttekintését nyújtja.

A **Beérkezés áttekintése** lap az összes várhatóan bejövő cikkek áttekintését nyújtja. Megjeleníti az áttekintés alapján inicializálható érkezéseket is. Ez a témakör a bevételezési folyamatra összpontosít.

## <a name="business-scenario"></a>Üzleti eset
Fontolja meg a következő példát a bevételezési folyamatokban.

[![Üzleti eset](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

Sanyi, a bevételezési adminisztrátor az iránt érdeklődik, hogy milyen beérkező cikkekre számítson az aktuális napon. A **Beérkezés áttekintése** lapon Sanyi áttekintést kaphat az aktuális feladatokról, valamint megtekintheti a mennyiségek, a térfogat, a súly, a különféle típusú rendelések stb. durva becslését is. Később a szállítás megérkezik az egyik érkeztetési területre, és Sanyi kap egy szállítási listát. A **Beérkezés áttekintése** lapon Sanyi a következő feladatokat végezheti el:

-   Azonosítja a megfelelő befizetési utalványt, és a bevételezést **Folyamatban** lévőként regisztrálja. A regisztrációhoz szükséges sorokat a rendszer automatikusan létrehozza, és a bevételezés figyelhető, annak ellenére, hogy a tranzakciókat még nem adták fel **Regisztrálva** állapotúként.
-   Nyissa meg a megfelelő cikkérkezési napló hivatkozását (például a **Cikkérkeztetési** naplót vagy a **Termékek beérkezése** naplót), és azonosítsa azokat a naplókat, amelyek készen állnak a termékbevételezések frissítésére.

## <a name="arrival-overview-page"></a>Beérkezés áttekintése lap
A **Beérkezés áttekintése** lap megnyitásához kattintson a **Készletkezelés** &gt; **Bejövő rendelések** &gt; **Beérkezés áttekintése** lehetőségre. Megtekintheti a várható rendelések listáját. Az Áttekintés egy fejlécre és sorokra van felosztva. A fejléc adatai a rendelés típusa, a várható bevételezési dátum és a szállítási hely szerint vannak csoportosítva. Ha egy fejlécet cikkérkeztetésre választ ki, a rendszer a számlahivatkozáshoz kapcsolódó összes részletsort érkeztetésre jelöli ki a lap soradatok részében. Az összes kapcsolódó naplósorok feladása után ez az információ nem jelenik meg.

### <a name="arrival-overview-profiles"></a>Érkezésáttekintési profilok

A **Beérkezés áttekintése** lap áttekintést nyújt a várhatóan beérkező cikkekről és a várható kézhezvételi dátumukról. Az érkeztetési eljárás részeként több személyes beállítást is használhat. Az egyes felhasználók megadhatják személyes beállításaikat az **Érkeztetési áttekintési profilok** lapon.

### <a name="set-up-item-arrival"></a>Cikkérkeztetés beállítása

Ebben a példában Sanyi új számítógépet szeretne felállítani egy olyan helyen, amely az 1. telephelyről érkező késztermékeket fogadja. Az **Érkeztetési áttekintési profilok** lapon Sanyi létrehoz egy új, **1. termelési telephely** elnevezésű beállítást, és megadja a következő beállításokat.

1.  Az **Érkezési beállítások** gyorslapon a **Tartomány** mezőcsoportban adja meg az áttekintésben szerepeltetni kívánt napok időközét és a raktárakat.
2.  Az **Érkezési beállítások** Gyorslapon a **Napló** mezőcsoportban adja meg a fogadó raktárat, a helyet és egy naplónevet (cikkérkeztetés/termelési bemenet).
3.  Az **Érkezéslekérdezés részletei** gyorslapon a **Telephely** mezőcsoportban a **Korlátozás a helyre** mezőbe írja be azt a helyet, amelyre az áttekintés megjelenítését korlátozza.
4.  Az **Érkezéslekérdezés részletei** gyorslapon a **Megjelenített tranzakciótípusok** mezőcsoportban állítsa be a **Termelési rendelések** lehetőséget **Igen** állapotúra.
5.  Az **Érkezéslekérdezés részletei** gyorslapon a **Vegyes** csoportban állítsa be a **Frissítés indításkor** lehetőséget **Igen** állapotúra, ha a nézetet indításkor automatikusan frissíteni szeretné. Állítsa a **Frissítés tartományváltozáskor** lehetőséget **Igen** állapotúra, ha a nézetet automatikusan frissíteni szeretné a tartományértékek módosulásakor.

Ennél a példánál a **Beérkezés áttekintése** lap **Érkezési beállítások** gyorslapján az **Érkeztetési áttekintés profil** mező beállítása **1. termelési telephely**.

### <a name="prerequisites-for-arrival-journals"></a>Érkeztetési naplók előfeltételei

Az érkeztetési naplók automatikus létrehozásához a **Beérkezés áttekintése** lapon meg kell adnia a megfelelő adatokat az **Érkezési beállítások** gyorslap **Napló** mezőcsoportjában.

-   Új napló létrehozásakor meg kell adnia egy naplónevet.

[![A napló nevének megadása](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   Ha értékeket ad meg a **Raktár** és a **Hely** mezőkben, ezeket az értékeket a rendszer alkalmazza a naplósorokban. Ha nem ad meg értéket, a rendszer a készlettranzakciókban megadott dimenzióértékeket használja.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>Várt befizetési utalvány cikkei

A **Nyugták** gyorslapon Sanyi kiválaszt egy sort, majd kattint az **Érkeztetés indítása** lehetőségre. Az összes kapcsolódó sor, amelyik a megadott tartományba esik, és regisztrálni mennyiséggel rendelkezik, a rendszer automatikusan kijelöli. Cikkérkeztetési napló jön létre, amely egyezést tartalmaz a várt befizetési utalvány és a napló között. A mennyiséget a program automatikusan inicializálja minden létrehozott sorban.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>Egynél több várt befizetési utalványból érkező cikkek

A **Nyugták** gyorslapon Sanyi több sort választ ki, majd kattint az **Érkeztetés indítása** lehetőségre. Cikkérkeztetési napló jön létre, amely egyezést tartalmaz az összes várt befizetési utalvány és a napló között. Az összes sor egy cikk cikkérkezési napló fejlécében jön létre, és a mennyiséget a program automatikusan inicializálja.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>Cikkek fogadása egy vagy több várt befizetési utalványból

#### <a name="view-information"></a>Információk megtekintése

Ha áttekintést szeretne kapni a várt bevételezésekről egy adott időszakban, Sanyi a következő adatokat írja be az **Beérkezés áttekintése** lap **Érkezési beállítások** gyorslapjának mezőibe, majd a **Frissítés** lehetőségre kattint a nézet frissítése érdekében:

-   Érkeztetésáttekintési profilnév: **Lekérdezés**
-   Sorok megjelenítése: **Mind**
-   Napra visszamenőleg: (Üres)
-   Napra előre: **0**
-   Raktárak: **GW, MW**

Sanyi az alábbi adatokat is megjelenítheti:

-   A rendszerdátumhoz kapcsolódó összes befizetési utalvány és a dátumtól számított korlátlan számú napra visszamenőleg (a **InventTrans.StatusDate** intervallum), és a GW és MW raktárak nyugtái, állapottól függetlenül.
-   Egynél több rendelés részletes soradatai. Sanyi több fejlécsort választhat ki az áttekintésben, majd kattinthat a **Minden kijelölt megjelenítése** lehetőségre az összes kiválasztott rendelés minden megfelelő sora részletes adatainak megtekintéséhez.
-   Adott beszerzési rendelés adatai. Ha Sanyi az áttekintésben csak egy bizonyos hivatkozási számhoz kapcsolódó adatokat szeretne megjeleníteni, megadhat egy számlaszámot a **Számlaszám** mezőben és a rendelés számát a **Hivatkozási szám** mezőben.
-   Az összes olyan esedékes rendelési sorra vonatkozó regisztrációs feladatok áttekintése, amelyekhez a cikkérkezési napló létrehozása már megtörtént, de még nincs feladva. Az információ megtekintéséhez Sanyi kiválaszthatja a **Folyamatban** lehetőséget a **Sorok megjelenítése** mezőben.

### <a name="update-journals"></a>Naplók frissítése

Egy vagy több feldolgozandó esedékes rendelési sor regisztrálásához Sanyi kijelölheti az áttekintő rácsban vagy a sorrácsba levő sorokat, majd kattinthat a **Naplók** &gt; **Érkezések megjelenítése a bevételekből** lehetőségre. Megjelenik a soroknak megfelelő cikkérkeztetési fejléc. A beszerzési rendelés termékbevételezésének regisztrált cikkekkel történő frissítése érdekében Sanyi elérhető a cikkérkeztetési napló frissíthető fejléceit. A cikkérkeztetési napló fejléceinek eléréséhez a **Naplók** &gt; **Termékbevételezésre kész naplók** lehetőségre kattint. Megjelenik minden olyan fejlécsor, amely készen áll termékbevételezés frissítésére a megadott raktártartományban. (A megjelenített fejlécsorok nem kapcsolódnak a napok időközéhez).

### <a name="start-an-arrival-registration"></a>Érkezési regisztráció indítása

A **Beérkezés áttekintése** lapon több sor kiválasztásával Sanyi egynél több számlahivatkozás beérkezését indíthatja el. Amikor a bevételezések áttekintéséből egy sort jelöl ki, a rendszer kijelöli a kapcsolódó soradatokat. Ha létezik regisztrációs mennyiség, az **Érkeztetés indítása** gomb elérhető. Sanyi két módszert használhat a beérkezésregisztráció elindításához:

-   A lap olyan módon történő szűréséhez, hogy csak a megadott feltételeknek megfelelő rekordok jelenjenek meg, a **Szállítói hivatkozás** mezőben beolvassa egy szállító hivatkozási számát, például a szállítólevél vonalkódját.
-   Az áttekintési részen vagy az **Érkeztetés áttekintése** lap részletes megjelenítésénél, manuálisan kiválasztja vagy elveti a beérkezésregisztrációs rekordok kijelölését. Ezután ha Sammy az **Érkeztetés indítása** lehetőségre kattint, a kijelölt rekordok automatikusan létrejönnek a cikkérkeztetési napló segítségével. A rekordok tartalmazzák a soradatokat, és minden egyedi mezőadat hozzá van rendelve.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>Érkezési adatok frissítése és a termékbevételezés feldolgozása
Ha minden áru regisztrálása megtörtént, a raktárvezető vagy a beszerzési igazgató egy termékbejegyzéssel frissítheti a fogadott cikkek adatait, amivel megadja a tényleges költségeket. Az érkezési adatok frissítése és a termékbevételezés feladása érdekében kövesse az alábbi lépéseket.

1.  Kattintson a **Készletkezelés** &gt; **Bejövő rendelések** &gt; **Beérkezés áttekintése** lehetőségre.
2.  A **Beérkezés áttekintése** lapon kattintson a **Naplók** &gt; **Szállítólevélre kész naplók** lehetőségre a szállítólevél-frissítésre kész naplók listájának megjelenítéséhez.
3.  Válassza ki a frissítendő naplókat, majd kattintson a **Funkciók** &gt; **Termékbevételezés** lehetőségre.
4.  A **Feladás** lapon adja meg a termékbevételezés számát, ha még nem érhető el a naplóban, majd kattintson az **OK** gombra a termékbevételezés feldolgozásához.

## <a name="summary"></a>Összegzés
A **Beérkezés áttekintése** lap áttekintést ad a raktárvezetőnek és a raktári dolgozóknak a bejövő feldolgozás részeként elvárt munkáról. A lapot a cikk érkeztetési folyamatának elindítására is használhatja, ezzel biztosítva a cikkek raktárba érkezésük első bejegyzésétől számított nyomon követését.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]