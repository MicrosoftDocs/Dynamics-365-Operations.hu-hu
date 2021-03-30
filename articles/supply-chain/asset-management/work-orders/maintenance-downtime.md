---
title: Karbantartás miatti üzemkimaradás munkarendelések esetén
description: Ez a témakör leírja, hogy a karbantartás miatti üzemkimaradás regisztrációkat a munkarendelésen kiválasztott eszközre vonatkozóan hogyan lehet létrehozni.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ba24ae9e82debf9a67761e4e2ca0817e1645db28
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209731"
---
# <a name="maintenance-downtime-for-work-orders"></a>Karbantartás miatti üzemkimaradás munkarendelések esetén

[!include [banner](../../includes/banner.md)]


A karbantartás miatti üzemkimaradás regisztrációkat a munkarendelésen kiválasztott eszközre vonatkozóan lehet létrehozni. Ez a képesség akkor lehet hasznos, ha a termelési területen egy vagy több gépen szeretné rögzíteni a karbantartás miatti üzemkimaradást. Először létre kell hoznia azokat a karbantartás miatti üzemkimaradásokat, amelyeket használni szeretne, például a **Meghibásodás** és a **Tervezett leállítás**. Ezt a lépést a **Karbantartás miatti üzemkimaradás okkódjai** oldalon teheti meg. Majd létrehozhatja a karbantartás miatti üzemkimaradás regisztrációkat a **Karbantartás miatti üzemkimaradás** helyen, és hozzáadhatja a megfelelő karbantartás miatti üzemkimaradás okkódokat.

## <a name="create-maintenance-downtime-reason-codes"></a>karbantartás miatti üzemkimaradás okkódjainak létrehozása

1. Válassza az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Karbantartás miatti üzemkimaradás okkódjai** lehetőséget.

2. Válassza az **Új** lehetőséget.

3. A **Karbantartás miatti üzemkimaradás okkódja** mezőben adjon meg egy azonosítót a karbantartás miatti üzemkimaradás okkódjához.

4. A **Név** mezőben adjon meg egy nevet.

5. Jelölje be a **KPI -k szerepeltetése** jelölőnégyzetet, ha az okkódot figyelembe kell venni az eszköz fő teljesítménymutatóinak (KPI) számítása során. A tervezett termelési leállások általában nem szerepelnek a KPI-számításokban, mivel ezek nem befolyásolják a várt teljesítményt.

6. Válassza a **Mentés** lehetőséget.

A lenti ábra a **Karbantartás miatti üzemkimaradási okkódok** oldalt szemlélteti.

![1. ábra](media/15-work-orders.png)

Miután létrehozta a használni kívánt karbantartás miatti üzemkimaradási okkódokat, létrehozhatja a munkarendelésekhez és a eszközökhöz tartozó karbantartás miatti üzemkimaradás regisztrációkat.


## <a name="create-maintenance-downtime-registrations"></a>karbantartás miatti üzemkimaradás regisztrációinak létrehozása

1. Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.

2. Válassza ki a munkarendelést, majd a Művelet panel **Munkarendelés** lapján az **Eszközök** csoportban válassz a **Karbantartási miatti üzemkimaradás** pontot.

3. Válassza az **Új** lehetőséget.

4. Dátum-és időintervallum definiálásához a karbantartási leállás regisztrálásához a **Kezdés** és **Befejezés** mezőkbe.

>[!NOTE]
>A **Befejezés** mező kihagyásakor a program automatikusan beszúrja az időtartamot órában az **Időtartam** mezőbe.

5. Válasszon egy okkódot a **karbantartás miatti üzemkimaradás okkódja** mezőben.

6. További regisztrációk hozzáadásához ismételje meg a 3–5. lépéseket.

7. Válassza a **Mentés** lehetőséget.

A következő ábrán egy karbantartás miatti üzemkimaradás regisztrációjának példája látható.

![2. ábra](media/16-work-orders.png)

A karbantartás miatti üzemkimaradások kiszámításához használt naptár a tárgyi eszközök és paraméterek beállításában megadott beállítástól függ. Ha ki van választva egy erőforrás egy eszközhöz az **Erőforrás** ,mezőben a **Tárgyi eszköz** gyorslapon az **Összes eszköz** oldalon, akkor a program a társított erőforráscsoport naptárát használja, ahogy az a következő ábrán látható.

![3. ábra](media/17-work-orders.png)

Ha az eszközhöz nincs kiválasztva erőforrás, akkor a program az **Eszközkezelés paraméterei** alatt kiválasztott naptárat használja a következő illusztrációnak megfelelően.

![4. ábra](media/18-work-orders.png)

Kattintson a **Vállalati eszközkezelés** > **Lekérdezések** > **Karbantartás miatti üzemkimaradás** lehetőségre az összes karbantartás miatti üzemkimaradás regisztráció megtekintéséhez.

>[!NOTE]
>Az **Eszközkezelés** modulban használt összes naptár a szervezeti felügyelet **Szervezeti adminisztráció** > **Beállítás** > **Naptárak** > **Naptárak** helyen van beállítva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]