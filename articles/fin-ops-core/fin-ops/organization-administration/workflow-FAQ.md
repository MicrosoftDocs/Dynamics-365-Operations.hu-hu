---
title: Munkafolyamat GYIK
description: Ez a cikk megválaszolja a munkafolyamat-rendszerrel kapcsolatos gyakori kérdéseket.
author: ChrisGarty
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a72fd141bb1178a3a83385c512d1a655064d5b00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896579"
---
# <a name="workflow-faq"></a>Munkafolyamat GYIK

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Ez a cikk megválaszolja a munkafolyamat-rendszerrel kapcsolatos gyakori kérdéseket.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Miért érkeznik a több értesítés egy munkaelem elutasítása esetén?
Egy munkaelem elutasításakor, a munkatétel elutasítottként lesz befejezve. Egy másik munkatétel lesz létrehozva és kiosztva a létrehozónak. Ez azt jelenti, hogy van egy értesítés az elutasított munka létrehozójának, és egy külön értesítés az új „módosítás kérése” munkaelemhez hozzárendelt felhasználónak. 

Minden értesítés egy másik meunelemhez tartozik, de a hasonlóság megtévesztő lehet. Tervezzük ennek fejlesztését egy későbbi kiadásban.

## <a name="why-are-my-workflow-exports-failing"></a>Miért nem sikerülnek a munkafolyamat-exportálásaim?
A munkafolyamat-exportálási funkcióra jelenleg korlátozás vonatkozik, amely megakadályozza, hogy a munkafolyamatok nevei túllépjék a 48 karaktert. Ha egy 48 karakternél hosszabb nevet használ, a „Kiszolgáló nem tudta hitelesíteni a kérelmet” hibát kap és/vagy nem lehetséges a fájlok fájltípus nélküli exportálása. A következő blogbejegyzés további részleteket nyújt: [Munkafolyamat exportálásának hibaelhárítása](https://community.dynamics.com/365/financeandoperations/b/elandaxdynamicsaxupgradesanddevelopment/posts/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>A munkafolyamat elküldője is jóváhagyhatja a munkafolyamatot?
Igen, ha így van beállítva, akkor a munkafolyamat elküldője is jóváhagyhatja a munkafolyamatot. Ennek a viselkedésnek a megelőzése érdekében adja meg a **Rendszerfelügyelet > Munkafolyamat >Munkafolyamat-paraméterek > Általános > Jóváhagyó > Beküldő általi jóváhagyás tiltása** beállításhoz az **Igen** értéket.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Hozzáadhatok olyan figyelmeztetéseket a munkafolyamatokhoz, amelyek értesítik a felhasználókat?
Az alábbiakban az értesítésre szolgáló figyelmeztetések munkafolyamatokhoz való hozzáadásáról olvashat néhány alapvető részletet:
- A figyelmeztetések és a munkafolyamat-értesítési mechanizmusok összehasonlítása
    - A figyelmeztetések beállíthatók a rekordok változásaihoz. A munkafolyamatok során módosulnak a rekordok, így beállítható a rekord munkafolyamat által okozott módosításával kapcsolatos figyelmeztetés. Mivel azonban a munkafolyamatok eltérő értesítési beállításokat használnak, a figyelmeztetések használata nem a legjobb megoldás.
- A munkafolyamatok normál értesítései 
    - A munkafolyamatok rendelkeznek beépített e-mail-értesítésekkel. A vevő beállíthatja, hogy a felhasználók e-mailben kapjanak értesítéseket. Az ilyen értesítések esetében a felhasználók nem kapnak üzenetet a Műveleti központból.
    - Egy jövőbeli frissítésben bevezetjük a Műveleti központ üzenetét, így a felhasználóhoz egy munkafolyamat munkatételét lehet hozzárendelni. 
- Értesítések hozzáadása a munkafolyamatokhoz
    - A Műveleti központ üzeneteivel adott felhasználók is megcélozhatók, például az X++ munkafolyamatból létrehozott üzenetekkel.
    - [A munkafolyamatok üzleti eseményekkel rendelkeznek](../../dev-itpro/business-events/business-events-workflow.md), amelyekkel a vevő a kívánt értesítést használható folyamatokat aktiválhatja.   

Ha a felhasználó nem a megfelelő értesítést kapja a Műveleti központból, amikor hozzárendelik a munkafolyamat egyik munkatételét, a [Munkafolyamat üzleti eseményeinek](../../dev-itpro/business-events/business-events-workflow.md) Microsoft Power Automate szolgáltatással való használatával további vagy más értesítések válhatnak elérhetővé.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>Miért nem lehet elindítani a munkafolyamat-szerkesztőt az AD FS alatt?
Ha az Active Directory összevonási szolgáltatások (AD FS) alatt egy frissített környezetben fut, előfordulhat, hogy a munkafolyamat-szerkesztő nem működik megfelelően. Ha igen, győződjön meg arról, hogy a „https://dynamicsaxworkfloweditor/” URL hozzá van adva a **Microsoft Dynamics 365 for Operations Helyszíni - Munkafolyamat - Natív alkalmazás** tulajdonsághoz az ADFS beállításaiban.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>Miért kapok SQL kizárásokat a munkafolyamatok feldolgozásakor? 
A **Munkafolyamat-elemek száma kötegenként** értéke a **Munkafolyamat paraméterei** lapon 0. A 0 érték hatására az alapértelmezett érték 20 cikkre változik egy kötegben. Legyen körültekintő ennek az értéknek a módosítása során, mivel a sok cikkel rendelkező kötegek (> 40) SQL kizáráshoz vezethet.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>Mi a munkafolyamat kibővített hiba funkció?
A 10.0.13 verzió munkafolyamat kibővített hiba szolgáltatása hibakódokat ad hozzá a különböző munkafolyamat-hibák megkülönböztetéséhez. A jelentett hibaüzenetek többnyire hasonlóak kisebb eltérésekkel az egyértelműség kedvéért.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
