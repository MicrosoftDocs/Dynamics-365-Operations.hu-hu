---
title: Jelentéskészítési beállítások a Talent szolgáltatásban
description: Ez a témakör ismerteti a probléma megoldását, ahol a vevő személyre akarja szabni a Microsoft Dynamics 365 for Talent jelentéseit vagy új jelentéseket akar létrehozni.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 7e00a6e4fc01f72e1ef2347e08754997135215ed
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518198"
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

- A Core HR szolgáltatás adatairól, amelyek a Common Data Service szolgáltatásba kerül átvitelre, jelentés készülhet a PowerApps Common Data Service csatlakozón keresztül a Power BI Desktop szolgáltatáshoz. Vegye figyelembe, hogy a Common Data Service tartalmazza a Core HR adatainak egy részhalmazást. Ha további tájékoztatást szeretne a Power BI irányítópultokról, lásd: [A Power BI jelentések és irányítópultok létrehozása a PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi) szolgáltatással.
- Elektronikus jelentéskészítés (ER) a Talent egyes jelentéseihez elérhető. A vevőközpontú testreszabások az ER konfigurációs beállításainak segítségével végezhetők el.
- Az adatokat exportálni lehet Microsoft Excel vagy Microsoft Word szolgáltatásba a Microsoft Office-integráción keresztül a Talent által kínált különböző adatentitások segítségével.

**Hosszú távú megoldás**

További Power BI beállítások lesznek elérhetők, és több adat és entitás lesz a Common Data Service része.
