---
title: Új felhasználók létrehozása
description: A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.
author: peakerbl
manager: AnnBe
ms.date: 06/08/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6f861b7493d039b332358be7df7d0198cbadcb7a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679840"
---
# <a name="create-new-users"></a>Új felhasználók létrehozása

[!include [banner](../../includes/banner.md)]

A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.

## <a name="associate-a-user-with-a-license-new-license-types-only"></a>Felhasználó társítása licenchez (csak az új licenctípusok esetében)
Azoknak a vevőknek, akik a 2019 októberében hozzáadott új licenccel rendelkeznek, a felhasználókat társítaniuk kell egy licenchez. A licenchez társított felhasználók automatikusan olyan rendszerfelhasználóként jelennek meg, akiknek nincs szerepkörük az első bejelentkezés alkalmával.

A rendszeradminisztrátorok [rendelhetnek hozzá licenceket a felhasználókhoz](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) a [Microsoft 365 felügyeleti központban](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a>Külső felhasználó társítása licenchez (csak az új licenctípusok esetében)
A bérlő környezetének külső felhasználóit fel kell tüntetni a gazdabérlő címtárában (Azure Active Directory (Azure AD)), hogy hozzájuk lehessen rendelni a licenceket. Ezeket a külső felhasználókat hozzá kell adni a bérlőhöz az Azure AD felületen vendég felhasználóként, majd hozzájuk rendelni a megfelelő licenceket. További tájékoztatás: [Azure Active Directory B2B együttműködő felhasználók hozzáadása az Azure Portal webhelyen](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

## <a name="add-a-new-user"></a>Új felhasználó hozzáadása
1. Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Felhasználói azonosító** mezőbe írja be a felhasználó egyedi azonosítóját. A felhasználó azonosítóját kötelező megadni.  
4. Írja be a felhasználó nevét a **Felhasználónév** mezőbe.  
5. A **Tartomány** mezőben adja meg a felhasználó tartományát.  
6. Az **Alias** mezőbe írja be a felhasználó aliasát.  
7. A **Vállalat** mezőben válassza ki a vállalatot. 
8. A **Felhasználó szerepkörei** gyorslapon válassza a **Szerepkörök társítása** lehetőséget a felhasználók biztonsági szerepkörökhöz történő hozzárendeléshez. További információ [Felhasználók hozzárendelése biztonsági szerepkörökhöz](assign-users-security-roles.md).
9. Válassza ki az **OK** lehetőséget.
10. Válassza a **Mentés** lehetőséget.

## <a name="import-users"></a>Felhasználók importálása
1. Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
2. A műveleti ablaktáblán válassza a **Felhasználók importálása** lehetőséget.
3. A listában jelölje meg a kiválasztott sort.
4. Válassza a **Felhasználók importálása** lehetőséget.
5. Válassza **Bezárás** lehetőséget.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]