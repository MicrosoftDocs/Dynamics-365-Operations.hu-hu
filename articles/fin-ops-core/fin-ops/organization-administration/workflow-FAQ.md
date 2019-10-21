---
title: Munkafolyamat GYIK
description: Ez a témakör a munkafolyamat-rendszerrel kapcsolatos gyakori kérdéseket tartalmazza.
author: ChrisGarty
manager: AnnBe
ms.date: 06/19/2019
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
ms.openlocfilehash: 14aa9b56da005e8e3ca121589d0e22c60f34343b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189775"
---
# <a name="workflow-faq"></a>Munkafolyamat GYIK

[!include [banner](../includes/banner.md)]

Ez a témakör a munkafolyamat-rendszerrel kapcsolatos gyakori kérdéseket tartalmazza.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Miért érkeznik a több értesítés egy munkaelem elutasítása esetén?
Egy munkaelem elutasításakor, a munkatétel elutasítottként lesz befejezve. Egy másik munkatétel lesz létrehozva és kiosztva a létrehozónak. Ez azt jelenti, hogy van egy értesítés az elutasított munka létrehozójának, és egy külön értesítés az új „módosítás kérése” munkaelemhez hozzárendelt felhasználónak. 

Minden értesítés egy másik meunelemhez tartozik, de a hasonlóság megtévesztő lehet. Tervezzük ennek fejlesztését egy későbbi kiadásban.

## <a name="why-are-my-workflow-exports-failing"></a>Miért nem sikerülnek a munkafolyamat-exportálásaim?
A munkafolyamat-exportálási funkcióra jelenleg korlátozás vonatkozik, amely megakadályozza, hogy a munkafolyamatok nevei túllépjék a 48 karaktert. Ha egy 48 karakternél hosszabb nevet használ, a „Kiszolgáló nem tudta hitelesíteni a kérelmet” hibát kap és/vagy nem lehetséges a fájlok fájltípus nélküli exportálása. A következő blogbejegyzés további részleteket nyújt: [Munkafolyamat exportálása](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>A munkafolyamat elküldője is jóváhagyhatja a munkafolyamatot?
Igen, ha így van beállítva, akkor a munkafolyamat elküldője is jóváhagyhatja a munkafolyamatot. Ennek a viselkedésnek a megelőzése érdekében adja meg a **Munkafolyamat-paraméterek > Általános > Jóváhagyó > Beküldő általi jóváhagyás tiltása** beállításhoz az **Igen** értéket.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Hozzáadhatok olyan figyelmeztetéseket a munkafolyamatokhoz, amelyek értesítik a felhasználókat?
Az alábbiakban az értesítésre szolgáló figyelmeztetések munkafolyamatokhoz való hozzáadásáról olvashat néhány alapvető részletet:
- A figyelmeztetések és a munkafolyamat-értesítési mechanizmusok összehasonlítása
    - A figyelmeztetések beállíthatók a rekordok változásaihoz. A munkafolyamatok során módosulnak a rekordok, így beállítható a rekord munkafolyamat által okozott módosításával kapcsolatos figyelmeztetés. Mivel azonban a munkafolyamatok eltérő értesítési beállításokat használnak, a figyelmeztetések használata nem a legjobb megoldás.
- A munkafolyamatok normál értesítései 
    - A munkafolyamatok rendelkeznek beépített e-mail-értesítésekkel. A vevő beállíthatja, hogy a felhasználók e-mailben kapjanak értesítéseket. Az ilyen értesítések esetében a felhasználók nem kapnak üzenetet a Műveleti központból.
    - Egy jövőbeli frissítésben bevezetjük a Műveleti központ üzenetét, így a felhasználóhoz egy munkafolyamat munkatételét lehet hozzárendelni. 
- Értesítések hozzáadása a munkafolyamatokhoz
    - A Műveleti központ üzeneteivel adott felhasználók is megcélozhatók, például az X++ munkafolyamatból létrehozott üzenetekkel.
    - [Üzleti események munkafolyamatai](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow), amelyekkel a vevő a kívánt értesítést használható folyamatokat aktiválhatja.   

Ha a felhasználó nem a megfelelő értesítést kapja a Műveleti központból, amikor hozzárendelik a munkafolyamat egyik munkatételét, a [Munkafolyamat üzleti eseményeinek](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) Microsoft Flow szolgáltatással való használatával további vagy más értesítések válhatnak elérhetővé.
