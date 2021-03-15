---
title: Főkönyvi kiegyenlítések
description: Ez a témakör ismerteti a Főkönyvi kiegyenlítések lap használatát a főkönyvi tranzakciók kiegyenlítéséhez és a kiegyenlítések sztornírozásához.
author: mikefalkner
manager: aolson
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 185a95cfebef0e9d6e7914f3102aa5ecb40a877a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988700"
---
# <a name="ledger-settlements"></a>Főkönyvi kiegyenlítések

[!include [banner](../includes/banner.md)]

A főkönyvi kiegyenlítések lehetővé teszik a megfelelő terhelési és jóváírási tranzakciók egyeztetését a főkönyvben, és kiegyenlítettként jelölését. Ezzel a módszerrel biztosíthatja, hogy a kapcsolódó tranzakciók törölve lettek. A kiegyenlítéseket sztornírozni is lehet, ha tévedésből történtek.

## <a name="enable-advanced-ledger-settlements"></a>Speciális főkönyvi kiegyenlítés engedélyezése

A speciális főkönyvi kiegyenlítések lap további lehetőségeket nyújt a szűrésre és a tranzakciók kijelölésére. Ahhoz, hogy a speciális főkönyvi kiegyenlítések lapot engedélyezze, kövesse az alábbi lépéseket.

1. Válassza a **Főkönyv** \>**Főkönyv beállítása** \>**Főkönyv paraméterei** lehetőséget. 
2. A **Főkönyvi kiegyenlítések** lapon állítsa a **Speciális főkönyvi kiegyenlítés** lehetőséget **Igen** állapotra a speciális főkönyvi kiegyenlítés funkció bekapcsolásához. A speciális **Főkönyvi kiegyenlítések** lapot a **Főkönyvi kiegyenlítések** **Időszakos feladatok** részben történő kiválasztásakor használhatja. 
3. Meg kell adnia azoknak a számláknak a listáját, amelyet a főkönyvi kiegyenlítésekhez szeretne használni minde egyes számlatükör esetében. Ez a lista azoknak a tranzakciók listájának szűréséhez használatos, amelyek a **Főkönyvi kiegyenlítések** oldalon jelennek meg. A **Számlatükör** listán válasszon ki egy számlatükröt, és válassza az **Új** lehetőséget az új fiókok hozzáadásához a listához.

## <a name="settle-transactions-by-using-the-advanced-ledger-settlements-page"></a>Tranzakciók kiegyenlítése a speciális főkönyvi kiegyenlítések lapjának használatával

Főkönyvi tranzakciók kiegyenlítéséhez kövesse az alábbi lépéseket.

1. Válassza a **Főkönyv** \>**Időszaki feladatok** \>**Főkönyvi kiegyenlítések** lehetőséget.
2. Az oldal tetején állítsa be a szűrőket:

    - Válasszon egy dátumtartományt, vagy válassza a **Dátumtartomány kódja** elemet, amely automatikusan kitölti a dátumtartományt.
    - Módosíthatja a feladási réteget szükség szerint.
    - A főkönyvi számla és dimenziók külön-külön megjelenítéséhez válasszon egy pénzügyi dimenziókészletet.

3. Válassza a **Tranzakciók megjelenítése** beállítást minden olyan tranzakció megjelenítéséhez, amely megfelel a beállított szűrőknek és a számlák listájának, amelyet a számlatükör lista beállításakor meghatározott az előző részben. Ha módosítja a szűrők vagy a dimenziókészletek bármelyikét, ki kell választania a **Tranzakciók megjelenítése** lehetőséget újra.
4. Válasszon ki egy vagy több sort, amelyet éppen figyelembe vesz a kiegyenlítéshez. A **Kijelölt összeg** mező értékét az oldal tetején növeli vagy csökkenti a kijelölt sorok teljes összege.
5. Miután befejezte a tranzakciók kijelölését, jelölje be a **Kijelöltek megjelölése** lehetőséget. Megjelenik egy pipa a **Megjelölt** oszlopban minden kiválasztott tranzakcióhoz. Ezenfelül a **Megjelölt összeg** mező értékét a rács felett növeli vagy csökkenti a megjelölt sorok teljes összege.
6. Ha a **Megjelölt összeg** értéke **0** (nulla), válassza a **Megjelölt tranzakciók kiegyenlítése** lehetőséget. A megjelölt tranzakciók állapota **Kiegyenlített** értékre frissül.

## <a name="make-transactions-easier-to-find"></a>Tranzakciók megkeresésének egyszerűbbé tétele

A **Főkönyvi kiegyenlítések** a lap tartalmazza a lehetőségeket, amelyek megkönnyítik a tranzakciók megjelenítését, amelyekre a kiegyenlítéshez szüksége van.

- A **Kijelöltek megjelölésének megszüntetése** gomb törli a **Megjelölt** mezőt minden olyan sorban, amely ki van választva.
- A **Megjelölt** szűrő lehetővé teszi a tranzakciók szűrését az alapján, hogy a **Megjelölt** mezőjük kijelölt vagy törölt.
- Az **Állapot** szűrő lehetővé teszi a tranzakciók szűrését az alapján, hogy állapotuk **Kiegyenlített** vagy **Ki nem egyenlített**.
- A **Rendezés abszolút összeg szerint** gomb lehetővé teszi, hogy az összegeket abszolút érték szerint rendezze, így csoportosíthatja azokat a tartozásokat és követeléseket, amelyek összege egyenlő.

## <a name="reverse-a-settlement"></a>Kiegyenlítés sztornírozása

A tévedésből létrehozott kiegyenlítések sztornírozhatók.

1. Kövesse az 1–3. lépést a „Tranzakciók kiegyenlítése a speciális főkönyvi kiegyenlítések lap használatával” című szakaszban, hogy a keresett tranzakciókat megjelenítse.
2. Az **Állapot** szűrőben válassza ki a **Kiegyenlített** lehetőséget.
3. Válasszon ki egy vagy több sort, amelyet éppen figyelembe vesz a sztornírozáshoz. A **Kijelölt összeg** mező értékét az oldal tetején növeli vagy csökkenti a kijelölt sorok teljes összege.
4. Miután befejezte a tranzakciók kijelölését, jelölje be a **Kijelöltek megjelölése** lehetőséget. Megjelenik egy pipa a **Megjelölt** oszlopban minden kiválasztott tranzakcióhoz. Ezenfelül a **Megjelölt összeg** mező értékét az oldal tetején növeli vagy csökkenti a megjelölt sorok teljes összege.
5. Ha a **Megjelölt összeg** értéke **0** (nulla), válassza a **Megjelölt tranzakciók sztornírozása** lehetőséget. A megjelölt tranzakciók állapota **Ki nem egyenlített** értékre frissül.

## <a name="update-the-list-of-accounts-that-are-included-in-the-list-of-transactions"></a>A tranzakciólistában szereplő számlák listájának frissítése

Válassza a **Főkönyvi kiegyenlítési számlák** lehetőséget egy párbeszédpanel megnyitásához, ahol aztán szerkeszteni lehet a számlákat, amelyek szerepelnek a tranzakciók listájában. Válassza az **Új** lehetőséget, ha új számlákat szeretne a listához adni. Ez a lista azoknak a tranzakciók listájának szűréséhez használatos, amelyek a **Főkönyvi kiegyenlítések** oldalon jelennek meg.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]