---
title: Jelentési funkciók
description: Ez a cikk ismerteti a probléma megoldását, ahol a vevő személyre kívánja szabni a Microsoft Dynamics 365 Human Resources jelentéseit vagy új jelentéseket kíván létrehozni.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 66581331dceacc1c0fa1816bf336339693db5339
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463286"
---
# <a name="reporting-options"></a>Jelentési funkciók

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**Környezet részletes adatai**

A probléma minden környezetre vonatkozik.

**Tünet**

A vevő személyre akarja szabni a Microsoft Dynamics 365 Human Resources jelentéseit vagy új jelentéseket akar létrehozni.

**Kiadás**

A felhasználó nem tudja testreszabni a beágyazott Microsoft Power BI jelentéseket.

**Megoldás**

- A Human Resources szolgáltatás Dataverse szolgáltatásba továbbított adatairól jelentés készíthető a Power Apps Dataverse csatlakozón keresztül a Power BI Desktop szolgáltatáshoz. Vegye figyelembe, hogy a Dataverse a Human Resources adatainak részhalmazát tartalmazza. Ha további tájékoztatást szeretne a Power BI szolgáltatásról és irányítópultokról, lásd: [A Power BI jelentések és irányítópultok létrehozása a Power Apps Common Data Service szolgáltatással](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).
- Az elektronikus jelentéskészítés (ER) a Human Resources egyes jelentéseihez érhető el. A vevőközpontú testreszabások az ER konfigurációs beállításainak segítségével végezhetők el.
- Az adatokat exportálni lehet a Microsoft Excel vagy a Microsoft Word alkalmazásba a Microsoft Office-integráción keresztül a Human Resources által kínált különböző adatentitások segítségével.

**Hosszú távú megoldás**

További Power BI beállítások lesznek elérhetők, és több adat és entitás lesz a Dataverse része.


[!INCLUDE[footer-include](../includes/footer-banner.md)]