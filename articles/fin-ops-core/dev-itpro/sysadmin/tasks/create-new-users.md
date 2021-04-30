---
title: Új felhasználók létrehozása
description: A felhasználók a szervezet olyan belső alkalmazottai vagy külső vevői és szállítói, akiknek hozzáféréssel kell rendelkezniük a rendszerhez a munkájuk elvégzéséhez.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 88d3f1fba05d944e78e4595018d190c3dc41e076
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907911"
---
# <a name="create-new-users"></a>Új felhasználók létrehozása

[!include [banner](../../includes/banner.md)]

A Finance and Operations alkalmazások eléréséhez először hozzá kell adni Önt a **Felhasználók** laphoz (**Rendszerfelügyelet \> Felhasználók \> Felhasználók**). A felhasználók közé tartoznak a szervezet belső alkalmazottai, illetve a külső vevők és szállítók. A felhasználókat importálni lehet, vagy kézzel lehet hozzáadni. A megfelelő használathoz minden felhasználónak megfelelő licenccel kell rendelkeznie.

A Finance and Operations alkalmazások vásárlásával és licencelésével kapcsolatos tudnivalókért lásd: [Microsoft Dynamics 365 licencelési útmutató](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409).

## <a name="assign-a-license-to-a-user"></a>Licenc hozzárendelése egy felhasználóhoz
A rendszeradminisztrátorok [rendelhetnek hozzá licenceket a felhasználókhoz](/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) a [Microsoft 365 felügyeleti központban](/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Külső felhasználó hozzáadása az Azure AD megoldásban, és egy licenc hozzárendelése 
A külső felhasználóknak meg kell jelenniük a bérlőkönyvtárban (Azure Active Directory (Azure AD)), hogy licenceket kaphassanak. Ezeket a külső felhasználókat hozzá kell adni a bérlőhöz az Azure AD felületen vendég felhasználóként, majd hozzájuk rendelni a megfelelő licenceket. A Finance and Operations alkalmazásoktól az a követelmény, hogy a vendégfelhasználó vállalatának használnia kell az Azure AD megoldást. További tájékoztatás: [Azure Active Directory B2B együttműködő felhasználók hozzáadása az Azure Portal webhelyen](/azure/active-directory/b2b/add-users-administrator).

## <a name="import-new-users-from-azure-ad"></a>Új felhasználók importálása az Azure AD-szolgáltatásból 
1. Ugrás a **Rendszerfelügyelet** \> **Felhasználók** \> **Felhasználók** elemre.
2. A műveleti ablaktáblán válassza a **Felhasználók importálása** lehetőséget.
3. Válassza ki az importálni kívánt felhasználókat. A lista olyan Azure AD felhasználókat is tartalmaz, akik jelenleg nem felhasználók ebben a környezetben.
4. Válassza a **Felhasználók importálása** lehetőséget.
5. Válassza **Bezárás** lehetőséget.

> [!NOTE]
> A **Vállalat** mező értéke a rendszergazda aktuális munkamenet-vállalata alapján lesz beállítva. Az importálás után a szerepköröket és a szervezeteket megfelelően kell hozzárendelni. További információ [Felhasználók hozzárendelése biztonsági szerepkörökhöz](assign-users-security-roles.md). Feltételesen előfordulhat, hogy a felhasználót egy **Személyhez** kell társítani, és frissíteni kell a felhasználói beállításokat, például a nyelvet.

## <a name="manually-add-a-new-user"></a>Új felhasználó manuális hozzáadása
1. Ugrás a **Rendszerfelügyelet** \> **Felhasználók** \> **Felhasználók** elemre.
2. A Műveleti ablaktáblán kattintson az **Új** elemre.
3. A **Felhasználói azonosító** mezőbe írja be a felhasználó egyedi azonosítóját.   
4. Írja be a felhasználó nevét a **Felhasználónév** mezőbe.  
5. A **Szolgáltató** mezőben válassza:
 - Belső felhasználók esetén használja az alapértelmezett értéket. Például az Azure AD bérlője https://sts.windows.net/ előtaggal.  
 - Nem Azure AD felhasználók, például a Service-2-Service fiókok esetén adjon meg egy alapvető szöveges értéket. Példa: NA. Ez az érték segít elkerülni a helytelen hitelesítési hívásokat, amelyek hibát okozhatnak, ha érvényes azonosítószolgáltató értéket használ.  
 - Külső vagy vendég felhasználók esetén adja meg az Azure AD-bérlő nevét ezt követően: https://sts.windows.net/.
6. Az **E-mail** mezőbe írja be a felhasználó teljes E-mailjét/Felhasználó elsődleges nevét.  
7. A **Vállalat** mezőben válassza ki a felhasználó alapértelmezett indítási vállalatát. 
8. Válassza a **Mentés** lehetőséget.

A rendszer a felhasználói rekord mentésekor [Microsoft Graph](/graph/overview) hívás alapján frissíti az identitásszolgáltatót és a telemetriai azonosítót. A telemetriai azonosító a felhasználó alapja a felhasználó objektumazonosítója/biztonsági azonosítója az Azure AD megoldásban.

> [!NOTE]
> Miután hozzáadta a felhasználót, a szerepköröket és szervezeteket hozzá kell rendelnie a megfelelő módon. További információ [Felhasználók hozzárendelése biztonsági szerepkörökhöz](assign-users-security-roles.md). Feltételesen előfordulhat, hogy a felhasználót egy **Személyhez** kell társítani, és frissíteni kell a **Felhasználói beállításokat**, például a nyelvet.

## <a name="change-a-user-id"></a>Felhasználói azonosító módosítása
Felhasználói azonosító módosítása csak akkor változtathat meg, ha átnevezi a kulcsot az adatbázisban. Ha ezzel az eljárással módosít egy felhasználói azonosítót, minden kapcsolódó felhasználói beállítás módosul, hogy az új felhasználói azonosítót használja. A **SysLastValue** tábla használati adatai például frissülnek, hogy az új felhasználói azonosítóra hivatkozhassanak.

> [!NOTE]
> A felhasználói azonosító a felhasználói információs tábla elsődleges kulcsa. Az elsődleges kulcs átnevezése bizonyos időt vehet igénybe a meglévő felhasználók számára, mivel a kulcsra mutató összes hivatkozás is frissül az adatbázisban. 

1. Ugrás a **Rendszerfelügyelet \> Felhasználók \> Felhasználók** elemre.
2. Jelöljön ki egy felhasználót a listából, és válassza a **Beállítások\> Rekordinformáció** elemet.
3. Válassza az **Átnevezés** lehetőséget.
4. Adja meg a felhasználói azonosító új és egyedi nevét, majd válassza az **OK** lehetőséget. 
5. A megerősítéshez kattintson az **Igen** gombra.

## <a name="additional-resources"></a>További erőforrások

A B2B-felhasználók implementálásához a további beállításokat itt találja: [B2B-felhasználók exportálása az Azure AD megoldásba](../implement-b2b.md).

Az előre konfigurált rendszerfiókokkal kapcsolatos tudnivalókat lásd: [Előre konfigurált rendszerfiókok](../pre-configured-system-accounts.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]