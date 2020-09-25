---
title: Szabadság vásárlására és eladására irányuló kérelem munkafolyamatának létrehozása
description: Hozzon létre egy szabadság vásárlására és eladására irányuló kérelem munkafolyamatot, a szabadságkérelmeket egységes vételéhez és eladásához a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d490e0c36ea0e854c5d7afc5b3bf75f6b65e542c
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712598"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Szabadság vásárlására és eladására irányuló kérelem munkafolyamatának létrehozása

Létrehozhat egy munkafolyamatot a Dynamics 365 Human Resources alkalmazásban a szabadságkérelmek egységes vételéhez és eladásához. A **Szabadság vásárlása és eladása** munkafolyamat lehetővé teszi:

- Feladatok definiálását
- Annak meghatározását, hogy kinek kell végrehajtania a feladatokat
- Annak megadását, hogy ki hagyhatja jóvá vagy utasíthatja el a kérelmeket

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>Szabadság vásárlására és eladására irányuló kérelem munkafolyamatának létrehozása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** alatt válassza az **Emberi erőforrás munkafolyamatok** lehetőséget.

3. Válassza az **Új** lehetőséget, majd válassza a **Szabadságkérelem vásárlása és eladása** lehetőséget. 

4. Amikor megjelenik a **Megnyitja ezt a fájlt?** üzenetmező, vákasza a **Megnyitás** lehetőséget, és jelentkezzen be a vállalati hitelesítő adataival.

5. A munkafolyamat-szerkesztővel hozzon létre egy munkafolyamatot a szabadságkérelmekhez. További tájékoztatás a munkafolyamatok használatáról: [Munkafolyamatok létrehozása – áttekintés](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Szabadság- és távolléti kérelem munkafolyamatának adatelemei

A következő adatelemek segítségével feltételes vagy automatikus jóváhagyásokat hozhat létre a munkafolyamatokban a szabadság vásárlásával és eladásával kapcsolatos kérelmekhez:

- **Összeg**
- **Szabadság vásárlásával és eladásával kapcsolatos irányelv**
- **Cég**
- **Létrehozta**
- **Létrehozás dátuma és időpontja**
- **Befejezés**
- **Szabadság típusa**
- **Módosította:**
- **Módosítás dátuma és időpontja**
- **Kérelemazonosító**
- **Kezdés dátuma**
- **Állapot** 
- **Küldés dátuma**
- **Beküldte:**
- **Elküldve az Emberi erőforrások által**
- **Beküldve a vezető által**
- **Beküldve a következő nevében**
- **Dolgozó**

## <a name="workflow-examples"></a>Munkafolyamat-példák

Ezek a példák azt mutatják be, hogyan lehet különböző típusú munkafolyamat-feltételeket létrehozni a következő adatelemek segítségével:

- Az **Emberi erőforrások által elküldött** és a **Vezető által beküldött** elemek használata egy automatikus műveletben a szabadságkérelmek eladásának és vételének automatikus jóváhagyásához, amelyeket ezek a szerepkörök küldtek be a munkavállalók nevében. Az automatikus műveletekkel kapcsolatos további tudnivalókat lásd: [Jóváhagyási folyamatok konfigurálása munkafolyamatokban](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).

- A **Szabadságtípus** használata feltételes állításban vagy automatikus műveletben, annak meghatározásához, hogy a munkafolyamat hogyan irányítsa át az egyes szabadságtípusokat tartalmazó szabadságkérelmeket.

## <a name="see-also"></a>Lásd még

[Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)<br>
[Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
