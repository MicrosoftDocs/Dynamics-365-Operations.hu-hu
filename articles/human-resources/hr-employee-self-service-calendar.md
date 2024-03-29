---
title: Csapatnaptár létrehozása
description: A csapatnaptárak megtekintése és létrehozása a Dynamics 365 Human Resources alkalmazásban.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6dffcb265030922e5134cfab1310027be43d87ea
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904159"
---
# <a name="view-team-and-company-calendars"></a>Csapat és vállalati naptárak megtekintése

>[!Important]
>Az ebben a cikkben említett funkciók jelenleg önálló vevők számára érhetők el Dynamics 365 Human Resources. A funkciók egy része vagy egésze a Finance infrastruktúra jövőbeni kiadásának részeként lesz elérhető a Finance 10.0.26-ös kiadása után.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Megtekintheti a csapat-és vállalati naptárakat a Dynamics 365 Human Resources alkalmazásban. A csapatnaptárak csak a sorhierarchiában meghatározott közvetlen jelentéseket jelenítik meg.

## <a name="view-your-team-calendar-as-an-employee"></a>A csoportja naptárának megtekintése alkalmazottként

- Az **Alkalmazotti önkiszolgáló** munkaterületen válassza az **Összegzés** alatt található **Csoport távolléti naptár** lehetőséget.

## <a name="view-your-team-calendar-as-a-manager"></a>A csoportja naptárának megtekintése vezetőként

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Saját csapat** lehetőséget.

2. Válassza a **Szabadság és távollét** lehetőséget, majd válassza a **Vezetői távolléti naptár megtekintése** lehetőséget.

A vezetők a csoport naptárát a **Saját csapathoz tartozó szabadságkérelmek**, **Jóváhagyott szabadságkérelmek** és a **Táűvolléti kérelmek** helyekről tekinthetik meg. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>Távollétkezelő naptárának megtekintése távollétkezelőként

> [!NOTE]
> A távollétkezelő naptár megtekintéséhez először be kell kapcsolnia az **(Előzetes verzió) A távollétkezelő kezeli a szabadásgokat** funkciót a funkciókezelésben. Az előzetes funkciók bekapcsolásával kapcsolatos további információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben.

A Távollétkezelő szerepkörű felhasználók a naptárban megtekinthetik az szabadságkérelmeket. A szabadságnaptár eléréséhez kövesse az alábbi lépéseket.

1. Az **Alkalmazotti önkiszolgáló** munkaterületen válassza a **Szabadságkezelés**, majd a **Távollétkezelő naptár** menüpontot.

2. Adja meg a kívánt dátumokat a **Dátum** mezőben.

3. Szükség szerint frissítse a nézetbeállításokat.

A távollétkezelő naptára mutatja az összes olyan alkalmazott rekordját, aki a Távolléti hierarchiában a távollétkezelő alá tartoznak.

## <a name="view-a-company-calendar"></a>Vállalati naptár megtekintése

Az emberi erőforrás szerepkörrel rendelkező személyek megtekinthetik a vállalati naptárakat. A vállalati naptárak minden alkalmazottat megjelenítenek. Alapértelmezés szerint a naptár a mai dátumot és 28 napot jeleníti meg, de a dátumtartományt módosítani lehet. A naptárt **Név**, **Személyzeti szám** és **Szabadság típusa** alapján is szűrheti.

1. A **Szabadság és távollét** munkaterületen válassza a **Hivatkozások** lehetőséget.

2. Válassza a **Szabadság- és távolléti naptár** lehetőséget.

A humánerőforrás-szerepkörök a vállalat naptárát a **Szabadság- és távolléti kérelmek**, **Jóváhagyott szabadság** és **Szabadságkérelmek** helyekről is elérhetik. 

A naptárak most további szűrőket és beállításokat tartalmaznak. Az összes naptárban tartalmaz nézetbeállításokat a következőkhöz:

- Jóváhagyott kérelmek
- Függőben lévő kérelmek
- Távolléti kérelmekkel rendelkező alkalmazottak
- Távolléti kérelmekkel nem rendelkező alkalmazottak
- Alkalmazottak születésnapjai
- Szabadságkérelmek 
- Távollétkérelmek

A **Szabadság és távollét paraméter** oldalon megadott naptárkonfiguráció határozza meg a rendelkezésre álló nézetbeállításokat.

A naptárak a felettes vagy a részleg alapján is szűrhetők. Az elsődleges beosztás-hozzárendelés határozza meg, hogy milyen alkalmazottak jelennek meg a szűrők beállításakor. 

> [!IMPORTANT]
> A **Vállalatközi szabadságnézet** funkciót a Funkciókezelésben kapcsolhatja be. Ezután engedélyeznie kell a funkciót a **Human Resources megosztott paraméterei** oldalon, hogy megjelenítse a jogi személy szűrőt a naptárakban. További tájékoztatás: [Szabadság és távolléti paraméterek konfigurálása](hr-leave-and-absence-parameters.md).
> 
> A naptárat jogi személy szerint szűrheti. Az összes alkalmazott megtekintéséhez jogi személytől függetlenül szeretné látni, törölje a jelet a szűrőmezőből, és nyomja meg az **Enter** billentyűt. 

A naptár beállításaival kapcsolatos további tudnivalókat lásd: [Naptárparaméterek konfigurálása](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
