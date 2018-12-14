---
title: "Jelentéskészítési beállítások a Talent szolgáltatásban"
description: "Ez a témakör ismerteti a probléma megoldását, ahol a vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: hu-hu
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a>Jelentéskészítési beállítások a Talent szolgáltatásban

[!include [banner](includes/banner.md)]

**Környezet részletes adatai**

A probléma minden környezetre vonatkozik.

**Tünet**

A vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni.

**Probléma**

A felhasználó nem tudja testreszabni a beágyazott Microsoft Power BI jelentéseket.

**Megoldás**

- A Core HR szolgáltatás adatairól, amelyek a Common Data Service for Apps szolgáltatásba kerül átvitelre, jelentés készülhet a PowerApps CDS csatlakozón keresztül a Power BI Desktop szolgáltatáshoz. Vegye figyelembe, hogy a Common Data Service for Apps tartalmazza a Core HR adatainak egy részhalmazást. A Power BI szolgáltatással és az irányítópultokkal kapcsolatos további információkért lásd: [Power BI-jelentések és irányítópultok létrehozása PowerApps Common Data Service használatával](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).
- Elektronikus jelentéskészítés (ER) a Talent egyes jelentéseihez elérhető. A vevőközpontú testreszabások az ER konfigurációs beállításainak segítségével végezhetők el.
- Az adatokat exportálni lehet Microsoft Excel vagy Microsoft Word szolgáltatásba a Microsoft Office-integráción keresztül a Talent által kínált különböző adatentitások segítségével.

**Hosszú távú megoldás**

További Power BI-beállítások lesznek elérhetők, és több adat és entitás lesz a Common Data Service for Apps része.

