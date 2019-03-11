---
title: Jelentéskészítési beállítások a Talent szolgáltatásban
description: Ez a témakör ismerteti a probléma megoldását, ahol a vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304740"
---
# <a name="reporting-options-in-talent"></a>Jelentéskészítési lehetőségek a Talent szolgáltatásban

[!include [banner](includes/banner.md)]

**Környezet részletes adatai**

A probléma minden környezetre vonatkozik.

**Tünet**

A vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni.

**Kibocsátás**

A felhasználó nem tudja testreszabni a beágyazott Microsoft Power BI jelentéseket.

**Megoldás**

- A Core HR szolgáltatás adatairól, amelyek a Common Data Service for Apps szolgáltatásba kerül átvitelre, jelentés készülhet a PowerApps CDS csatlakozón keresztül a Power BI Desktop szolgáltatáshoz. Vegye figyelembe, hogy a Common Data Service for Apps tartalmazza a Core HR adatainak egy részhalmazást. Ha további tájékoztatást szeretne a Power BI irányítópultokról, lásd: [A Power BI jelentések és irányítópultok létrehozása a PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi) szolgáltatással.
- Elektronikus jelentéskészítés (ER) a Talent egyes jelentéseihez elérhető. A vevőközpontú testreszabások az ER konfigurációs beállításainak segítségével végezhetők el.
- Az adatokat exportálni lehet Microsoft Excel vagy Microsoft Word szolgáltatásba a Microsoft Office-integráción keresztül a Talent által kínált különböző adatentitások segítségével.

**Hosszú távú megoldás**

További Power BI beállítások lesznek elérhetők, és több adat és entitás lesz a Common Data Service for Apps része.
