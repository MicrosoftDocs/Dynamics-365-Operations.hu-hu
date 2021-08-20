---
title: Szabályok
description: Ez a témakör leírja, hogyan kell létrehozni konvenciókat annak megállapítására, hogy a költségeket hogyan kell elszámolni a Global Inventory Accounting szolgáltatásban.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2d629b082b423edf417714b8362be3364bc861e78f62d430a4d7083b8c49611a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773417"
---
# <a name="conventions"></a>Szabályok

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

A konvenció a rendszer viselkedését befolyásoló irányelvek tárolója. Az üzleti követelmények alapján meg kell határoznia az egyezményeket a különböző politikák kombinációjával, amelyek meghatározzák, hogyan kell a költségeket a Global Inventory Accounting szolgáltatásban elszámolni. Az egyes konvenciókat egy vagy több főkönyvvel társíthatja, hogy biztosítsa a főkönyvekben alkalmazott számviteli irányelvek következetességét.

A konvenciók beállításához lépjen a **Global inventory accounting \> Beállítás \> Konvencióihoz**. Állítsa be a következő mezőket minden egyes konvenciónál:

- **Név** – Írja be a konvenció nevét.
- **Leírás** – Adja meg a konvenció leírását.
- **Költségobjektum-házirend** – Költségobjektum-irányelv kiválasztása. Ezek a szabályzatok határozzák meg a rendszer által a készletérték kiszámítására és fenntartására használt részletességi szintet. Ehhez a következő előre meghatározott lehetőségek állnak rendelkezésre:

    - Termék
    - Termék – Webhely
    - Termék – Telephely – Raktár

    Ha például a *Termék – Webhely* lehetőséget választja minden készletmozgáshoz (be- vagy kiáramláshoz), a rendszer kiszámítja és fenntartja az egyes termékek készletköltségét a telephely szintjén. Ezért az alacsonyabb szintű készletmozgások, például a raktári szint, nem befolyásolják a készlet értékét. (A raktárszintű átvitelre példa a telephely két raktára közötti cikkátadás.) Hasonlóképpen, a készletköltséget nem tekintheti meg alacsonyabb szinten, például a raktári szinten.

- **Bemeneti mérték alapirányelv** – Bemeneti mérték alapirányelv kiválasztása. Ezek a szabályzatok határozzák meg a leltárszámlára beáramló költségeket és a felszámítandó költségeket. A következő lehetőségek relevánsak a kereskedelmi vállalatok számára:

    - **Normál előzmény** – Az összes költségösszetevő a készletszámlára áramlik.
    - **Standard** – A standard költség a készletszámlákba áramlik, és az alkalmazott költség és a tényleges költségek közötti különbséget a varianciaszámlákra terhelik. Ha *Standard* bemeneti mérési alapszabályt szeretne létrehozni, először létre kell hoznia egy árlistát, ahol az irányelv megkeresheti az elem szokásos költségét.
    - **Árlisták** – A Global Inventory Accounting támogatja a cikkárak több jogi személytől történő lekérését. Megadhat egy árlistát, amelyet a bemeneti mérési alapirányelve fog használni. Ily módon a rendszer tudni fogja, hol keresse fel a cikk árát. Kövesse az alábbi lépéseket az árlisták beállításához:

        1. A **Név** mezőben adjon meg egy nevet.
        1. Adjon meg egy leírást a **Leírás** mezőben.
        1. A **Költségszámítási típus** mezőben válasszon egy költségszámítási típust (*Standard* költség vagy *Tervezett költség*).
        1. Az **Ártípus** mezőben válasszon egy ártípust (*Költség*, *Vásárlás* vagy *Eladási ár*).
        1. Adjon hozzá költségszámítási verziót.
        1. A Műveletablakban válassza az **Ár** lehetőséget az árlistában szereplő cikkárak érvényesítéséhez.

- **Költségforgalom-feltételezési irányelv** – Válasszon költségforgalom-feltételezési irányelvet. Ezek a szabályzatok határozzák meg, hogy a költségeket hogyan távolítják el a készletből, és hogyan számolják el az eladott áruk költségét. Ehhez a következő előre meghatározott lehetőségek állnak rendelkezésre:

    - Átlag
    - Specifikus – Köteg

    > [!NOTE]
    > A Global Inventory Accounting egy végleges leltározási rendszer. Ezért a rendszer tranzakcióról tranzakcióra követi nyomon a készlet értékét.

- **Költségelem-irányelv** – A költségelem-irányelveket erre a területre kattintva határozhatja meg. A *költségelem* egy esemény által felhasznált erőforrás költsége. A költségelemek segítségével nyomon követheti és kategorizálhatja a költségeket. Költségelem-irányelvek létrehozásához adjon meg adatokat a következő helyeken:

    - **Név** mezőe
    - **Leírás** mezője
    - **Költségösszetevői** lista
    - **Szabályok** rács

    Ha nem szeretné tovább bontani a készlet értékét, akkor is létre kell hoznia egy költségelem-listát, amely egyetlen költségelemet tartalmazza. Ezután létre kell hoznia egy költségelem-házirendet, hogy az összes releváns mérési típust (költségösszetevőt) az adott költségelemhez rendelje.
