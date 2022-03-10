---
title: Okkódok beállítása
description: A Dynamics 365 Human Resources okkódokat használ annak elmagyarázása érdekében, hogy miért változnak az alkalmazottak juttatásai.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a30a59a648d54eda771845b8bee52df43987d3d1
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068284"
---
# <a name="set-up-reason-codes"></a>Okkódok beállítása


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A Dynamics 365 Human Resources okkódokat használ annak elmagyarázása érdekében, hogy miért változnak az alkalmazottak juttatásai.

> [!NOTE]
> 2021 januárjától az okkódok a **Személyzetkezelés** munkaterületre kerültek a **Juttatáskezelés** munkaterület helyett. További információk: [Okkódok manuális áttelepítése a Személyzetkezelés munkaterületre](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Okkódok létrehozása

1. A **Személyzetkezelés** munkaterületen (vagy a **Juttatáskezelés** munkaterületen, ha az okkódok nincsenek áttelepítve), válassza a **Hivatkozások** lehetőséget, majd válassza az **Okkódok** lehetőséget.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Okkód** | Egyedi név, amellyel azonosíthatja, hogy az alkalmazott milyen okból módosítja a juttatási konstrukciós regisztrációját. |
   | **Leírás** | Az okkód leírása. |

4. Az **Alkalmazandó forgatókönyvek** pontban állítsa a **Juttatáskezelés** lehetőséget **Igen** értékre. (Nem alkalmazandó, ha az okkódokat nem telepítette át a **Személyzetkezelés** munkaterületre.)

5. Válassza a **Mentés** lehetőséget.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Okkódok manuális áttelepítése a Személyzetkezelés munkaterületre

2021 januárjában az okkódok a **Személyzetkezelés** munkaterületre kerültek a **Juttatáskezelés** munkaterület helyett. A legtöbb okkódadat automatikusan áttelepítésre kerül a környezetben. Előfordulhat, hogy néhány okkódadat nem kerül áttelepítésre. Például az okkódok most már legfeljebb 15 karakterből állhatnak, így a 15 karakternél hosszabb okkódok nem kerülnek automatikusan áttelepítésre.

A **Juttatáskezelés** munkaterület **Hivatkozások** lapján megjelenik egy dokumentum, amely tájékoztatja az áttelepítésről, illetve arról, hogy van-e olyan okkód, amely nem került áttelepítésre.

1. Az **Okkódok** lehetőségben megtekintheti az áttelepítési állapottal kapcsolatos részleteket.

   [![Okkódok.](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Válasszon ki egy olyan okkódot, amelynél az áttelepítés sikertelen volt.

   [![Okkód áttelepítési állapota.](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Válassza az **Okkód áttelepítése** lehetőséget.

   [![Okkód áttelepítése.](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. A **Juttatási okkód áttelepítése** ablakban két lehetőség áll rendelkezésre a Személyzetkezelés okkódjának leképezésére:

   - A Személyzetkezelésben létező okkód használatához válasszon egyet a **Meglévő okkód használata** legördülő menüből.
     > [!NOTE]
     > A Személyzetkezelés eszközben csak akkor használhat meglévő okkódot, ha még nincs rá áttelepítve másik Juttatáskezelési okkód.
   - Ha új okkódot kell létrehozni a Személyzetkezelés eszközben, írjon be egy újat az **Új okkód** pontba, majd adjon meg egy leírást az **Új leírás** lehetőségben.

   [![Leképezés a Személyzetkezelés egy okkódjára.](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

Miután megtörtént az okkódok áttelepítése a Személyzetkezelés eszközbe, a Juttatáskezelés funkcióban való használatuk beállítása automatikusan **Igen** lesz.

[![Okkód használata a Juttatáskezelés eszközben.](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
