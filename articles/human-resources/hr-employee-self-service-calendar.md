---
title: Csapatnaptár létrehozása
description: A csapatnaptárak megtekintése és létrehozása a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 07c7f1303238fe61d70be26ec5a198f1ac489090
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790764"
---
# <a name="view-team-and-company-calendars"></a>Csoportos és vállalati naptárak megtekintése

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Megtekintheti a csapat-és vállalati naptárakat a Dynamics 365 Human Resources alkalmazásban. A csapatnaptárak csak a sorhierarchiában meghatározott közvetlen jelentéseket jelenítik meg.

## <a name="view-your-team-calendar-as-an-employee"></a>A csoportja naptárának megtekintése alkalmazottként

1. Az **Alkalmazotti önkiszolgáló** munkaterületen válassza az **Összegzés** alatt található **Csoport távolléti naptár** lehetőséget.

## <a name="view-your-team-calendar-as-a-manager"></a>A csoportja naptárának megtekintése vezetőként

1. Az **Alkalmazotti önkiszolgáló rendszer** munkaterületen válassza a **Saját csapat** lehetőséget.

2. Válassza a **Szabadság és távollét** lehetőséget, majd válassza a **Vezetői távolléti naptár megtekintése** lehetőséget.

A vezetők a csoport naptárát a **Saját csapathoz tartozó szabadságkérelmek**, **Jóváhagyott szabadságkérelmek** és a **Táűvolléti kérelmek** helyekről tekinthetik meg. 

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

>[!IMPORTANT]
>A szabadság és a távollét megtekintése a vállalatok között jelenleg előzetes verzióban érhető el. Engedélyeznie kell azt a **Tesztkörnyezetében**. Az előzetes funkciók engedélyezésével kapcsolatos további részletekért tekintse meg a [Kezelési funkciók](hr-admin-manage-features.md) cikket.<br><br>
>Ezután engedélyeznie kell a funkciót a **Human Resources megosztott paramétereiben**, hogy megjelenítse a jogi személy szűrőt a naptárakban. További tájékoztatás: [Szabadság és távolléti paraméterek konfigurálása](hr-leave-and-absence-parameters.md).<br><br>
>A naptárat jogi személy szerint szűrheti. Ha az összes alkalmazottat jogi személytől függetlenül szeretné látni, törölje a jelet a szűrőmezőből, és válassza az entert. 

A naptár beállításaival kapcsolatos további tudnivalókat lásd: [Naptárparaméterek konfigurálása](hr-leave-and-absence-parameters.md?configure-calendar-parameters).



[!INCLUDE[footer-include](../includes/footer-banner.md)]