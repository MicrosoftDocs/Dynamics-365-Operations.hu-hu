---
title: Integrált helyek és raktárak
description: Ez a témakör a hely- és raktáradatok integrációját ismerteti a Finance and Operations és a Common Data Service között.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 4cf402e2811aaf92ddfa78eaf6d8887d88d93cbc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770988"
---
# <a name="integrated-sites-and-warehouses"></a>Integrált helyek és raktárak

[!include [banner](../includes/banner.md)]

Ez a témakör a hely- és raktáradatok integrációját ismerteti a Finance and Operations és a Common Data Service között. Az üzemeltetési helyszínek és a raktárak közös fogalmak az Supply Chain Management alkalmazásban. Ezek a vállalat ellátási láncának modellezésére használatosak.

## <a name="templates"></a>Sablonok

A Common Data Serviceintegrációjával ezekkel elvekkel és a hozzájuk kapcsolódó adatokkal a következő táblázatban található Common Data Service helyek és raktárak adatentitásai használhatók.

Finance and Operations alkalmazások | Egyéb Dynamics 365 alkalmazások | Leírás
--------------------------|---------------------------|---
Webhelyek | msdyn_operationalsites | 
Raktárak | msdyn_warehouses | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

