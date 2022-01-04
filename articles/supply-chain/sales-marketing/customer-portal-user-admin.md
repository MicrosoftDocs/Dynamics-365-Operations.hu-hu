---
title: Vevői portál felhasználóinak létrehozása és kezelése (videofelvételt tartalmaz)
description: Ez a témakör azt mutatja be, hogyan kell létrehozni az Ügyfélportál felhasználói fiókjait, és hogyan állíthatja be a rájuk vonatkozó engedélyeket.
author: Henrikan
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 20751a25a6dedb04806068780bc2f4e381bf79bc
ms.sourcegitcommit: ef0dd4245fc499907ffe00e2a32f59a6cd96e45d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/18/2021
ms.locfileid: "7937453"
---
# <a name="create-and-manage-customer-portal-users"></a>Ügyfélportál felhasználóinak létrehozása és kezelése

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

A „gyári” implementációban nincs mód arra, hogy a felhasználók önállóan regisztrálhatják magukat a Ügyfélportál segítségével létrehozott webhelyeken. A bejelentkezéshez és a webhely használatához a felhasználókat az adminisztrátornak kell meghívnia. A Microsoft szándékosan zárolta a lehetőséget, hogy a felhasználók önállóan regisztrálhatják magukat.

Ahhoz, hogy a felhasználó használhassa a webhelyet, létre kell hozni egy kapcsolattartó-rekordot a felhasználó számára. Ez a rekord jelzi, hogy melyik ügyfélfiókhoz és jogi személyhez tartozik a felhasználó. Ezek az adatok elengedhetetlenek ahhoz, hogy a felhasználó létrehozhasson és megtekinthessen értékesítési rendeléseket.

Amikor a felhasználók magukat regisztrálják, a kapcsolattartói rekordok automatikusan jönnek létre hozzájuk. Ennélfogva nem lehet biztosítani, hogy a felhasználó a megfelelő ügyfélfiókot és jogi személyt válassza ki. Másrészről a meghívó folyamat lehetővé teszi, hogy egy rendszergazda a megfelelő ügyfélfiókot és jogi személyt rendelje hozzá a kapcsolattartói rekordhoz a meghívó kiküldése előtt. Ha úgy gondolja, hogy testreszabja a megoldást, hogy a felhasználók önállóan regisztrálhatják magukat,mindenképpen vegye figyelembe vegye a lehetséges következményeket.

## <a name="video"></a>Videó
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

A [Hívja meg a vevőket, hogy regisztráljanak és használják a portált](https://youtu.be/drGUYHX9QIQ) című videó (fent) szerepel a [Finance and Operations lejátszási listán,](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) amely elérhető a YouTube felületén.

## <a name="prerequisite-setup"></a>A beállítás előfeltételei

A Power Apps portálokon található kapcsolattartók rekordokként vannak tárolva a Microsoft Dataverse **Kapcsolattartók** táblában. A kettős írás ezt követően szükség szerint szinkronizálja ezeket a rekordokat a Microsoft Dynamics 365 Supply Chain Management alkalmazásba.

![A Ügyfélportál kapcsolattartóinak rendszerdiagramja.](media/customer-portal-contacts.png "A Ügyfélportál kapcsolattartóinak rendszerdiagramja")

Új vevők meghívásának megkezdése előtt győződjön meg arról, hogy a **Kapcsolattartó** táblák megfeleltetése engedélyezve van a kettős írásban.

## <a name="the-invitation-process"></a>A meghívás folyamata

Ha meg szeretne hívni egy meglévő kapcsolattartót a Ügyfélportálra webhelyére, kövesse a [Kapcsolattartók meghívása a portáljára](/powerapps/maker/portals/configure/invite-contacts) rész lépéseit a Power Apps portálok dokumentációjában.

Mielőtt meghívja a vevőt, hogy csatlakozzon a Ügyfélportálra győződjön meg arról, hogy a vevő [kapcsolattartói rekordja](/powerapps/maker/portals/configure/configure-contacts) elérhető, és be van állítva a következő módon:

1. Állítsa be a **Vállalat** mezőt arra a jogi személyre, amelyhez az ügyfelet hozzá szeretné rendelni a Supply Chain Management alkalmazásban.
2. Állítsa be a **Számlaszám** mezőt arra a számlaszámra amelyhez az ügyfelet hozzá szeretné rendelni a Supply Chain Management alkalmazásban.

Miután létrehozta a kapcsolattartót az látható lesz a Supply Chain Management modulban.

A további tudnivalókat lásd: [A portálon használható kapcsolattartó konfigurálása](/powerapps/maker/portals/configure/configure-contacts) részt a Power Apps portálok dokumentációjában.

## <a name="out-of-box-web-roles-and-table-permissions"></a>Gyári webes szerepkörök és táblaengedélyek

A Power Apps portálok felhasználói szerepköreit a [webes szerepkörök](/powerapps/maker/portals/configure/create-web-roles) és az [táblaengedélyek](/powerapps/maker/portals/configure/assign-entity-permissions) határozzák meg. A Ügyfélportál néhány szerepkört kínál már gyári állapotban is. Új szerepköröket hozhat létre, és módosíthatja vagy törölheti a meglévő szerepköröket.

### <a name="out-of-box-web-roles"></a>Gyári webes szerepkörök

Ez a szakasz a Ügyfélportál szolgáltatással szállított webes szerepköröket írja le.

A gyári felhasználói szerepkörök módosításával kapcsolatos további tudnivalókat lásd: [Webes szerepkörök létrehozása a portálokhoz](/powerapps/maker/portals/configure/create-web-roles) és [Rekordalapú biztonság hozzáadása táblaengedélyek használatával a portálokhoz](/powerapps/maker/portals/configure/assign-entity-permissions) a Power Apps dokumentációjában.

#### <a name="administrator"></a>Rendszergazda

A rendszergazda felügyeli és tartja karban a webhelyet. Ez a személy építi ki és állítja be az Ügyfélportált. A rendszergazda karbantartja a portált informatikai és biztonsági szempontokból, és gondoskodik arról, hogy minden simán fusson. Előfordulhat, hogy a rendszergazda testreszabhatja és/vagy módosíthatja a portált új funkciók hozzáadásával, új szerepkörök létrehozásával stb.

#### <a name="customer-representative"></a>Ügyfél képviselője

Az ügyfél képviselője dolgozik egy ügyfélvállalatnál dolgozik, és ő felelős a vállalat által leadott megrendelések kezeléséért. Az ügyfél képviselője a látja vállalathoz tartozó összes rendelést, valamint azokat a felhasználókat, akik leadták azokat. Ezenkívül az ügyfél képviselője információkat jeleníthet meg a teljes partnerről, és azt, hogy mely kapcsolattartók adhatnak le rendeléseket az adott partner nevében.

#### <a name="authorized-users"></a>Jogosult felhasználók

A felhatalmazott felhasználók leadhatnak a rendeléseket, és megtekinthetik az általuk leadott rendelések állapotát. Azonban nem tudják megtekinteni azoknak a rendeléseknek az állapotát, amelyek a vállalatuk más felhasználói adtak le.

#### <a name="unauthorized-users"></a>Nem felhatalmazott felhasználók

A nem felhatalmazott felhasználók nem tekinthetnek meg adatokat. Csak a publikus információkat, például az üzletszabályzatot Ügyfélportált futtatott vállalat adatait láthatják.

#### <a name="example"></a>Példa

A következő táblázat bemutatja, hogy a rendszerben mely értékesítési rendeléseket láthatják az egyes webes szerepkörök.

| Értékesítési rendelés | Adminisztrátor | X&nbsp;ügyfél ügyfélképviselője | Jogosult felhasználó: Jane | Jogosult felhasználó: Sam | Nem felhatalmazott felhasználó: May |
|---|---|---|---|---|---|
| X&nbsp;ügyfél megrendelő:&nbsp;Jane | Igen | Igen | Igen | Nem | Nem |
| X&nbsp;ügyfél megrendelő:&nbsp;Sam | Igen | Igen | Nem | Igen | Nem |
| Y&nbsp;ügyfél Megrendelő:&nbsp;May | Igen | Nem | Nem | Nem | Nem |

> [!NOTE]
> Annak ellenére, hogy mind a Sam, mind a Jane olyan kapcsolattartó, aki az X ügyfélnek dolgozik, csak azokat a rendeléseket láthatja, amelyekhez ők maguk adtak le, és semmi mást. Annak ellenére, hogy Maynek van egy rendelése a rendszerben, az Ügyfélportálon nem láthatja ezt a rendelést mivel ő egy nem felhatalmazott felhasználó. (Ezenkívül a rendelést egy az Ügyfélportáltól eltérő csatornán adta le.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]