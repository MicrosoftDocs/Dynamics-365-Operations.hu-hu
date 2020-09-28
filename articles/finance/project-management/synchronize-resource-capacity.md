---
title: Erőforrás-kapacitás szinkronizálása
description: Ez a témakör azt mutatja be, hogyan lehet szinkronizálni az erőforrás kapacitását a naptárak és a projektek között.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27b6fde91a72e37bb2712daba765032322cbd4e9
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760562"
---
# <a name="synchronize-resource-capacity"></a>Erőforrás-kapacitás szinkronizálása

[!include [banner](../includes/banner.md)]

Az erőforrás-szinkronizálási folyamatok segítségével garantálható, hogy a naptár- és alapnaptáradatok a projekterőforrás-ütemezéssel összhangba kerülnek. Ha a naptár módosult, a folyamatok elvégzik a szükséges frissítéseket a projekterőforrások ütemezéséhez. A folyamatok a teljesítmény javításában is segítenek, mivel a naptár-erőforrásadatok szinkronizálása előre megtörténik. Ezért az erőforrás-ütemezési információk módosításai gyorsabban megtörténnek. Javasoljuk, hogy ne egyesével, hanem kötegként ütemezze a folyamatokat. Ellenkező esetben fennáll a kockázata annak, hogy valaki elfelejti az utolsó adatszinkronizálás inkluzív időpontját. Ha az inkluzív időpontokat nem használták, szünetek fordulhatnak elő a dátumszinkronizálás során.

![Naptár szinkronizálása](./media/projectresourcing04-1024x471.jpg)

## <a name="synchronize-resource-capacity-roll-ups"></a>Erőforrás kapacitás-összesítéseinek szinkronizálása

A szinkronizálási folyamat arra szolgál, hogy az összes naptári erőforrásadatot szinkronizálja. Ez az információ alapnaptár adatokat tartalmaz a projekt Erőforrásnaptár kapacitás tábláját ért bármely módosításról. Ha új erőforrások kerülnek a projekthez, a szinkronizálás biztosítja a frissített naptáradatok elérhetőségét. Ez a szinkronizálás bármikor megtehető.

Köteg használatát javasoljuk. A beállítások a kapacitásfoglalások szinkronizálása során érhető el.

1. Válassza a **Projektvezetés és könyvelés** &gt; **Időszakos** &gt; **Kapacitásszinkronizálás** &gt; **Erőforrás kapacitás-összesítéseinek szinkronizálása** lehetőségeket.
2. Állítsa be az alábbi táblázatban található lehetőségeket.

    | Lehetőség      | Leírás |
    |-------------|-------------|
    | Időszak kódja | Bejelölheti a Főkönyvi dátumtartomány kódját, és beállíthatja a szinkronizálási folyamat kezdő és záró dátumát erőforráskapacitás-összesítésekhez. |
    | Kezdő dátum  | Adja meg a szinkronizálási folyamat kezdő dátumát erőforráskapacitás-összesítésekhez. |
    | Befejezés    | Adja meg a szinkronizálási folyamat záró dátumát erőforráskapacitás-összesítésekhez. |

[![Szinkronizálási folyamat](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)
