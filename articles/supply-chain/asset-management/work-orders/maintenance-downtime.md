---
title: Karbantartás miatti üzemkimaradás munkarendelések esetén
description: Ez a témakör azt ismerteti, hogyan lehet karbantartási leállási regisztrációkat létrehozni a munkarendelésben kiválasztott eszközre.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4a310152685f733093cc7e50404c23b6f24c40cc
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016652"
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

1. Kattintson az **Eszközkezelés munkarendelések** > **–** > **Minden munkarendelés vagy** aktív **munkarendelés elemre**.

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