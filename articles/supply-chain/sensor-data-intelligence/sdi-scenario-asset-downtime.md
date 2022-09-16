---
title: Az eszköz leállási esete
description: Ez a témakör a tárgyi eszközök leállási helyzetét írja le, amelynek segítségével nyomon követheti az eszközök elérhetőségét.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetObjectProductionStop
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 944818557deebed06c02c00fd69de6e8f08bda83
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428984"
---
# <a name="the-asset-downtime-scenario"></a>Az eszköz leállási esete

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Az eszköz leállási helyzet karbantartási leállási rekordot generál, ha egy géptől a legutóbbi jel be vétele óta egy megadott időhatáron belül nem érkezik jel. Az ilyen helyzetekben a gépet úgy kell beilleszkedni, hogy a gép működési ideje alatt rendszeresen küldjön egy jelet az Azure Azure-központnak, de nem küld jelet, ha a gép nem működik.

## <a name="set-up-the-asset-downtime-scenario"></a>Tárgyi eszközök leállási esetének beállítása

A következő lépések szerint állítsa be az eszköz *leállási* esetét az Ellátásilánc-kezelés eszközben.

1. Az Esetadatok **lap megnyitásához \>\> nyissa \>** meg az Eszközkezelés beállítása biztonsági adatintelligencia-eseteket **·**.
2. A Tárgyi eszközök **leállási** eset mezőben válassza **a Konfigurálás** lehetőséget az eset beállítási varázslóának megnyitásához.
3. Az Új **lapon** jelölje be az **Új** gombra, ha hozzá szeretne adni egy bővítményt a rácshoz. Ezután állítsa be a következő mezőket:

    - **Mérőazonosító** – adja meg a használatbanlott eszköz azonosítóját. (Ha a Pi Azure Azure online szimulátort használja, és a következőben leírtak szerint [beállította: Szimulált készlet beállítása teszteléshez](sdi-set-up-simulated-sensor.md), adja meg az *AssetDownTime értékét*.)
    - **Mérő leírása** – adja meg a mérő leírását.

4. Ismételje meg az előző lépést minden további, most hozzáadni kívánt mérővel. Bármikor vissza lehet jönni, és további fogatokat lehet hozzáadni.
5. Válassza ki **Következő** lehetőséget.
6. Az üzleti **rekord megfeleltetési** lapján **, a Társítások szakaszban** válassza ki a rekordot az előbb hozzáadott valamelyik hőmérséklethez.
7. Az Üzleti rekord **megfeleltetése** szakaszban válassza az Új **lehetőséget**, ha sort szeretne hozzáadni a rácshoz.
8. Az új sorban állítsa be **az Üzleti** rekord mezőt arra az erőforrásra, amely a kiválasztott figyelőt használja figyelésként. (Ha bemutatóadatokat használ, *válassza a AK-101, légi közlekedés az 1. sorhoz*.)
9. Válassza ki **Következő** lehetőséget.
10. Adja meg az **eszköz leállási küszöbértékét jelző** oldalon, hogy a rendszer meddig várjon az eszköz leállási értesítése előtt. A küszöbérték kétféleképpen definiálhat:

    - **Alapértelmezett küszöbérték (perc)** – a mező beállítása az alapértelmezett küszöbérték meghatározására. Ez az érték minden olyan erőforrásra érvényes, **ahol az Értesítési küszöbérték (perc) mező** két percnél kisebb értékre van állítva. A minimális érték *2* (perc).
    - **Küszöbérték annak meghatározásához, hogy a gép nem válaszol (perc)** – a rács minden olyan erőforrása esetében, amely nem szeretné használni az alapértelmezett küszöbértéket, írjon be egy felülbírálási értéket ebbe a mezőbe. Azok az erőforrások, amelyek **két perc vagy kevesebb küszöbérték használatára vannak beállítva, az Alapértelmezett küszöbérték (perc) beállítást használják** helyette.
11. Válassza ki **Következő** lehetőséget.
12. Válassza ki **a** beállítottmérőt a rács aktiváló lapján, majd válassza ki az Aktiválás **lehetőséget**. A rácsban aktivált mindegyik aktivált eszközhöz megjelenik egy pipa az Aktív **oszlopban**.
13. Válassza a **Befejezés** lehetőséget.

## <a name="work-with-the-asset-downtime-scenario"></a>A tárgyi eszközök leállási esetének használható

Ha egy eszköz nem érkezik visszajelként az eset konfigurációjában megadott küszöbértéken belül, a rendszer karbantartási leállási rekordot hoz létre az adott eszközhöz. A vezetőknek rendszeresen ellenőrizniük kell a leállási rekordokat (például minden műszak során egyszer), és minden egyes leállási idő regisztrációja esetén alkalmazzanak megfelelő okkódokat és záró időpontokat. A következő lépések szerint tekintse meg egy eszköz karbantartási leállási rekordjait:

1. Menjen az Eszközkezelés **> eszköz > eszközhöz**.
2. Keresse meg és válassza ki a vizsgálni kívánt eszközt. (Ha bemutatóadatokat használ, *válassza a AK-101*.)
3. A munkaablakban nyissa **meg** az Eszköz lapot, **·** **majd** a Munkarendelés csoportban válassza a Karbantartás leállási idő lehetőséget, hogy a kijelölt eszközhöz karbantartási leállásrekordok számára nyissa meg a lapot.
