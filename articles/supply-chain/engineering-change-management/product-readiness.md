---
title: Termékkészenlét
description: Ez a témakör azt mutatja be, hogyan használhatók a készenléti ellenőrzések annak biztosítására, hogy a szükséges alapadatok egy termékhez teljesek a tranzakciókban való használat előtt.
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
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 23ee82922a2103d02a4c1fe0c364fa381c4984c3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842010"
---
# <a name="product-readiness"></a>Termékkészenlét

[!include [banner](../includes/banner.md)]

A készenléti ellenőrzéseket annak biztosítására használhatja, hogy a szükséges alapadatok mindegyike meg legyen adva egy termékhez a tranzakciókban való használat előtt. Amikor készenléti ellenőrzést alkalmaznak, a felhasználó vagy a csoport felelős a megadott előre meghatározott termékkel kapcsolatos adatok ellenőrzéséért. Ha egy termékhez nyitott készenléti ellenőrzés tartozik, akkor a termék nem adható ki, illetve nem használható fel a tranzakciókban.

A mérnöki termékhez, változathoz vagy verzióhoz tartozó **Aktív** jelölőnégyzet csak akkor érhető el, ha az összes szükséges adatot bevitték és ellenőrizték, és miután minden készenléti ellenőrzést feldolgoztak. Ezen a ponton a termék, verzió vagy változat más vállalatoknak is kiadható, és a tranzakciókban használható. A készenléti ellenőrzéseket új termékekhez, új változatokhoz és új mérnöki verziókhoz lehet létrehozni.

## <a name="types-of-readiness-checks"></a>Készenléti ellenőrzések típusai

Háromféle készenléti ellenőrzés van:

- **Rendszerellenőrzés** – A rendszer ellenőrzi, hogy létezik-e érvényes rekord. Előfordulhat például, hogy a rekord egy aktív anyagjegyzék (AJ).
- **Manuális ellenőrzés** – A felhasználó ellenőrzi, hogy a rekord érvényes-e. Például a készenléti ellenőrzéshez szükség lehet az alapértelmezett rendelési beállítások érvényesítésére. Bizonyos esetekben, például ha a termék még nincs megtervezve, és így nem kerül készletre, akkor nem szükségesek alapértelmezett rendelési beállítások. Előfordulhat azonban, hogy az alapértelmezett rendelési beállításokat egy másik, azonos típusú termék esetében kötelező megadni, mert a termék tárolható készleten. A felhasználó felelős azért, hogy tudja, hogyan kell helyesen eldönteni, hogy szükséges-e a készenléti ellenőrzés.
- **Ellenőrzőlista** – A felhasználó egy ellenőrzőlista egyik kérdését válaszolja meg, és a rendszer meghatározza, hogy a válaszok megfelelnek-e a várakozásoknak. A ellenőrzőlista rendelkezhet bármilyen tárggyal. Felhasználható például annak meghatározására, hogy a marketinganyagok vagy a termékdokumentáció készen áll-e.

## <a name="how-readiness-checks-are-created-for-a-new-product-variant-or-version"></a>Új termékhez, változathoz vagy verzióhoz létrehozott készenléti ellenőrzések

Amikor új mérnöki **terméket** hoz létre, a rendszer határozza meg, hogy a mérnöki termékkategória számára be van-e állítva a készenléti ellenőrzési irányelv. (A készenléti ellenőrzési irányelvek a kiadott termék szintjén, a kiadott változat szintjén és a mérnöki verzió szintjén is alkalmazhatók.) Ha egy házirend be van állítva, akkor a következő események történnek:

- A termékre vonatkozó készenléti ellenőrzések a vonatkozó irányelv alapján jönnek létre.
- A mérnöki verzió inaktív értékre van állítva a termék használatának blokkolásához. A szóban forgó termékhez tartozó összes verzió inaktív értékre van állítva.

Ha egy termékhez új **változatot** hoz létre, akkor a rendszer ellenőrzi, hogy be van-e állítva készenléti ellenőrzés a mérnöki termékkategória esetében. (A készenléti ellenőrzések a kiadott változat szintjén és a mérnöki verzió szintjén is alkalmazhatók.) Ha egy készenléti ellenőrzés be van állítva, akkor a következő események történnek:

- A termékhez létrejönnek a készenléti ellenőrzések.
- A mérnöki verzió inaktív értékre van állítva a termék használatának blokkolásához.

Ha egy termékhez új mérnöki **verziót** hoz létre, akkor a rendszer ellenőrzi, hogy be van-e állítva készenléti ellenőrzés a mérnöki termékkategória esetében. (A készenléti ellenőrzések a mérnöki verzió szintjén alkalmazhatók.) Ha egy készenléti ellenőrzés be van állítva, akkor a következő események történnek:

- A termékhez létrejönnek a készenléti ellenőrzések.
- A mérnöki verzió inaktív értékre van állítva a termék használatának blokkolásához.

## <a name="view-readiness-checks"></a>Készenléti ellenőrzések megtekintése

### <a name="view-open-readiness-checks-for-a-product-or-product-version"></a>Termék vagy termék verziójához tartozó nyitott készenléti ellenőrzések megtekintése

A termék nyitott készenléti ellenőrzésének megkereséséhez nyissa meg a **Kiadott termékek részletei** oldalt. Ezután a műveleti ablaktáblán a **Termék** lapon a **Készenléti ellenőrzések** csoportban válassza a **Készenléti ellenőrzések** lehetőséget.

A termék verziójához tartozó nyitott készenléti ellenőrzések megkereséséhez nyissa meg a kiadott termék **Mérnöki verziók** oldalát, és válasszon egy verziót. Ezután a műveleti ablaktáblán a **Termék** lapon az **Ellenőrzőlista** csoportban válassza a **Készenléti ellenőrzések** lehetőséget.

### <a name="view-open-readiness-checks-that-are-assigned-to-you"></a>A Önhöz rendelt nyitott készenléti ellenőrzések megtekintése

Ha meg szeretné tekinteni az Önhöz rendelt nyitott készenléti ellenőrzéseket, hajtsa végre a következő lépések egyikét.

- Lépjen a **Mérnöki módosítások kezelése \> Általános \> Termékkészenlét \> Saját nyitott készenléti ellenőrzések** részre.
- Lépjen a **Termékinformáció-kezelés \> Munkaterületek \> Termék készenléti állapota elkülönített gyártáshoz** részre.

Ez a beállítás határozza meg, hogy hozzá van-e rendelve készenléti ellenőrzés a mérnöki termékkategóriához. A készenléti ellenőrzések hozzárendelhetők egy személyhez vagy egy csoporthoz. Ha egy csapathoz egy készenléti ellenőrzést rendel, akkor a csapatban egy személynek fel kell dolgoznia a készenléti ellenőrzést. A további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).

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

A termékre vonatkozó készenléti ellenőrzések a termékre vonatkozó készenléti irányelvek segítségével kezelhetők. Mivel a mérnöki kategóriához a készenléti irányelv van hozzárendelve, a készenléti irányelvek minden ellenőrzése a mérnöki kategóriákon alapuló összes mérnöki termékre vonatkozik. A további tudnivalókat lásd: [Mérnöki verziók és a mérnöki termékkategóriák](engineering-versions-product-category.md).

A készenléti szabályok a készenléti ellenőrzések készletét tartalmazzák. Ha egy mérnöki termékkategória számára egy készenléti irányelvet rendelnek hozzá, akkor az adott mérnöki termékkategória alapján létrehozott összes termék rendelkezik a készenléti irányelvekben jelzett készenléti ellenőrzéssel.

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
| Aktív | Ezzel a beállítással lehet karbantartani a készenléti irányelveket. Az összes használt készenléti irányelv esetében állítsa *Igen* értékre. *Nem* értékre állításával inaktívként jelölheti meg a készenléti irányelvet, ha nincsen használatban. Ne feledje, hogy nem lehet inaktiválni egy mérnöki termékkategória számára hozzárendelt készenléti irányelvet, és csak az inaktív kiadási irányelveket lehet törölni. |

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
| Kérdőív | Válassza ki azt a kérdőívet, amelyet alkalmazni kell az ellenőrzőlista esetében. Az ellenőrzőlista egy helyi ellenőrzőlista azon a vállalaton belül, ahol a készenléti ellenőrzést végrehajtják. A rendszernek képesnek kell lennie annak értékelésére, hogy helyesen válaszol-e az ellenőrzőlista. Ezért a ellenőrzőlistát úgy kell beállítani, hogy a helyes válaszok alapján végezze el az értékelést. A kérdőívek létrehozásával kapcsolatos további tudnivalókat lásd a [Kérdőívek használata](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/using-questionnaires) és a kapcsolódó témakörök között. |
| Automatikus jóváhagyás | A készenléti ellenőrzés rekordjai egy **Jóváhagyott** jelölőnégyzetet tartalmaznak, amely jelzi a jóváhagyási állapotot. Jelölje be az **Automatikus jóváhagyás** jelölőnégyzetet azon ellenőrzések esetén, amelyeket a hozzárendelt felhasználó általi végrehajtás után azonnali jóváhagyásra kell beállítani. Ennek a jelölőnégyzetnek a törlésével további lépésként explicit jóváhagyást követelhet meg. |
| Kötelező | Ezt a jelölőnégyzetet a hozzárendelt felhasználó által végrehajtandó ellenőrzések esetében jelölje be. A kötelező ellenőrzéseket nem lehet kihagyni. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]