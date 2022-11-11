---
title: Dynamics 365 Human Resources infrastruktúra-egyesítés ismert problémái
description: Ez a cikk felsorolja azokat a problémákat, amelyek a Microsoft Dynamics 365 Human Resources infrastruktúra-egyesítése során fordulhatnak elő.
author: twheeloc
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5f5981801317ad9647f57a0f68f9b67b592256ab
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752690"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-known-issues"></a>Dynamics 365 Human Resources infrastruktúra-egyesítés ismert problémái

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="shared-dataverse-environments"></a>Megosztott Dataverse környezetek

A kettős írási keretrendszer nem támogatja két pénzügyi és műveleti alkalmazáskörnyezet ugyanannak a környezetnek a kapcsolatát Dataverse. Ha olyan környezete van, Dataverse amely mindkét következő elemhez meg van osztva, vagy meg kell ismétlődnie a környezetben, Dataverse vagy fel kell osztania:

- Pénzügyi és műveleti alkalmazás
- Aktuális Emberi erőforrások környezet

## <a name="environment-type-requirements"></a>Környezettípus követelményei

Az áttelepítés előtt a következő környezettípusokra van szükség:

- Ha nincs önállóbox-környezete, létre kell hoznia egyet az áttelepítés ellenőrzéséhez.
- Ha több önálló termelési környezete van, akkor az egyiket át lehettelepíteni. A többi környezet jelölőnégyzetként való megjelöléséhez forduljon a Microsoft támogatási szolgálatához.

## <a name="teams-integration"></a>Teams-integráció

A Teams alkalmazásban jelenleg meglévő Emberi erőforrások alkalmazás egy megoldásra való áttolása Microsoft Power Platform folyamatban van. További tájékoztatás: [Human Resources alkalmazás a Teamsben](hr-admin-teams-leave-app.md).

