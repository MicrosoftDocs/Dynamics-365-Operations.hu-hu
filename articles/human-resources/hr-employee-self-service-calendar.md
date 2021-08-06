---
title: Csapatnaptár létrehozása
description: A csapatnaptárak megtekintése és létrehozása a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 52ae36f499871087cc086bcaf8c345af41d06943
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639390"
---
# <a name="view-team-and-company-calendars"></a>Csoportos és vállalati naptárak megtekintése

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

1. Válassza ki az **Alkalmazotti önkiszolgáló szolgáltatás** munkaterületén a **Távollétkezelő**, majd a **Távollétkezelő naptára** lehetőséget.

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

A szabadság és távollét paraméterben megadott naptárkonfiguráció határozza meg a rendelkezésre álló nézetbeállításokat.

A naptárak a felettes vagy a részleg alapján is szűrhetők. Az elsődleges beosztás-hozzárendelés határozza meg, hogy milyen alkalmazottak jelennek meg a szűrők beállításakor. 

> [!IMPORTANT]
> A **Vállalatközi szabadságnézet** funkciót a Funkciókezelésben kapcsolhatja be. Ezután engedélyeznie kell a funkciót a **Human Resources megosztott paraméterei** oldalon, hogy megjelenítse a jogi személy szűrőt a naptárakban. További tájékoztatás: [Szabadság és távolléti paraméterek konfigurálása](hr-leave-and-absence-parameters.md).
> 
> A naptárat jogi személy szerint szűrheti. Az összes alkalmazott megtekintéséhez jogi személytől függetlenül szeretné látni, törölje a jelet a szűrőmezőből, és nyomja meg az **Enter** billentyűt. 

A naptár beállításaival kapcsolatos további tudnivalókat lásd: [Naptárparaméterek konfigurálása](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
