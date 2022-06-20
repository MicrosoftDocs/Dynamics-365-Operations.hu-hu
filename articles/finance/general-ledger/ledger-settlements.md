---
title: Főkönyvi kiegyenlítések
description: Ez a cikk bemutatja, hogy hogyan lehet a Főkönyvi kiegyenlítések lapon a főkönyvi tranzakciók kiegyenlítését és a kiegyenlítések sztornírozátni.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 39fd6c6677565a4b1e9a9bf6f43a4c630cb5e07b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902487"
---
# <a name="ledger-settlements"></a>Főkönyvi kiegyenlítések

[!include [banner](../includes/banner.md)]

A főkönyvi kiegyenlítés a tartozik és követel tranzakciók egyeztetésének folyamata a főkönyvben. A tartozik és követel összegek kiegyenlítésével lehet egyeztetni a főkönyvi számla egyenlegét az egyenleget fel adó részletes tranzakciókkal.

A kiegyenlített tranzakciókat ki lehet zárni a lekérdezések és jelentésekből. Ily módon egyszerűbb a főkönyvi számla egyenlegét fel adó nyitott főkönyvi tranzakciók elemzése.

> [!IMPORTANT] 
> A Kötelezettségek (AP) és a Kinnlevőségek (AR) modulban a számlák és kifizetések kiegyenlítése is található. Amikor kiegyenlítés történik a vevői és a szállítói részalapnál, a megfelelő főkönyvi bejegyzések kiegyenlítése nem történik meg automatikusan.

## <a name="ledger-settlement-features"></a>Főkönyvi kiegyenlítési funkciók
A Microsoft Dynamics 365 Pénzügyi modul 10.0.21-es **·** **verziójában a speciális főkönyvi kiegyenlítés engedélyezése beállítás el lett távolítva a Főkönyvi paraméterek lapról.** A főkönyvi kiegyenlítés mostantól mindig engedélyezett.
A Pénzügy modul 10.0.25-ös **verziójában** a főkönyvi kiegyenlítés és az év végi lezárás közötti tájékoztatás funkció került bevezetésre. Ez a funkció a főkönyvi kiegyenlítés és a főkönyv év végi zárás alapvető funkcióit is megváltoztatja. Mielőtt engedélyezi ezt a funkciót a **Funkciókezelés** munkaterületen, tekintse meg a [Főkönyvi kiegyenlítés és az év végi lezárás közötti tudatosságot](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Főkönyvi kiegyenlítés beállítása
Ki kell választania azokat a fő számlákat, amelyekre a főkönyvi kiegyenlítést el szeretné könyvelni. Ezeket a fő számlákat kétféleképpen lehet kiválasztani.

1. Ugrás a Főkönyv **beállítása** > **főkönyvi** > **paraméterekhez**.
2. A Főkönyvi **kiegyenlítések** lapon válassza ki azokat a számladiagramokat, amelyekről ki szeretné választani a fő számlákat.
3. Válassza ki azokat a fő számlákat, amelyekre a főkönyvi kiegyenlítést el kell könyvelni. Mivel a számladiagramok globálisak, minden vállalat, amelyekhez a kiválasztott számladiagramok hozzá vannak rendelve, ugyanazt a főkönyvi kiegyenlítésre kijelölt fő számlát fogja látni.

  – vagy –

1. Ugrás a Főkönyv **–** > **Időszakos feladatok főkönyvi** > **kiegyenlítések modulhoz**.
2. Válassza ki a **főkönyvi kiegyenlítési számlákat**.
3. A párbeszédpanelen válassza ki azokat a számladiagramokat és fő számlákat, amelyekre a főkönyvi kiegyenlítést el kellkönyvelni. Ez a párbeszédpanel egy parancsikon. Az itt megadott fő számlák a **Főkönyvi paraméterek lapon is megjelennek**.

Ugyanezeket az alapvető eljárásokat használhatja a fő számlák bármikori eltávolítására a főkönyvi kiegyenlítésből. A fő számla eltávolítása nincs hatással a korábbi főkönyvi kiegyenlítésre. A fő számla és a tranzakciók azonban már nem jelennek meg a Főkönyvi **kiegyenlítés oldalon**.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Tranzakciók kiegyenlítése
Főkönyvi tranzakciók kiegyenlítéséhez kövesse az alábbi lépéseket.

1. Ugrás a Főkönyv **–** > **Időszakos feladatok főkönyvi** > **kiegyenlítések modulhoz**.
2. Az oldal tetején állítsa be a szűrőket:

    - Válasszon ki egy dátumtartományt. Másik lehetőségként válasszon egy dátumtartománykódot, amely automatikusan kitölti a dátumtartományt. Nem ajánlott a főkönyvi kiegyenlítést a pénzügyi éven átívelő tranzakciók esetében.
    - Szükség szerint módosítsa a feladási réteget. Nem egyenlíthet ki különböző feladási rétegekben tranzakciókat.
    - A fő számla és a dimenziók külön-külön való kiválasztásához válasszon ki egy pénzügyi dimenziókészletet.

3. Válassza a **Tranzakciók megjelenítése** beállítást minden olyan tranzakció megjelenítéséhez, amely megfelel a beállított szűrőknek és a számlák listájának, amelyet a számlatükör lista beállításakor meghatározott az előző részben.

    - Ha módosítja a szűrők vagy a dimenziókészletek bármelyikét, ki kell választania a **Tranzakciók megjelenítése** lehetőséget újra.
    - Ha a tranzakciókat egy fő számlára is szűrni kell, használja a **Főkönyvi számla mező szűrőját**. Nem ajánljuk a főkönyvi kiegyenlítést a különböző fő számlákra feladott tranzakciók esetében.

4. Válassza ki a kiegyenlítés sorait. A lap tetején **található** Kiválasztott összeg mező értéke a kijelölt sorok végösszegének megfelelően nő vagy csökken.
5. Ha befejezte a tranzakciók kijelölését, válassza a Megjelölés **lehetőséget**. Minden kijelölt tranzakciónál megjelenik egy pipa a Megjelölt **oszlopban**. Ezenkívül a rács **fölötti Megjelölt** összeg mező értéke a megjelölt sorok teljes összegének megfelelően nő vagy csökken.
6. Ha a Megjelölt **összeg** **mezőben 0** (nulla) érték van megjelölve, **válassza a Megjelölt tranzakciók egyenlítő értékét.** A megjelölt tranzakciók állapota **Kiegyenlített** értékre frissül.

    > [!IMPORTANT]
    > Az aktív jogi személy kiegyenlítésére megjelölt összes tranzakció ki lesz egyenlítve, még akkor is, ha a szűrő alkalmazása miatt jelenleg nem jelennek meg a főkönyvi kiegyenlítési lapon.

## <a name="make-transactions-easier-to-find"></a>Tranzakciók megkeresésének egyszerűbbé tétele
A **Főkönyvi kiegyenlítések** lap olyan funkciókat tartalmaz, amelyek segítségével egyszerűbben megtekinthetők a kiegyenlítéshez szükséges tranzakciók.

- A Megjelölt **szűrő** használatával annak alapján szűrheti a tranzakciókat, hogy be **van**-e jelölve a Megjelölt jelölőnégyzet.
- Az Állapot szűrő **használatával** állapotuk alapján szűrheti a tranzakciókat.
- Válassza az **abszolút összeg alapján való rendezést** az összegek abszolút érték alapján való rendezéshez. Ily módon csoportosíthatja az azonos összegű tartozik és követel tételeket.

## <a name="reverse-a-settlement"></a>Kiegyenlítés sztornírozása
A tévedésből létrehozott kiegyenlítések sztornírozhatók.

1. Hajtsa végre a Tranzakciók rendezésének szakasz 1–3 [...](#settle-transactions). lépését, hogy a tranzakciót érdeklődésére mutassa.
2. Az **Állapot** szűrőben válassza ki a **Kiegyenlített** lehetőséget.
3. Válassza ki a sorokat a megfordításhoz.
4. Jelölje ki a **Megjelölt tranzakciók sztornírozása lehetőséget**. Az azonos kiegyenlítési azonosítójú tranzakciók állapota Nincs kiegyenlítve **állapotúra módosul**.

    > [!IMPORTANT]
    > Minden olyan tranzakció sztornírozva lesz, amelyek kiegyenlítési azonosítója megegyezik, még akkor is, ha nincsenek megjelölve. Például négy sort jelöltek meg és egyenlíttek ki. Mind a négy sor kiegyenlítési azonosítója megegyezik. Ha kijelöli a négy sor valamelyikét, és a **Megjelölt** tranzakciók sztornírozása lehetőséget választja, mind a négy sort sztornírozni fogja a tranzakció.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
