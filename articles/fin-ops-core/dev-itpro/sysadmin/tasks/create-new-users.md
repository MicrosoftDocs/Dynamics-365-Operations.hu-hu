---
title: Új felhasználók létrehozása
description: A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.
author: maertenm
manager: AnnBe
ms.date: 10/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c347a34a389c32d005cc8086c4a1349ecb8a698
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570521"
---
# <a name="create-new-users"></a>Új felhasználók létrehozása

[!include [task guide banner](../../includes/task-guide-banner.md)]

A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Felhasználó társítása licenchez (csak az új licenctípusok esetében)
Azoknak a vevőknek, akik a 2019 októberében hozzáadott új licenccel rendelkeznek, a felhasználókat társítaniuk kell egy licenchez. A licenchez társított felhasználók automatikusan olyan rendszerfelhasználóként jelennek meg, akiknek nincs szerepkörük az első bejelentkezés alkalmával. A licenchez nem társított felhasználók figyelmeztető üzenetet kapnak.

A rendszeradminisztrátorok [rendelhetnek hozzá licenceket a felhasználókhoz](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) a [Microsoft 365 felügyeleti központban](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-a-new-user"></a>Új felhasználó hozzáadása
1. Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Felhasználói azonosító** mezőbe írja be a felhasználó egyedi azonosítóját. A felhasználó azonosítóját kötelező megadni.  
4. Írja be a felhasználó nevét a **Felhasználónév** mezőbe.  
5. A **Tartomány** mezőben adja meg a felhasználó tartományát.  
6. Az **Alias** mezőbe írja be a felhasználó aliasát.  
7. A **Vállalat** mezőben válassza ki a vállalatot. 
8. A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök társítása** lehetőséget a [felhasználók biztonsági szerepkörökhöz történő hozzárendeléshez](assign-users-security-roles.md).
9. Válassza ki az **OK** lehetőséget.
10. Válassza a **Mentés** lehetőséget.

## <a name="import-users"></a>Felhasználók importálása
1. A műveleti ablaktáblán válassza a **Felhasználók importálása** lehetőséget.
2. A listában jelölje meg a kiválasztott sort.
3. Válassza a **Felhasználók importálása** lehetőséget.
4. Válassza **Bezárás** lehetőséget.

