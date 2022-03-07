---
title: Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz
description: Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat hozzárendelni az üzletekhez vagy munkavállalókhoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 18f13fb1754b2740b8447a67f09320651b0ca4003c6f46c6d4668e5159ae1a2d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730827"
---
# <a name="assign-task-lists-to-stores-or-employees"></a>Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz

[!include [banner](includes/banner.md)]

Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat hozzárendelni az üzletekhez vagy munkavállalókhoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A Feladatkezelés a Dynamics 365 Commerce alkalmazásban lehetővé teszi egy feladatlista hozzárendelését több üzlethez vagy alkalmazotthoz, illetve üzletekhez és alkalmazottak kombinációjához is. Például egy 20 üzletet kezelő területi vezető a **Felkészülés az ünnepi időszakra** feladatlistáját mind a 20 üzlethez társítani szeretné.

## <a name="start-the-task-list-assignment-process"></a>A Feladatlista-hozzárendelési folyamat elindítása

A Feladatlista hozzárendelési folyamatának megkezdéséhez hajtsa végre az alábbi lépéseket.

1. Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelés adminisztrációja** lehetőséget.
1. Válassza ki a hozzárendelni kívánt feladatlistát.
1. Válassz a **Folyamat indítása** lehetőséget.
1. A **Folyamat indítása** párbeszédpanelen az **Általános** lapon a **Folyamat neve** mezőbe írjon be egy nevet (például **Keleti területi üzletei**).
1. Válasszon ki egy dátumot a **Céldátum** mezőben.
1. A Feladatlista üzletekhez történő hozzárendeléséhez az **üzletek** lapon a **Szervezeti hierarchia** szűrője segítségével keresse meg és válassza ki az üzleteket.

    A Feladatlista alkalmazottakhoz rendeléséhez a **Dolgozók** lapon keresse meg és válassza ki az alkalmazottakat.

1. A folyamat az **OK** gombot választva indítható el. A feladatlista a kiválasztott üzletekhez vagy alkalmazottakhoz van rendelve.

A következő ábra egy példát mutat be az üzletek megtalálására és kiválasztására a **Folyamat indítása** párbeszédpanelen.

![Üzletek keresése és kiválasztása a Folyamat indítása párbeszédpanelen.](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a>Feladatlisták társítása ismétlődő alapon

A kiskereskedőnek néha ismétlődő feladatai is vannak, például a „Csütörtöki zárási ellenőrzőlista” vagy „A hónap első napjának ellenőrzőlistája”. Ezért előfordulhat, hogy a feladatlistát ismétlődően szeretné hozzárendelni.

1. Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelés adminisztrációja** lehetőséget.
1. Válassza ki a hozzárendelni kívánt feladatlistát.
1. Válassz a **Folyamat indítása** lehetőséget.
1. A **Folyamat indítása** párbeszédpanelen az **Általános** lapon a **Folyamat neve** mezőbe írjon be egy nevet.
1. Állítsa az **Ismétlődés** beállítást **Igen** értékre.
1. Írjon be a napok számár az **Ismétlődés céldátumának eltolása napokban** mezőbe. Ha például a **4** értéket adja meg, akkor a céldátum az ismétlődés dátuma plusz négy nap.
1. A **Futtatás a háttérben** lapon válassz az **Ismétlődés** elemet.
1. Az **Ismétlődés definiálása** párbeszédpanelen írja be a gyakorisági feltételeket, majd kattintson az **OK** gombra.

A következő ábra egy példát mutat be a gyakorisági feltételek megadására az **Ismétlődés definiálása** párbeszédpanelen.

![Gyakorisági feltételek megadása az Ismétlődés definiálása párbeszédpanelen.](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a>A feladatlista állapotának nyomon követése

Ha Ön egy területi vezető vagy üzletvezető, akkor lehet, hogy nyomon szeretné követni a több üzlethez vagy alkalmazotthoz rendelt feladatlisták állapotát. Ezután nyomon követheti azokat az üzleteket vagy dolgozókat, akik nem teljesítették a hozzájuk rendelt feladatokat időben. A Commerce háttériroda segítségével megtekintheti a feladatlisták állapotát, áthelyezheti a feladatokat, illetve módosíthatja egy feladat állapotát.

Ha nyomon szeretné követni a feladatlista állapotát az összes feladathoz, hajtsa végre az alábbi lépéseket.

1. Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelési folyamatok** lehetőséget.
1. Válassza a **Minden Feladatlista** lapot, amelyen megtekintheti a különböző üzletekhez társított összes feladatlista állapotát.

Ha nyomon szeretné követni a az összes önhöz rendelt feladat feladatlista állapotát az összes feladathoz, hajtsa végre az alábbi lépéseket.

1. Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelési folyamatok** lehetőséget.
1. Válassza a **Saját feladatok** vagy az **Összes feladat** lapot az Önhöz rendelt feladatok állapotának megtekintéséhez vagy frissítéséhez.

## <a name="additional-resources"></a>További erőforrások

[Feladatkezelés – áttekintés](task-mgmt-overview.md)

[Feladatkezelés konfigurálása](task-mgmt-configure.md)

[Feladatlisták létrehozása és feladatok hozzáadása](task-mgmt-create-lists.md)

[Feladatkezelés a pénztárban](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
