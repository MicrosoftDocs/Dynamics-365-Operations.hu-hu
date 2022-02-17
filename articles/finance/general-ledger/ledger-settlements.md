---
title: Főkönyvi kiegyenlítések
description: Ez a témakör ismerteti a Főkönyvi kiegyenlítések lap használatát a főkönyvi tranzakciók kiegyenlítéséhez és a kiegyenlítések sztornírozásához.
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
ms.openlocfilehash: e98b012210338e7f18cb874eefbc8a023aa4428b
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075324"
---
# <a name="ledger-settlements"></a>Főkönyvi kiegyenlítések

[!include [banner](../includes/banner.md)]

A főkönyvi kiegyenlítés a terhelési és jóváírási tranzakciók egyeztetésének folyamata a főkönyvben. A terhelési és jóváírási összegek elszámolása a főkönyvi számla egyenlegének egyeztetésére szolgál az egyenleget alkotó részletes tranzakciókkal.

Az elszámolt tranzakciók kizárhatók a lekérdezésekből és a jelentésekből. Ily módon könnyebb a főkönyvi számla egyenlegét alkotó nyitott főkönyvi tranzakciók elemzése.

> [!IMPORTANT] 
> A számlák (AP) és a vevők (AR) modulok számlák és fizetések kiegyenlítésével is rendelkeznek. Amikor a kiegyenlítés az AR és AP alkönyvekben történik, a megfelelő főkönyvi bejegyzések nem kerülnek kiegyenlítésre automatikusan.

## <a name="ledger-settlement-features"></a>Főkönyvi elszámolás jellemzői
A Microsoftban Dynamics 365 Finance 10.0.21 verzió, a **Speciális főkönyvi kiegyenlítés engedélyezése** opciót eltávolították a **Főkönyvi paraméterek** oldalon. A speciális főkönyvi kiegyenlítés mostantól mindig engedélyezve van.
A Finance 10.0.25-ös verziójában a **Tudatosság a főkönyvi elszámolás és az év végi zárás között** funkciót vezették be. Ez a szolgáltatás megváltoztatja az alapvető funkciókat mind a főkönyvi elszámolásban, mind a főkönyvi év végi zárásban. Mielőtt engedélyezi ezt a funkciót a **Funkciókezelés** munkaterület, lásd [Tudatosság a főkönyvi elszámolás és az év végi zárás között](awareness-between-ledger-settlement-year-end-close.md).

## <a name="set-up-ledger-settlement"></a>Főkönyvi elszámolás beállítása
Ki kell választania azokat a fő számlákat, amelyekhez főkönyvi elszámolást szeretne végezni. Kétféleképpen lehet kiválasztani ezeket a fő fiókokat.

1. Menj **Főkönyvi** > **Főkönyvi beállítás** > **Főkönyvi paraméterek**.
2. A **Főkönyvi elszámolások** lapon válassza ki azokat a számlatáblázatokat, amelyekről ki szeretné választani a fő számlákat.
3. Válassza ki a fő számlákat a főkönyvi kiegyenlítéshez. Mivel a számlatükör globálisak, minden olyan vállalatnak, amelyhez a kiválasztott számlatükör hozzá van rendelve, ugyanazok a főszámlák lesznek kiválasztva a főkönyvi kiegyenlítéshez.

  – vagy –

1. Menj **Főkönyvi** > **Időszakos feladatok** > **Főkönyvi elszámolások**.
2. Válassza ki **Főkönyvi elszámolási számlák**.
3. A párbeszédpanelen válassza ki azokat a számlatáblázatokat és főszámlákat, amelyekre a főkönyvi elszámolást szeretné elvégezni. Ez a párbeszédpanel egy parancsikon. Az itt hozzáadott fő fiókok szintén megjelennek a **Főkönyvi paraméterek** oldalon.

Ugyanezekkel az alapvető eljárásokkal bármikor eltávolíthatja a főszámlákat a főkönyvi elszámolásból. A főszámla eltávolítása nincs hatással a korábbi főkönyvi elszámolásokra. A főszámla és a tranzakciók azonban már nem jelennek meg a **Főkönyvi elszámolás** oldalon.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Tranzakciók kiegyenlítése
Főkönyvi tranzakciók kiegyenlítéséhez kövesse az alábbi lépéseket.

1. Menj **Főkönyvi** > **Időszakos feladatok** > **Főkönyvi elszámolások**.
2. Az oldal tetején állítsa be a szűrőket:

    - Válasszon ki egy dátumtartományt. Alternatív megoldásként válasszon egy dátumintervallum kódot a dátumtartomány automatikus kitöltéséhez. Nem javasoljuk, hogy főkönyvi kiegyenlítést végezzen a pénzügyi éveket átívelő tranzakcióknál.
    - Szükség szerint módosítsa a feladási réteget. A különböző feladási rétegekben lévő tranzakciók nem rendezhetők.
    - A fő számla és a dimenziók külön-külön történő megjelenítéséhez válasszon egy pénzügyi dimenziókészletet.

3. Válassza a **Tranzakciók megjelenítése** beállítást minden olyan tranzakció megjelenítéséhez, amely megfelel a beállított szűrőknek és a számlák listájának, amelyet a számlatükör lista beállításakor meghatározott az előző részben.

    - Ha módosítja a szűrők vagy a dimenziókészletek bármelyikét, ki kell választania a **Tranzakciók megjelenítése** lehetőséget újra.
    - A tranzakciók egyéni főszámlára történő szűréséhez használja a szűrőt a **Főkönyvi számla** terület. Nem javasoljuk, hogy főkönyvi kiegyenlítést végezzen a különböző főszámlákra könyvelt tranzakciók esetében.

4. Válasszon vonalakat az elszámoláshoz. Az érték a **Kiválasztott mennyiség** Az oldal tetején lévő mező növekszik vagy csökken, hogy tükrözze a kiválasztott sorok teljes összegét.
5. Ha végzett a tranzakciók kiválasztásával, válassza a lehetőséget **Jelölje meg kiválasztottként**. Minden kiválasztott tranzakciónál egy pipa jelenik meg a **Megjelölt** oszlop. Ezenkívül az érték a **Megjelölt összeg** A rács feletti mező növekszik vagy csökken, hogy tükrözze a megjelölt vonalakon lévő teljes összeget.
6. Amikor az érték a **Megjelölt összeg** mező az **0** (nulla), válassza ki **A megjelölt tranzakciók rendezése**. A megjelölt tranzakciók állapota **Kiegyenlített** értékre frissül.

    > [!IMPORTANT]
    > Minden olyan tranzakció, amelyet az aktív jogi személy számára kiegyenlítésre jelölt meg, akkor is kiegyenlítésre kerül, ha jelenleg nem jelennek meg a Főkönyvi kiegyenlítés oldalon, mert szűrőt alkalmazott.

## <a name="make-transactions-easier-to-find"></a>Tranzakciók megkeresésének egyszerűbbé tétele
A **Főkönyvi elszámolások** oldal olyan lehetőségeket tartalmaz, amelyek megkönnyítik az elszámoláshoz szükséges tranzakciók megtekintését.

- Használja a **Megjelölt** szűrő a tranzakciók szűréséhez az alapján, hogy a **Megjelölt** jelölőnégyzet be van jelölve számukra.
- Használja a **Állapot** szűrő a tranzakciók állapotuk alapján történő szűréséhez.
- Válassza ki **Rendezés abszolút összeg szerint** az összegek abszolút érték szerinti rendezéséhez. Ily módon csoportosíthatja az azonos összegű terheléseket és jóváírásokat.

## <a name="reverse-a-settlement"></a>Kiegyenlítés sztornírozása
A tévedésből létrehozott kiegyenlítések sztornírozhatók.

1. Kövesse az 1–3. lépéseket a [A tranzakciók rendezése](#settle-transactions) szakaszban megtekintheti az Önt érdeklő tranzakciókat.
2. Az **Állapot** szűrőben válassza ki a **Kiegyenlített** lehetőséget.
3. Válassza ki a sorokat a visszafordításhoz.
4. Válassza ki **Fordított megjelölt tranzakciók**. Az azonos elszámolási azonosítóval rendelkező összes tranzakció állapota a következőre frissül **Nem rendezett**.

    > [!IMPORTANT]
    > Minden olyan tranzakció, amelynek elszámolási azonosítója megegyezik, visszavonásra kerül, még akkor is, ha nincsenek megjelölve. Például négy sort jelöltek ki és rendeztek el. Mind a négy sornak ugyanaz a településazonosítója. Ha kijelöli a négy sor egyikét, majd kiválasztja **Fordított megjelölt tranzakciók**, mind a négy sor megfordul.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
