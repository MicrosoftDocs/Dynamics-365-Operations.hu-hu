---
title: Termékkészenlét
description: Ez a cikk bemutatja, hogy hogyan használhatók a készenlét-ellenőrzések annak biztosítására, hogy a termékekhez a tranzakciókban történő felhasználás előtt meg kell adni a szükséges alapadatokat.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a8e76d5fc786b6f4cac7cd0430399ca3ad13a7bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856222"
---
# <a name="product-readiness"></a>Termékkészenlét

[!include [banner](../includes/banner.md)]

A készenléti ellenőrzéseket annak biztosítására használhatja, hogy a szükséges alapadatok mindegyike meg legyen adva egy termékhez a tranzakciókban való használat előtt. Amikor készenléti ellenőrzést alkalmaznak, a felhasználó vagy a csoport felelős a megadott előre meghatározott termékkel kapcsolatos adatok ellenőrzéséért.

A mérnöki termékhez, változathoz vagy verzióhoz tartozó **Aktív** jelölőnégyzet bejelölheti, ha az összes szükséges adatot bevitték és ellenőrizték, és miután minden készenléti ellenőrzést feldolgoztak. Ha egy vagy több ellenőrzés nem lett feldolgozva a termékhez, verzióhoz vagy változathoz, majd amikor megpróbálja bejelölni az **Aktív** jelölőnégyzetet, rendszer figyelmezteti, hogy nem minden ellenőrzés lett befejezve.

A készenléti ellenőrzéseket új tervezési termékekhez, új változatokhoz és verziókhoz lehet létrehozni. A szokásos (nem tervezési) termékekre készenlét-ellenőrzést is alkalmazhat (lásd még [Normál termékek készenléti ellenőrzése](#standard-products)). 

A tranzakciókban használhatja az általános termékeket annak ellenére, hogy nem minden készenlét-ellenőrzés lett befejezve. Ha le kell tiltani egy termék tranzakciókban való használatát, használja annak életciklus-állapotát. Hozzárendelhet egy életciklus-állapotot, amely megakadályozza a termék tranzakciókban történő használatát, majd miután minden készenlét-ellenőrzés befejeződött, új életciklus-állapotot rendelhet hozzá, amely engedélyezi a szükséges tranzakciókat.

## <a name="types-of-readiness-checks"></a>Készenléti ellenőrzések típusai

Háromféle készenléti ellenőrzés van:

- **Rendszerellenőrzés** – A rendszer ellenőrzi, hogy létezik-e érvényes rekord. Előfordulhat például, hogy a rekord egy aktív anyagjegyzék (AJ).
- **Manuális ellenőrzés** – A felhasználó ellenőrzi, hogy a rekord érvényes-e. Például a készenléti ellenőrzéshez szükség lehet az alapértelmezett rendelési beállítások érvényesítésére. Bizonyos esetekben, például ha a termék még nincs megtervezve, és így nem kerül készletre, akkor nem szükségesek alapértelmezett rendelési beállítások. Előfordulhat azonban, hogy az alapértelmezett rendelési beállításokat egy másik, azonos típusú termék esetében kötelező megadni, mert a termék tárolható készleten. A felhasználó felelős azért, hogy tudja, hogyan kell helyesen eldönteni, hogy szükséges-e a készenléti ellenőrzés.
- **Ellenőrzőlista** – A felhasználó egy ellenőrzőlista egyik kérdését válaszolja meg, és a rendszer meghatározza, hogy a válaszok megfelelnek-e a várakozásoknak. A ellenőrzőlista rendelkezhet bármilyen tárggyal. Felhasználható például annak meghatározására, hogy a marketinganyagok vagy a termékdokumentáció készen áll-e.

<a name="checks-engineering"></a>

## <a name="how-readiness-checks-are-created-for-a-new-engineering-product-variant-or-version"></a>Új tervezési termékhez, változathoz vagy verzióhoz létrehozott készenléti ellenőrzések

A készenléti ellenőrzés irányelvei a kiadott termék szintjén, a kiadott változat szintjén és a mérnöki verzió szintjén is alkalmazhatók.

Új *tervezési termék* létrehozásakor a rendszer meghatározza, hogy vonatkozik-e rá [valamelyik készenléti ellenőrzési irányelv](#assign-policy). Ha vonatkozik rá készenléti ellenőrzési irányelv, akkor a következő események történnek:

- A termékre vonatkozó készenléti ellenőrzések a vonatkozó irányelv alapján jönnek létre.
- A mérnöki verzió inaktív értékre van állítva a termék használatának blokkolásához. A termék összes tervezési verziója inaktívra van állítva.

Ha új *változatot* hoznak létre egy termékhez, a rendszer ellenőrzi, hogy vonatkozik-e rá készenléti ellenőrzési irányelv. (A készenléti ellenőrzések a kiadott változat szintjén és a tervezési verzió szintjén is alkalmazhatók.) Ha vonatkozik rá irányelv, akkor a következő események történnek:

- A termékre vonatkozó készenléti ellenőrzések a vonatkozó irányelv alapján jönnek létre.
- A tervezési verzió és a változat inaktívra van állítva a termék használatának blokkolásához.

Ha új tervezési *verziót* hoznak létre egy termékhez, a rendszer ellenőrzi, hogy vonatkozik-e rá készenléti ellenőrzési irányelv. (A készenléti ellenőrzések a tervezési verzió szintjén alkalmazhatók.) Ha vonatkozik rá irányelv, akkor a következő események történnek:

- A termékre vonatkozó készenléti ellenőrzések a vonatkozó irányelv alapján jönnek létre.
- A mérnöki verzió inaktív értékre van állítva a termék használatának blokkolásához.

> [!NOTE]
> A normál (nem tervezési) termékekhez készenléti ellenőrzési irányelveket is beállíthat. A további tudnivalókat [lásd](#standard-products) a cikk szokásos termékekkel kapcsolatos készenlét-ellenőrzése című részében.

## <a name="view-readiness-checks"></a>Készenléti ellenőrzések megtekintése

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Termék vagy termék verziójához tartozó nyitott készenléti ellenőrzések megtekintése

A termék nyitott készenléti ellenőrzésének megkereséséhez nyissa meg a **Kiadott termékek részletei** oldalt. Ezután a műveleti ablaktáblán a **Termék** lapon a **Készenléti ellenőrzések** csoportban válassza a **Készenléti ellenőrzések** lehetőséget.

A termék verziójához tartozó nyitott készenléti ellenőrzések megkereséséhez nyissa meg a kiadott termék **Mérnöki verziók** oldalát, és válasszon egy verziót. Ezután a műveleti ablaktáblán a **Termék** lapon az **Ellenőrzőlista** csoportban válassza a **Készenléti ellenőrzések** lehetőséget.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>A Önhöz rendelt nyitott készenléti ellenőrzések megtekintése

Ha meg szeretné tekinteni az Önhöz rendelt nyitott készenléti ellenőrzéseket, hajtsa végre a következő lépések egyikét.

- Lépjen a **Mérnöki módosítások kezelése \> Általános \> Termékkészenlét \> Saját nyitott készenléti ellenőrzések** részre.
- Lépjen a **Termékinformáció-kezelés \> Munkaterületek \> Termék készenléti állapota elkülönített gyártáshoz** részre.

Ez a beállítás határozza meg, hogy hozzá van-e rendelve készenléti ellenőrzés a készenléti irányelvhez. A készenléti ellenőrzések hozzárendelhetők egy személyhez vagy egy csoporthoz. Ha egy csapathoz egy készenléti ellenőrzést rendel, akkor a csapatban egy személynek fel kell dolgoznia a készenléti ellenőrzést.

## <a name="process-open-readiness-checks"></a>Nyitott készenléti ellenőrzések feldolgozása

### <a name="process-system-and-manual-readiness-checks"></a>A rendszer és a kézi készenléti ellenőrzések feldolgozása

Miután megnyitotta a **Készenléti ellenőrzések** oldalt, megtekintheti a rendszer és a manuális készenléti ellenőrzések tárgyát a műveleti ablak **Kapcsolódó információk megtekintése** lehetőségének kiválasztásával. Ezután kitöltheti és/vagy érvényesítheti az adatokat a készenléti ellenőrzéshez. A nyitott készenléti ellenőrzések **Állapot** értéke *Függőben van*. Ez az állapot azt jelzi, hogy a készenléti ellenőrzést még fel kell dolgozni. Készenléti ellenőrzés feldolgozásához hajtsa végre az alábbi lépések valamelyikét.

- A művelet ablaktáblán jelölje be a **Ellenőrzés/befejezés** lehetőséget készenléti ellenőrzés áttekintéséhez és befejezéséhez. Ha befejezte a munkát, az **Állapot** mező értéke *Megfelelt* értékre módosul.
- A művelet ablaktáblán válassza a **Kihagyás** lehetőséget, ha ki szeretné hagyni a készenléti ellenőrzést, amely nem kötelező. Beállíthat például egy készenléti ellenőrzést az árak számításához. Azonban úgy dönt, hogy kihagyja ezt az ellenőrzést, amíg a termék még a tervezési fázisban van. Ebben az esetben az **Állapot** mező *Kihagyva* értékre módosul.

A készenléti irányelv konfigurációjától függően, ha a készenléti ellenőrzés **Állapot** mezője *Megfelelt* értékre van frissítve, a készenléti ellenőrzés jóváhagyásához további lépésre lehet szükség. Ebben az esetben válassza ki a **Jóváhagyás** lehetőséget a készenléti ellenőrzés befejezéséhez. Ez a jóváhagyási lépés mindig kötelező, ha a készenléti ellenőrzést kihagyja.

Amikor egy új termékhez, változathoz vagy verzióhoz az összes nyitott készenléti ellenőrzést feldolgozták és jóváhagyták, a cikk automatikusan aktívvá válik, és így készen áll a használatra.

### <a name="process-checklist-readiness-checks"></a>Ellenőrzőlista készenléti ellenőrzéseinek feldolgozása

Ellenőrzőlista megnyitásához nyissa meg a **Készenléti ellenőrzések** oldalt, majd a művelet ablaktáblán válassza az **Ellenőrzőlista indítása** lehetőséget. Amikor befejezte az ellenőrzőlistát, a rendszer ellenőrzi, hogy a készenléti ellenőrzés megfelelt-e a kérdőív beállításai alapján. Ha az ellenőrzés megfelelt, az **Állapot** mező értéke *Megfelelt* értékre módosul. Ha a készenléti ellenőrzés nem kötelező, akkor kihagyhatja. Ebben az esetben az **Állapot** mező *Kihagyva* értékre módosul.

A készenléti irányelv konfigurációjától függően, ha a készenléti ellenőrzés **Állapot** mezője *Megfelelt* értékre van frissítve, a készenléti ellenőrzés jóváhagyásához további lépésre lehet szükség. Ebben az esetben válassza ki a **Jóváhagyás** lehetőséget a készenléti ellenőrzés befejezéséhez. Ez a jóváhagyási lépés mindig kötelező, ha a készenléti ellenőrzést kihagyja.

Amikor egy új termékhez, változathoz vagy verzióhoz az összes nyitott készenléti ellenőrzést feldolgozták és jóváhagyták, a cikk automatikusan aktívvá válik, és így készen áll a használatra.

## <a name="create-and-manage-product-readiness-policies"></a>A termék készenléti irányelveinek létrehozása és kezelése

A termékre vonatkozó készenléti ellenőrzések a termékre vonatkozó készenléti irányelvek segítségével kezelhetők. A készenléti szabályok a készenléti ellenőrzések készletét tartalmazzák. Ha egy tervezési termékkategóriához vagy egy megosztott termékhez hozzárendelnek egy készenléti irányelvet, akkor az adott kategórához vagy megosztott termékhez kapcsolódó összes termék rendelkezik a készenléti irányelvben szereplő készenléti ellenőrzéssel.

A termék készenléti irányelveivel való munkavégzéshez menjen a **Mérnöki változtatások kezelése \> Beállítás \> Termék készenléti irányelvei** lehetőségre. Majd tegye a következők egyikét.

- Új irányelv létrehozásához válassza az **Új** lehetőséget a Művelet ablakon, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő irányelv szerkesztéséhez jelölje ki azt a listaablaktáblán, válassza a Művelet ablak **Szerkesztés** parancsát, majd állítsa be a mezőket az alábbi alszakaszokban leírtak szerint.
- Meglévő irányelv törléséhez jelölje ki a listaablaktáblán, válassza a **Szerkesztés** parancsot a Művelet ablaktáblán, majd győződjön meg arról, hogy az **Általános** gyorslapon az **Aktív** beállítás *Nem* értékre van állítva. A Műveletpanelen válassza ezután a **Törlés** elemet.

### <a name="header"></a>Fejléc

Állítsa be a következő mezőket egy termék készenléti irányelv fejlécében.

| Mező | Leírás |
|---|---|
| Név | Adja meg az irányelv nevét. |
| Leírás | Adja meg az irányelv leírását. |

### <a name="general-fasttab"></a>Általános gyorslap

Állítsa be a következő mezőket egy termék készenléti irányelvének **Általános** gyorslapján.

| Mező | Leírás |
|---|---|
| Terméktípus | Válassza ki, hogy az irányelv a *Cikk* vagy a *Szolgáltatás* típusának termékeit érinti-e. A rekord mentése után a beállítás nem módosítható. |
| Aktív | Ezzel a beállítással lehet karbantartani a készenléti irányelveket. Az összes használt készenléti irányelv esetében állítsa *Igen* értékre. *Nem* értékre állításával inaktívként jelölheti meg a készenléti irányelvet, ha nincsen használatban. Ne feledje, hogy a tervezési termékkategóriákhoz vagy a megosztott termékekhez hozzárendelt készenléti irányelvet nem lehet inaktiválni, és csak az inaktív kiadási irányelveket lehet törölni. |

### <a name="readiness-control-fasttab"></a>Készenléti ellenőrzés gyorslap

Az irányelvbe foglalandó minden készenléti ellenőrzéshez vegyen fel egy sort a **Készenléti ellenőrzés** gyorslapon. A gyorslap eszköztár következő gombjaival lehet a szükséges sorokat hozzáadni és eltávolítani:

- **Ellenőrzés hozzáadása** – Normál készenléti ellenőrzés hozzáadása a házirendhez. Ha megnyomja ezt a gombot, megjelenik az **Ellenőrzés hozzáadása** párbeszédpanel. Itt választhat a rendelkezésre álló ellenőrzések listájából.
- **Meglévő kérdőív hozzáadása** – Üres sor hozzáadása a rácshoz. Ezt követően hozzárendelheti a meglévő kérdőíveket a mezők beállításával a következő táblázatban.
- **Másolás** – A kijelölt sor másolatának hozzáadása a rácshoz.
- **Törlés** – A kiválasztott sor törlése a rácsból.

Minden egyes hozzáadott sorhoz állítsa be a következő mezőket.

| Mező | Leírás |
| --- | --- |
| Folyamat területe | Válassza ki, hogy melyik területre vonatkozik az ellenőrzés. |
| Típus | Itt beállíthatja, hogy az ellenőrzés egy rendszerellenőrzés, egy manuális ellenőrzés vagy egy ellenőrzőlista (kérdőív). |
| Név | Ha az ellenőrzés egy ellenőrzőlista, írjon be egy nevet. A rendszer- és a manuális ellenőrzések esetében ez a mező automatikusan be van állítva. |
| Leírás | Ha az ellenőrzés egy ellenőrzőlista, írjon be egy leírást. A rendszer-és a manuális ellenőrzések esetében ez a mező automatikusan be van állítva, és a leírás bemutatja az ellenőrzés fókuszát. |
| Ellenőrzések alkalmazása a következő esetén: | Annak megadása, hogy a sornak készenléti ellenőrzéseket kell-e generálnia egy új kiadott termékre, kiadott változatra vagy kiadott verzióra válaszként. |
| Végrehajtás a következőben: | Itt beállíthatja, hogy a sor által generált készenléti ellenőrzések mindegyik vállalatra vagy egy vállalatra érvényesek-e. |
| Cég | Ha a **Végrehajtás helye** mezőt a *Egyetlen vállalat* értékre állítja be, válassza ki a vállalatot. |
| Tulajdonos típusa | Adja meg, hogy a sor által generált készenléti ellenőrzések egy személyhez vagy egy csoporthoz legyenek-e hozzárendelve. |
| Tulajdonos | Válassza ki a személyt vagy csoportot, amelyhez a készenléti ellenőrzéseket hozzá kívánja rendelni. |
| Kérdőív | Válassza ki azt a kérdőívet, amelyet alkalmazni kell az ellenőrzőlista esetében. Az ellenőrzőlista egy helyi ellenőrzőlista azon a vállalaton belül, ahol a készenléti ellenőrzést végrehajtják. A rendszernek képesnek kell lennie annak értékelésére, hogy helyesen válaszol-e az ellenőrzőlista. Ezért a ellenőrzőlistát úgy kell beállítani, hogy a helyes válaszok alapján végezze el az értékelést. A kérdőívek létrehozásáról a [Kérdőívek](/dynamicsax-2012/appuser-itpro/using-questionnaires) használata és a kapcsolódó cikkek tartalmaznak további tájékoztatást. |
| Automatikus jóváhagyás | A készenléti ellenőrzés rekordjai egy **Jóváhagyott** jelölőnégyzetet tartalmaznak, amely jelzi a jóváhagyási állapotot. Jelölje be az **Automatikus jóváhagyás** jelölőnégyzetet azon ellenőrzések esetén, amelyeket a hozzárendelt felhasználó általi végrehajtás után azonnali jóváhagyásra kell beállítani. Ennek a jelölőnégyzetnek a törlésével további lépésként explicit jóváhagyást követelhet meg. |
| Kötelező | Ezt a jelölőnégyzetet a hozzárendelt felhasználó által végrehajtandó ellenőrzések esetében jelölje be. A kötelező ellenőrzéseket nem lehet kihagyni. |

<a name="assign-policy"></a>

## <a name="assign-readiness-policies-to-standard-and-engineering-products"></a>Készenléti házirendek hozzárendelése a szokásos és a tervezési termékekhez

Ha egy tervezési kategória alapján hoz létre új terméket, akkor egy *kiadott terméket* és egy kapcsolódó *megosztott terméket* is létre kell hoznia. A kiadott termékekre vonatkozó készenlét-szabályok megoldásának módja attól függ, hogy a rendszer be van-e kapcsolva a *Termék* készenlét-ellenőrzése funkció ([a](#standard-products) funkcióról és annak bekapcsolásról a cikk későbbi, a szokásos termékekre való készenlét ellenőrzése című részében olvashat bővebben).

- Ha a *Termék készenléti ellenőrzései* funkció *ki* van kapcsolva, a readiness policy készenléti irányelv csak a [terevzési kategóriájú](engineering-versions-product-category.md) rekordoknál van beállítva, és csak náluk jelenik meg. Annak megállapításához, hogy melyik irányelv vonatkozik egy kiadott termékre, a rendszer ellenőrzi a kapcsolódó tervezési kategória **Termékkészenléti házirend** mezőjét. Egy meglévő termékre vonatkozó készenléti házirend a kapcsolódó tervezési kategória (és nem a megosztott termék) szerkesztésével módosítható.
- Ha a *Termék készenléti ellenőrzései* funkció *be* van kapcsolva, a rendszer hozzáadja a **Termékkészenléti házirend** mezőt a **Termék** oldalhoz (ahol a megosztott termékek beállítása történik) és a **Kiadott termék** oldalhoz (ahol az érték írásvédett és a kapcsolódó megosztott termékből származik). A rendszer a kapcsolódó megosztott termék ellenőrzésével megkeresi a kiadott termékre vonatkozó készenléti házirendet. Ha új tervezési termék létrehozásához tervezési kategóriát használ, a rendszer egy megosztott terméket és egy kiadott terméket is létrehoz, és a tervezési kategóriához tartozó **Termékkészenléti házirend** beállításait átmásolja az új megosztott termékbe. Egy meglévő termékre vonatkozó készenléti házirend a kapcsolódó megosztott termék (és nem a kiadott tervezési kategória) szerkesztésével módosítható.

Készenléti házirend megosztott termékhez való hozzárendeléséhez kövesse az alábbi lépéseket.

1. Ugorjon a **Termékinformációk \> Termékek \> Termékek** részre.
1. Nyissa meg vagy hozza létre azt a terméket, amelyhez készenléti házirendet szeretne hozzárendelni.
1. Az **Általános** gyorslapon állítsa be a **Termékkészenléti házirend** mezőben a termékre alkalmazni kívánt házirend nevét.

Készenléti házirend tervezési kategóriához való hozzárendeléséhez kövesse az alábbi lépéseket.

1. Lépjen a **Tervezési változáskezelés \> Beállítás \> Tervezési termékkategória részletei** részre.
1. Nyissa meg vagy hozza létre azt a tervezési kategóriát, amelyhez készenléti házirendet szeretne hozzárendelni.
1. A **Termékkészenléti házirend** gyorslapon állítsa be a **Termékkészenléti házirend** mezőben a tervezési kategóriára alkalmazni kívánt házirend nevét.

<a name="standard-products"></a>

## <a name="readiness-checks-on-standard-products"></a>Normál termékek készenléti ellenőrzése

A normál (nem tervezési) termékekre vonatkozó termékkészenléti ellenőrzések a Funkciókezelés *Termék készenléti ellenőrzései* funkciójának bekapcsolásával engedélyezhetők. Ez a funkció néhány kis módosítást biztosít a készenlétellenőrzési rendszerben, amely így a normál termékeket is támogatja.

### <a name="enable-or-disable-readiness-checks-on-standard-products"></a>Szokásos termékek készenlét-ellenőrzésének engedélyezése vagy letiltása

Ehhez a funkcióhoz a mérnöki *változáskezelést* *és* a termékre való készenlétet ellenőrző funkciókat is be kell kapcsolva lennie a rendszeren. A funkciók be- és kikapcsolása a [Műszaki változáskezelés témakörében található](product-engineering-overview.md).

### <a name="create-readiness-policies-for-standard-products"></a>Készenléti irányelvek létrehozása normál termékekhez

A normál termékekhez ugyanúgy hozható létre készenléti irányelv, mint a tervezési termékekhez. Lásd a korábbi, ebben a cikkben található információkat.

### <a name="assign-readiness-policies-to-standard-products"></a>Készenléti irányelvek hozzárendelése normál termékekhez

Ha normál termékhez szeretne készenléti házirendet hozzárendelni, nyissa meg a kapcsolódó megosztott terméket, és állítsa be a **Termékkészenléti házirend** mezőben az alkalmazni kívánt házirend nevét. A további tudnivalókat lásd [a](#assign-policy) cikk korábbi, "Készenlét hozzárendelése a szabványos és mérnöki termékekhez" című részében.

### <a name="view-and-process-readiness-checks-on-standard-products"></a>Normál termékek készenléti ellenőrzésének megtekintése és feldolgozása

Ha ez a funkció be van kapcsolva, akkor a normál termékekre vonatkozó készenléti ellenőrzéseket úgy lehet megtekinteni és feldolgozni, mint a tervezési termékekét. Lásd a korábbi, ebben a cikkben található információkat.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
