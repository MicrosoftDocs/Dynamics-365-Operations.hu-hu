---
title: Jelentési funkciók
description: Ez a témakör a Microsoft Dynamics 365 Human Resources jelentések testreszabását vagy új jelentések létrehozását ismerteti.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4649005d6944c05310fc40f0dfd10519b2739ff0
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693976"
---
# <a name="reporting-options"></a>Jelentési funkciók


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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
