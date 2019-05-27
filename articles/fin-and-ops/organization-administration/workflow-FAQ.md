---
title: Munkafolyamat GYIK
description: Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509291"
---
# <a name="workflow-system"></a>Munkafolyamat-rendszer

[!include [banner](../includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 for Finance and Operations munkafolyamat rendszerével kapcsolatos gyakori kérdéseket tartalmazza.

## <a name="notifications"></a>Értesítések

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Miért érkeznik a több értesítés egy munkaelem elutasítása esetén?
Egy munkaelem elutasításakor, a munkatétel elutasítottként lesz befejezve. Egy másik munkatétel lesz létrehozva és kiosztva a létrehozónak. Ez azt jelenti, hogy van egy értesítés az elutasított munka létrehozójának, és egy külön értesítés az új „módosítás kérése” munkaelemhez hozzárendelt felhasználónak. 

Minden értesítés egy másik meunelemhez tartozik, de a hasonlóság megtévesztő lehet. Tervezzük ennek fejlesztését egy későbbi kiadásban.

### <a name="why-are-my-workflow-exports-failing"></a>Miért nem sikerülnek a munkafolyamat-exportálásaim?
A munkafolyamat-exportálási funkcióra jelenleg korlátozás vonatkozik, amely megakadályozza, hogy a munkafolyamatok nevei túllépjék a 48 karaktert. Ha egy 48 karakternél hosszabb nevet használ, a „Kiszolgáló nem tudta hitelesíteni a kérelmet” hibát kap és/vagy nem lehetséges a fájlok fájltípus nélküli exportálása. A következő blogbejegyzés további részleteket nyújt: [Munkafolyamat exportálása](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).
