---
title: Költség-visszaigazolások feldolgozása
description: Ez a témakör a nyugták optikai karakterfelismerésre (OCR) alapuló feldolgozásával kapcsolatban tartalmaz tájékoztatást. Ez a funkció azt a célt szolgálja, hogy javítsa a felhasználói élményt, amikor költségjelentéseket hoz létre a Microsoft Dynamics 365 Finance szolgáltatásban.
author: stevensporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 1ead9039de63e2cf4f3a7faddd1702b9614d7f99
ms.sourcegitcommit: 6aceca43c53c4dde46954c0b6b855d488eb44ed2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027903"
---
# <a name="public-preview-expense-receipt-processing"></a>Nyilvános előnézet: költség-visszaigazolások feldolgozása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


A kiadások bevitelét a nyugták optikai karakterfelismerés (OCR) segítségével történő feldolgozása jobbá tette. Ez a funkció azt a célt szolgálja, hogy javítsa a felhasználói élményt, amikor költségjelentéseket hoz létre.

## <a name="key-features"></a>Fő funkciók

- A kereskedő neve, a dátum és a teljes összeg a nyugtából megállapítható.
- A funkció megpróbálja egyeztetni a nem csatolt bevételeket a nem csatolt kiadási tranzakciókkal.
- A felhasználók manuálisan megadott kiadási tranzakciókat hozhatnak létre a nyugtákból.

## <a name="usage-examples"></a>Felhasználási példák

- **Hitelkártya-adatokat tartalmazó nyugták automatikus csatolása költségjelentés létrehozásakor.**

    1. Nyissa meg a **Költséggazdálkodás** munkaterületet.
    2. A **Nyugták** lapon ellenőrizze, hogy vannak-e nem csatolt nyugták. A nyugtákat a **Nyugták** lapon is fel lehet tölteni.
    3. A **Költségek** lapon ellenőrizze, hogy vannak-e nem csatolt költségek. A költség felügyelője általában a hitelkártya kiadójától importálja ezeket a költségeket.
    4. Jelölje ki az **Új költégjelentés** lehetőséget. Vegye észre, hogy a költségek és a most már a nyugták is a költségjelentés létrehozásakor is megadhatók. Ha a költséget és a nyugtákat is hozzáadja, akkor a program automatikusan egyezteti a kiadásokat a bevételekhez.

- **Költség létrehozása vagy költség egyeztetése nyugta alapján.**

    1. Egy költségjelentés **Nyugták** lapján a **Nyugták hozzáadása** lehetőség kiválasztásával csatoljon nyugtát.
    2. A nyugta feltöltött képe alatt vegye észre a **Létrehozás** és az **Egyeztetés** beállításokat.

        - Válassza a **Létrehozás** lehetőséget, ha manuálisan megadott kiadási tranzakciót szeretne létrehozni, és töltse ki a nyugtából megszerzett értékeket.
        - Ha az **Egyeztetés** lehetőséget választja, a rendszer megpróbál egy meglévő költséget egyeztetni a nyugta értékéhez.

## <a name="installation"></a>Telepítés

Ez a funkció együtt dolgozik a **Költségjelentések újragondolva** szolgáltatással, amely egyszerűsíti a költségek élményét.

Ha ezeket a speciális képességetek szeretné használni, telepítse a Microsoft Dynamics 365 Finance Expense Management Service beépülő modulját, és kapcsolja be a saját példányának funkcióit. A bővítményt a projektje Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásából éri el.

1. Jelentkezzen be a LCS-ba, majd nyissa meg a kívánt környezetet.
2. Lépjen a **Teljes részletek** elemre.
3. Válassza a **karbantartás** lehetőséget, vagy görgessen a **környezeti bővítmények** gyorslapra.
4. Válassza az **Új bővítmény telepítése** lehetőséget.
5. Válassza az **Expense Management Service** lehetőséget.
6. Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.
7. Válassza a **Telepítés** parancsot.

Kapcsolja be a következő funkciókat a **Funkció kezelése** munkaterületen:

- Költségjelentések újragondolva
- Automatikus egyeztetés és költség létrehozása nyugtából

A funkciók bekapcsolásakor a következő műveletek történnek:

- A meglévő **Költséggazdálkodás** munkaterületet az új munkaterülettel helyettesíti a program.
- A program hozzáad egy új menüelemet a költségmező láthatóságához.
- A korábbi **Költségjelentések** lapot továbbra is megnyithatja, ha a **Költségkezelés > Költségeim >Költségjelentések** elemre lép.
- A munkafolyamatok és az esetleges jóváhagyások továbbra is elviszik a meglévő költségjelentések lapra.
- A program a nyugtákat a Microsoft Azure Cognitive Services segítségével dolgozza fel, és a metaadatokat kinyeri, majd hozzáadja.
- Olyan beállítás van kiválasztva, amely lehetővé teszi az egyeztetett, nem csatolt nyugtákat tartalmazó költségjelentés létrehozását.
- Egy, a költségjelentésekhez kapcsolódó opció lehetővé teszi a költségsor létrehozását a nyugtából, vagy egy meglévő bevétel egyeztetésének megkísérlését egy meglévő költségsorral.

A Költségjelentések újragondolva szolgáltatással kapcsolatos további tudnivalókat lásd: [Költségjelentések újragondolva](ExpenseWorkspaceNew.md).

## <a name="frequently-asked-questions"></a>Gyakori kérdések

**Felhasználja-e a Microsoft az adataimat a modelljeiben?**

Nem, a Microsoft egy általános gépi tanulási modellt épített ki a nyugtafeldolgozási szolgáltatáshoz. Ez a modell nem a feltöltött nyugtákon alapul.

**Hol érhető el a funkció, és hogyan dolgozzák fel?**

Jelenleg az Egyesült Államok támogatott.

**Hová kerülnek a nyugtáim?**

A Finance kapcsolatba lép a Cognitive Services szolgáltatással a mezőadatok kinyeréséhez. A Cognitive Services legfeljebb 24 óráig őrzi meg a nyugta egy példányát. A feldolgozás befejezése után a Cognitive Services eltávolítja a nyugtát. A Finance továbbra is tárolja a nyugtát.

További tudnivalókért lásd: [A nyugta megértésének engedélyezése a Form Recognizer új képességével](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).
