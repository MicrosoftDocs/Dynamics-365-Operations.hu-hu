---
title: Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban
description: Ez a témakör azt mutatja be, hogyan lehet leképezni az üzleteket és a megfelelő csapatokat a Dynamics 365 Commerce központi felületén, ha a szervezet már létrehozott csapatokat a Microsoft Teams alkalmazásban a Commerce-integráció előtt.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3edd176788b24a5f5246e9b7bcb3c6fbcdca2254
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842676"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Üzletek és csapatok leképezése, ha már vannak csapatok a Microsoft Teams alkalmazásban

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet leképezni az üzleteket és a megfelelő csapatokat a Dynamics 365 Commerce központi felületén, ha a szervezet már létrehozott csapatokat a Microsoft Teams alkalmazásban a Commerce-integráció előtt.

Előfordulhat, hogy a szervezet a Dynamics 365 Commerce és a Microsoft Teams integrációja előtt csapatokat hoz létre az összes üzlet egy részére vagy mindegyikére. Ebben az esetben a feladatszinkronizálás létrehozásához a Commerce POS és a Microsoft Teams között, és meg kell adnia az üzletek és a megfelelő csapat hozzárendelését a Commerce központi felületén.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Üzletek és a megfelelő csapatok leképezése a Commerce központi felületén 

Üzletek és a megfelelő csapatok leképezéséhez a Commerce központi felületén hajtsa végre az alábbi lépéseket.

1. Lépjen a **Rendszerfelügyelet \> Munkaterület \> Adatkezelés** elemre.
1. Válassza az **Exportálás** lehetőséget. 
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Csoport neve** alatt írja be a „Teams-leképezés exportálása” kifejezést.
1. A **Kiválasztott entitások** gyorslapon válassza az **Entitás hozzáadása** elemet. Megjelenik az **Entitás hozzáadása** párbeszédpanel.  
1. Az **Entitás neve** legördülő listában válassza a **Teams-leképezés a forrás és a csapat között** lehetőséget.
1. A **Cél adatformátum** legördülő listában válassza a **CSV** lehetőséget.
1. Válassza ki a **Hozzáadás**, majd a **Bezárás** lehetőséget.
1. A Művelet panel alatt bal felső sarokban válassza az **Exportálás most** lehetőséget.
1. A **Entitásfeldolgozás állapota** alatt válassza a **Fájl letöltése** lehetőséget.
1. Az exportált CSV-fájlban adja meg a **SOURCETYPE**, **SOURCEID** és **TEAMID** értékeket az alábbiak szerint:
    - A **SOURCETYPE** esetében írja be a „RetailStore” kifejezést. 
    - A **SOURCEID** esetében írja be az üzlet számát (például „000135” a San Francisco-i üzlethez). Az üzletek számát a **Retail és Commerce \> Csatornák \> Üzlete** alatt találja.
    - A **TEAMID** esetében írja be a megfelelő csapatazonosítót a Microsoft Teams alkalmazásból (például „5f8bc92b-6aa8-451e-85d1-3949c01ddc6c”). A csapatazonosító adatait itt találja: [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Mentse a CSV-fájlt a helyi gépre.
1. Lépjen a **Rendszerfelügyelet \> Munkaterület \> Adatkezelés** elemre, majd válassza az **Importálás** lehetőséget.
1. A **Kiválasztott entitások** gyorslapon válassza a **Fájl hozzáadása** elemet. Megjelenik a **Fájl hozzáadása** párbeszédpanel.
1. Az **Entitás neve** legördülő listában válassza a **Teams-leképezés a forrás és a csapat között** lehetőséget.
1. A **Forrás adatformátum** legördülő listában válassza a **CSV** lehetőséget.
1. Válassza a **Feltöltés és hozzáadás** lehetőséget, válassza ki a korábban mentett CSV-fájl, majd a **Megnyitás** lehetőséget.
1. A **Fájl hozzáadása** párbeszédpanelen válassza a **Bezárás** elemet.
1. Válassza a Művelet panel **Mentés** elemét, majd válassza az **Importálás** elemet.

A következő példakép az megjeleníti a Commerce rendszer **Csoportleképezések exportálása** csoportját az **Entitás hozzáadása** elemeket és az exportált CSV-fájlfejléceket kiemelve.

![A Commerce rendszer Csoportleképezések exportálása csoportja az entitás hozzáadása elemekkel és az exportált CSV-fájlfejlécekkel kiemelve](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> Az előzetes lépések befejezése után hajtsa végre a [Feladatkezelés szinkronizálása a Microsoft Teams és a pénztár között](synchronize-tasks-teams-pos.md) lépést a feladatkezelés szinkronizálása érdekében. 

## <a name="additional-resources"></a>További erőforrások

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának áttekintése](commerce-teams-integration.md)

[A Dynamics 365 Commerce és a Microsoft Teams integrációjának engedélyezése](enable-teams-integration.md)

[Microsoft Teams kiépítése a Dynamics 365 Commerce rendszerből](provision-teams-from-commerce.md)

[Feladatkezelés szinkronizálása a Microsoft Teams és a Dynamics 365 Commerce-pénztár között](synchronize-tasks-teams-pos.md)

[Felhasználói szerepkörök kezelése a Microsoft Teams alkalmazásban](manage-user-roles-teams.md)

[Dynamics 365 Commerce és Microsoft Teams integrációja – GYIK](teams-integration-faq.md)
