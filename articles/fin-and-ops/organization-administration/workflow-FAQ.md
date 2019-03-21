---
title: Munkafolyamat GYIK
description: Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/01/2019
ms.locfileid: "773213"
---
# <a name="workflow-system"></a>Munkafolyamat-rendszer

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.

## <a name="notifications"></a>Értesítések

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Miért érkeznik a több értesítés egy munkaelem elutasítása esetén?
Egy munkaelem elutasításakor, a munkatétel elutasítottként lesz befejezve. Egy másik munkatétel lesz létrehozva és kiosztva a létrehozónak. Ez azt jelenti, hogy van egy értesítés az elutasított munka létrehozójának, és egy külön értesítés az új „módosítás kérése” munkaelemhez hozzárendelt felhasználónak. 

Minden értesítés egy másik meunelemhez tartozik, de a hasonlóság megtévesztő lehet. Tervezzük ennek fejlesztését egy későbbi kiadásban.
