---
title: Okkódok beállítása
description: A Dynamics 365 Human Resources okkódokat használ annak elmagyarázása érdekében, hogy miért változnak az alkalmazottak juttatásai.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae82c8312d344f5380adec8413766304681a0a05
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112797"
---
# <a name="set-up-reason-codes"></a>Okkódok beállítása

A Dynamics 365 Human Resources okkódokat használ annak elmagyarázása érdekében, hogy miért változnak az alkalmazottak juttatásai.

> [!NOTE]
> 2021 januárjától az okkódok a **Személyzetkezelés** munkaterületre kerülnek a **Juttatáskezelés** munkaterület helyett. További információk: [Okkódok manuális áttelepítése a Személyzetkezelés munkaterületre](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Okkódok létrehozása

1. A **Személyzetkezelés** munkaterületen (vagy a **Juttatáskezelés** munkaterületen, ha az okkódok még nincsenek áttelepítve), válassza a **Hivatkozások** lehetőséget, majd válassza az **Okkódok** lehetőséget.

2. Válassza az **Új** lehetőséget.

3. Adjon meg értékeket a következő mezőkben:

   | Mező | Leírás |
   | --- | --- |
   | **Okkód** | Egyedi név, amellyel azonosíthatja, hogy az alkalmazott milyen okból módosítja a juttatási konstrukciós regisztrációját. |
   | **Leírás** | Az okkód leírása. |

4. Az **Alkalmazandó forgatókönyvek** pontban állítsa a **Juttatáskezelés** lehetőséget **Igen** értékre. (Nem alkalmazandó, ha az okkódokat még nem telepítette át a **Személyzetkezelés** munkaterületre.)

5. Válassza a **Mentés** lehetőséget.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Okkódok manuális áttelepítése a Személyzetkezelés munkaterületre

2021 januárjától az okkódok a **Személyzetkezelés** munkaterületre kerülnek a **Juttatáskezelés** munkaterület helyett. A legtöbb okkódadat automatikusan áttelepítésre kerül a környezetben. Előfordulhat, hogy néhány okkódadat nem kerül áttelepítésre. Például az okkódok most már legfeljebb 15 karakterből állhatnak, így a 15 karakternél hosszabb okkódok nem kerülnek automatikusan áttelepítésre.

A **Juttatáskezelés** munkaterület **Hivatkozások** lapján megjelenik egy dokumentum, amely tájékoztatja az áttelepítésről, illetve arról, hogy van-e olyan okkód, amely nem került áttelepítésre.

1. Az **Okkódok** lehetőségben megtekintheti az áttelepítési állapottal kapcsolatos részleteket.

   [![Okkódok](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Válasszon ki egy olyan okkódot, amelynél az áttelepítés sikertelen volt.

   [![Okkód áttelepítési állapota](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Válassza az **Okkód áttelepítése** lehetőséget.

   [![Okkód áttelepítése](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. A **Juttatási okkód áttelepítése** ablakban két lehetőség áll rendelkezésre a Személyzetkezelés okkódjának leképezésére:

   - A Személyzetkezelésben létező okkód használatához válasszon egyet a **Meglévő okkód használata** legördülő menüből.
     > [!NOTE]
     > A Személyzetkezelés eszközben csak akkor használhat meglévő okkódot, ha még nincs rá áttelepítve másik Juttatáskezelési okkód.
   - Ha új okkódot kell létrehozni a Személyzetkezelés eszközben, írjon be egy újat az **Új okkód** pontba, majd adjon meg egy leírást az **Új leírás** lehetőségben.

   [![Leképezés a Személyzetkezelés egy okkódjára](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

Miután megtörtént az okkódok áttelepítése a Személyzetkezelés eszközbe, a Juttatáskezelés funkcióban való használatuk beállítása automatikusan **Igen** lesz.

[![Okkód használata a Juttatáskezelés eszközben](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]