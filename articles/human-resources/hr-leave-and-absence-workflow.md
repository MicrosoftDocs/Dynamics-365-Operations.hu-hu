---
title: Szabadságkérelem munkafolyamat létrehozása
description: Hozzon létre egy szabadság- és távollétkérelem munkafolyamatot, a szabadságkérelmeket egységes kezeléséhez a Dynamics 365 Human Resources alkalmazásban.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c8030e568ac8ef47d8383f09e06ce02a62947698
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728638"
---
# <a name="create-a-leave-request-workflow"></a>Szabadságkérelem munkafolyamat létrehozása

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Létrehozhat egy munkafolyamatot a Dynamics 365 Human Resources alkalmazásban a szabadságkérelmek egységes kezeléséhez. A **Szabadság és távollét** munkafolyamata lehetővé teszi:

- Feladatok definiálását
- Annak meghatározását, hogy kinek kell végrehajtania a feladatokat
- Annak megadását, hogy ki hagyhatja jóvá vagy utasíthatja el a kérelmeket

## <a name="create-a-leave-and-absence-request-workflow"></a>Szabadság- és távolléti kérelem munkafolyamat létrehozása

1. A **Szabadság és távollét** oldalon válassza a **Hivatkozások** lapot.

2. A **Beállítás** alatt válassza az **Emberi erőforrás munkafolyamatok** lehetőséget.

3. Válassza az **Új** lehetőséget, majd válassza a **Szabadság- és távollétkérelem** lehetőséget. 

4. Amikor megjelenik a **Megnyitja ezt a fájlt?** üzenetmező, vákasza a **Megnyitás** lehetőséget, és jelentkezzen be a vállalati hitelesítő adataival.

5. A munkafolyamat-szerkesztővel hozzon létre egy munkafolyamatot a szabadságkérelmekhez. További tájékoztatás a munkafolyamatok használatáról: [Munkafolyamatok létrehozása – áttekintés](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Szabadság- és távolléti kérelem munkafolyamatának adatelemei

A következő adatelemek segítségével feltételes vagy automatikus jóváhagyásokat hozhat létre a munkafolyamatokban a szabadság- és a távolléti kérelmekhez:

- **Összeg**
- **Megjegyzés**
- **Cég**
- **Létrehozta:**
- **Létrehozás dátuma és időpontja**
- **Befejezés**
- **Szabadság típusa**
- **Módosította:**
- **Módosítás dátuma és időpontja**
- **Okkód**
- **Kérelemazonosító**
- **Kezdés dátuma**
- **Állapot** 
- **Küldés dátuma**
- **Beküldte:**
- **Elküldve az Emberi erőforrások által**
- **Beküldve a vezető által**
- **Beküldve a következő nevében**
- **Dolgozó**
- **Dolgozó típusa**

Ezek a példák azt mutatják be, hogyan lehet különböző típusú munkafolyamat-feltételeket létrehozni a következő adatelemek segítségével:

- Az **Okkód** feltételes állításban történő használata a betegszabadság-kérelmek átirányításához a **Műtét** okkóddal a HR számára, míg az összes többi okkód átirányítása a vezetőhöz. A feltételes állításokkal kapcsolatos további tudnivalókat lásd: [Feltételes döntések konfigurálása egy munkafolyamatban](../fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow.md). 

- Az **Emberi erőforrások által elküldött** és a **Vezető által beküldött** elemek használata egy automatikus műveletben a szabadságkérelmek automatikus jóváhagyásához, amelyeket ezek a szerepkörök küldtek be a munkavállalók nevében. Az automatikus műveletekkel kapcsolatos további tudnivalókat lásd: [Jóváhagyási folyamatok konfigurálása munkafolyamatokban](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md).

- A **Szabadságtípus** használata feltételes állításban vagy automatikus műveletben, annak meghatározásához, hogy a munkafolyamat hogyan irányítsa át az egyes szabadságtípusokat tartalmazó szabadságkérelmeket.

## <a name="see-also"></a>Lásd még

- [Szabadság és távollét áttekintése](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
