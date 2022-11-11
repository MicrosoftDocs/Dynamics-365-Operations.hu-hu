---
title: Optimalizált év végi zárás
description: Ez a témakör ismerteti az Év végi szolgáltatászárás optimalizálása bővítményt, amely elérhető a főkönyv év végi zárási folyamatához.
author: moaamer
ms.date: 11/02/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2022-11-28
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 41d0c2975341cf3d612cc36be348326e24e94f1b
ms.sourcegitcommit: 707957bb7bcd98faf2600eff1c98067901a0fb73
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/08/2022
ms.locfileid: "9749995"
---
# <a name="optimize-year-end-close"></a>Optimalizált év végi zárás

A 365 Pénzügy szolgáltatás év végi zárása bővítmény lehetővé teszi az év végi lezárás feldolgozását a Dynamics 365 Pénzügyi erőforrások Application Object Server- (AOS- Microsoft Dynamics) példányán kívülre. Mikroszolgáltatási technológiát használ. Az Év végi optimalizálás funkcióval járó juttatások közé tartozik a jobb teljesítmény és az SQL-adatbázisra gyakorolt minimális hatás az év végi lezárás feldolgozása során.

Az Év végi zárás optimalizálása funkció használatához a következő feladatokat kell elvégeznie:

1. Telepítse az Év végi szolgáltatászárás optimalizálása bővítményt Microsoft Dynamics a Lifecycle Service projektjéről.
2. Engedélyezze az **Év végi lezárás optimalizálása** funkciót a Funkciókezelésben.

> [!NOTE]
> A Pénzügyi erőforrások aktuális **év végi zárása akkor is használható, ha letiltja az Év végi** zárás optimalizálása funkciót a Szolgáltatáskezelésben.

## <a name="improved-performance"></a>Javított teljesítmény

Az **Év végi lezárás** optimalizálása funkció az év végi lezárás feldolgozásának felgyorsítására van kialakítva, különösen a nagy mennyiségű adatot feldolgozó vevők esetében. Amikor az év végi lezárás lefut egy szolgáltatáson, a nehéz feldolgozást a program berakodja a pénzügyi erőforrásokból, hogy csökkentse a feldolgozási időt, és felszabadítsa az erőforrásokat, amelyek hatással lehetnek más felhasználók napi műveleteire.

Az **Év végi lezárás** optimalizálása szolgáltatás a következő célok elérésében segít:

- A futási idő csökkentése az év végi zárás teljesítményének javítása érdekében.
- Csökkenti a más folyamatokra gyakorolt hatást az év végi zárási futtatás során.
- Az év végi eredmények jelentéskészítésének és helyesbítésének javítása, mivel az év végi zárási futtatás rövidebb időt vesz igénybe.

## <a name="new-options-and-visibility"></a>Új beállítások és láthatóság

Ha az **Év végi lezárás** optimalizálása funkció engedélyezve van, **·** **a** következő helyeken két új oszlop – az eredmények és az állapot – kerülnek be a következő helyekre:

- Az Év **végi záró** oldalon
- Az Év végi **lezárás eredmény párbeszédpanelén**
- Az Év **végi záró** **sablonoldal mérleg pénzügyi dimenziójának átviteli beállításai**

Az alábbi ábra **az** **Év** végi bezárás lap Eredmény és **állapot oszlopait mutatja** be. Az Eredmények oszlopban **az** Eredmények hivatkozással **nyithatja** meg az év végi lezárás eredményeit. Az **Állapot** oszlop az év végi zárási folyamat aktuális állapotát mutatja. Ebből következően az új oszlopokban látható lesz az év végi zárási folyamat előrehaladása.

[![Eredmények és állapot oszlopok az Év végi záró lapon.](./media/Yearendclose.jpg)](./media/Yearendclose.jpg)

Továbbá ha **az Év végi lezárás optimalizálása funkció engedélyezve van, akkor a** **Mérleg pénzügyi dimenziók gyorslap** elérhetővé válik az év végi záró sablonoldalon **.** Ez a gyorslap a mérleg pénzügyi dimenzióinak részletes megadására használható az év bezárásakor. Ez a képesség párhuzamos azokkal a képességekkel, amelyek már elérhetők az eredményszámlák számára.

## <a name="architecture-and-data-flow"></a>Architektúra és az adatforgalom

**Ha** az Év végi zárás optimalizálása funkciót szeretné használni, és az év végi zárat egy mikroszolgáltatáson szeretné futtatni, telepítenie kell az Év végi szolgáltatászárás optimalizálása bővítményt a Lifecycle Services **szolgáltatásból**, majd engedélyeznie kell az Év végi zárás optimalizálása funkciót a Szolgáltatáskezelésben.

Az alábbi ábra bemutatja, hogy az év végi feldolgozás ellenőrzi, hogy telepítve van-e a bővítmény, és engedélyezve van-e a funkció. Ha mindkét előfeltétel teljesül, az év végi zárás a mikroszolgáltatáson megy le.

[![Adatáramlási diagram.](./media/Lifecycle-services.jpg)](./media/Lifecycle-services.jpg)

## <a name="high-level-flow-for-year-end-close-processing"></a>Felső szintű folyamat az év végi lezárás feldolgozásához

1. Az év végi lezárási folyamat a Pénzügy modulban kezdődik, **\> a főkönyvi időszak lezárási \> év végi zárása során**. A folyamat létrehozza a lezárt jogi személyek kötegelt feladatainak és záró feladatainak lezárását.
2. Az év végi zárás meghatározza, hogy az év végi zárást a mikroszolgáltatáson vagy az aktuális zárási logikán kell futtatni.

    - Ha a Lifecycle Services szolgáltatásban telepítve van az Év végi szolgáltatászárás optimalizálása bővítmény, **és** a Szolgáltatáskezelésben engedélyezve van az Év végi zárás funkció, akkor az év végi zárás a mikroszolgáltatáson fog futni.

        1. Az Optimalizálás év végi zárása funkció minden lezárt jogi személyhez létrehoz egy év végi záró szerviz feladatot, majd futtatja az év végi zárása logikát. A mikroszolgáltatás év végi zárul.
        2. A pénzügyek a mikroszolgáltatás év végi zárását figyelik meg, hogy mikor fejeződött be a mikroservice. A program ezután **frissíti az év végi zárás eredményeit a Pénzügy év végi** záróoldalán.

    - Ellenkező esetben az év végi lezárás az aktuális zárási logikán fog futni.
