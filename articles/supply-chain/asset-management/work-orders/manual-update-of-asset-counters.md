---
title: Eszközök számlálóinak manuális frissítése
description: Ez a témakör az Eszközkezelésben használt eszközszámlálók manuális frissítését ismerteti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 74d840cbb064018560a6abc2823f520c2f3179ac42b149c0507c9421a4e73391
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776434"
---
# <a name="manual-update-of-asset-counters"></a>Eszközök számlálóinak manuális frissítése

[!include [banner](../../includes/banner.md)]



A számlálók egy tárgyi eszközre vonatkozó regisztrációk létrehozásához szükségesek, azoknak az eszköz üzemóráinak számára vonatkozóan, illetve a termelt mennyiség szerint.

Előfordulhat, hogy a számlálóhoz kiválasztott számlálótípus be van állítva a számlálóértékek öröklésére. Más szóval, az **Eszközök számlálók öröklése** beállítás értéke **igen** **Számlálók** lap **Általános** gyorslapján (**Eszközkezelés** > **Beállítások** > **Eszköztípusok** > **Számlálók**). Ebben az esetben az ilyen típusú új számláló sor létrehozásakor minden olyan származtatott eszköz automatikusan frissül, amely ugyanazt a számlálótípust használja.

A **Minden eszköz** lapon, az eszköz leolvasott értékei alapján hozhatja létre az eszköz óraszám- vagy mennyiségszámláló regisztrációit.

1. Válassza ki az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** lehetőséget.

2. Jelölje ki az eszközt, majd az **Eszköz** lap műveleti ablakában a **Megelőző** csoportban válassza ki a **Számlálók** elemet. Az **Eszközszámlálók** oldalon látható a kiválasztott eszközhöz korábban létrehozott számlálóregisztrációk listája.

3. Válassza ki az **Új** lehetőséget egy regisztráció létrehozásához. Az eszközazonosítót a program automatikusan beírja az **Eszköz** mezőbe.

4. A **Számláló** mezőben válassza ki a megfelelő számlálót. Csak az eszközön kiválasztott eszköztípushoz kapcsolódó számlálók érhetők el kiválasztásra. A program automatikusan beírja a kapcsolódó egységet az **Egység** mezőbe.

5. A **Regisztrált** mezőben válassza ki a számláló regisztrációjának dátumát és időpontját.

6. Az **Érték** mezőbe írja be az utolsó számláló regisztrációja utáni számot. Azt is megteheti, hogy az **Összesített érték** mezőbe beírja a számláló teljes számát.

Vegye figyelembe az alábbiakat:

- Ha egy eszközhöz fizikailag telepít új számlálót, akkor a módosítást regisztrálni kell az eszközön az **Eszközszámlálók** oldalon. Ezután két olyan regisztrációs sort kell létrehozni, amelyeknek azonosak az időbélyegei. Az első sornak a helyettesíteni kívánt számlálóhoz kell tartoznia. Jelölje be az új számlálóhoz kapcsolódó sorban a **Számláló alaphelyzetbe állítása** jelölőnégyzetet. Az **Összesen** mezőben lévő teljes szám az adott típusú számláló összes regisztrált értékének az összege.

- Ha a **Számláló alaphelyzetbe állítása** jelölőnégyzet be van jelölve egy olyan eszközön, amelyiknek az időköztípusa „Egyszer ettől...” vagy „Egyszer elérés után...”, akkor a számláló továbbra is aktív az új számlálósorban, mert külön számlálósor jön létre, és a rendszer az új számlálóval kezd újra.

Az alábbi ábra az **Eszköszámlálók** oldal egy példáját mutatja be.

![1. ábra](media/11-work-orders.png)

Az **Eszközszámlálók** oldalon (**Eszközkezelés** > **Lekérdezése** > **Eszközök** > **Eszközszámlálók**) egyszerre több eszközre vonatkozóan is lehet számlálókat regisztrálni.

>[!NOTE]
>Egy tartományt úgy állíthat be, hogy meghatározza az eltéréseket a manuális számlálóregisztrációk között. Azt is megadhatja, hogy milyen típusú üzenetet jelenítsen meg a program, ha a regisztrációk a meghatározott tartományon kívül esnek. Az számlálók beállításával kapcsolatos további információkat lásd: [Számlálók](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]