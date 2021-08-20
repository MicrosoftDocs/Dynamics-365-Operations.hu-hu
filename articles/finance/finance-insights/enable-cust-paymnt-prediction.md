---
title: Vevői fizetési előrejelzések engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni és konfigurálni a Vevői fizetési előrejelzések funkciót a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 0b945111f360838dfa35cddb916c4fb34a41f55bdd8f3095bd97c906b7dd3dd7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768891"
---
# <a name="enable-customer-payment-predictions-preview"></a>Vevői fizetési előrejelzések engedélyezése (előzetes verzió)

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni és konfigurálni a Vevői fizetési előrejelzések funkciót a pénzügyi elemzésekben. A funkció bekapcsolását a **Funkciókezelés** munkaterületen kapcsolja be, és adja meg a konfigurációs beállításokat a **Pénzügyi elemzési paraméterek** lapon. Ez a témakör olyan információkat is tartalmaz, amelyek segíthetnek a funkció hatékony használatában.

> [!NOTE]
> A következő lépések elvégzése előtt mindenképpen hajtsa végre az előfeltételeket a [Pénzügyi elemzések konfigurálása](configure-for-fin-insites.md) témakörben.

1. A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben. Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához. (Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('PayPredEnableFeature', 1)`

    > [!NOTE]
    > Hagyja ki ezt a lépést, ha a 10.0.20-as vagy újabb verziót használja, vagy ha Service Fabric-telepítést használ. A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára. Ha nem látja a funkciót a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni, keressen fel minket: <fiap@microsoft.com>. 

2. Kapcsolja be az Ügyfél fizetési elemzés funkciót:

    1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
    2. Keresse meg az **Ügyfél fizetési elemzés adatai (előzetes verzió)** nevű funkciót.
    3. Válassza az **Engedélyezés most** lehetőséget.

    Az Ügyfél fizetési elemzés funkciója be van kapcsolva, és készen áll a konfigurálásra.

3. Konfigurálja az Ügyfél fizetési elemzés funkciót:

    1. Nyissa meg a **Jóváírás és gyűjtemények \> Beállítás \> Pénzügyi elemzés \> Pénzügyi elemzés paraméterei** lehetőséget.

        [![A Pénzügyi elemzés paraméterei lap a funkció konfigurálása előtt.](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)

    2. A **Pénzügyi elemzési paraméterek** lap **Ügyfélfizetési elemzések** lapján válassza az **Előrejelzési modellhivatkozásban használt adatmezők megtekintése** lehetőséget az **Előrejelzési modell adatai** lap megnyitásához. Itt megtekintheti a mesterséges intelligencia (AI) előrejelzési modelljének létrehozásához használt mezők alapértelmezett listáját az ügyfelek fizetési előrejelzéseihez.

        Ha az előrejelzési modell létrehozásához az alapértelmezett mezőlistát szeretné használni, zárja be az **Előrejelzési modell adatmezői** lehetőséget, majd a **Pénzügyi elemzési paraméterek lapon** állítsa a **Szolgáltatás engedélyezése** beállítást **Igen** értékre.

    3. Adja meg a „nagyon későn” tranzakciós időszakot annak meghatározásához, hogy mit jelent a **Nagyon későn** előrejelzési gyűjtő a vállalkozás számára.

        Minden nyitott számla esetében a rendszer három gyűjtőben jelzi előre meg a fizetés valószínűségét: **Időben**, **Későn** és **Nagyon későn**.

        - **Időben** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek előre jelzett kifizetése a tranzakció esedékességi dátumán vagy előtte történik.
        - **Későn** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek a tranzakció esedékességi dátuma után, de a „nagyon késő” tranzakciós időszak kezdete előtt kerülnek kifizetésre.
        - **Nagyon későn** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek a „nagyon késő” tranzakciós időszak kezdete után kerülnek kifizetésre.

        > [!NOTE]
        > Ha módosítja a „nagyon későn” tranzakciós időszakot, és a **Későn küszöbérték módosítása** lehetőséget választja a vevői kifizetések előrejelzési modelljének létrehozása után, a meglévő előrejelzési modell törlődik, és egy új modell jön létre. Az új előrejelzési modell a tranzakciókat a „nagyon későn” időszakba mozgatja a definiáláshoz megadott beállítások alapján.

    4. Miután befejezte a „nagyon későn” tranzakciós időszak definiálását, válassza az **Előrejelzési modell létrehozása** lehetőséget az előrejelzési modell létrehozásához. Az **Előrejelzési modell** szakasz a **Pénzügyi elemzési paraméterek** lapon az előrejelzési modell állapotát mutatja.

        > [!NOTE]
        > Az előrejelzési modell létrehozása közben bármikor kiválaszthatja a **Modell létrehozásának visszaállítása** lehetőséget a folyamat újraindításához.

    A funkció most már konfigurálva van, és készen áll a használatra.

Miután a funkció be van kapcsolva és konfigurálva van, és az előrejelzési modell létrejött és működik, a **Pénzügyi elemzések paraméterei** lap **Előrejelzési modell** szakasza a modell pontosságát mutatja, ahogy az az alábbi ábrán is látható.

[![Az előrejelzési modell pontossága a Pénzügyi információk paraméterei oldalon.](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)

## <a name="release-details"></a>Kiadás adatai

A Finance Insights nyilvános előzetes verzió az Amerikai Egyesült Államokban, Európában és az Egyesült Királyságban is elérhető a próbaverzió telepítéshez. A Microsoft fokozatosan adja hozzá a további régiók támogatását.

A nyilvános előzetes verziójú funkciók csak 2. szintű tesztkörnyezetekben szabad bekapcsolni. A tesztkörnyezetben létrehozott telepítési és AI-modellek nem telepíthetők át éles környezetbe. További információ: [A Microsoft Dynamics 365 előzetes verziók kiegészítő használati feltételei](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
