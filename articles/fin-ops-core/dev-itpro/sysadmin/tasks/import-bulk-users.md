---
title: Felhasználók importálása az Azure Active Directory-szolgáltatásból
description: Ezzel az eljárással a rendszergazdák manuálisan importálhatnak felhasználókat nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c2600ad8f441e6b73b143c27afa08ad0a5c2748
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5571005"
---
# <a name="import-users-from-azure-active-directory"></a>Felhasználók importálása az Azure Active Directory-szolgáltatásból

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>Kiválasztott felhasználók importálása

Ezzel az eljárással a rendszergazdák kiválasztott felhasználókat importáljanak az Azure Active Directory (Azure AD) rendszerből.

1. A rendszer az aktuális munkamenet vállalatát importálja alapértelmezett vállalatként. A felhasználók importálása előtt módosítsa az aktuális vállalatot, ha az szükséges.
2. Ugrás a **Rendszerfelügyelet > Felhasználók > Felhasználók** elemre.
3. Kattintson a **Felhasználók importálása** elemre.
4. Jelölje ki az importálandó felhasználókat, és válassza a **Felhasználók importálása** lehetőséget.

Az importálás befejezése után szerepköröket kell hozzárendelni a felhasználókhoz.

## <a name="import-users-in-bulk"></a>Felhasználók tömeges importálása

Ezzel az eljárással a rendszergazdák nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.
Ne feledje, hogy a Kötegelt importálás beállítás használatakor nem lehet felhasználókat kijelölni.

## <a name="run-the-import-as-a-batch-job"></a>Az importálás futtatása kötegelt feladatként
1. A rendszer az aktuális munkamenet vállalatát importálja alapértelmezett vállalatként. A felhasználók importálása előtt módosítsa az aktuális vállalatot, ha az szükséges.
2. Ugrás a **Rendszerfelügyelet > Felhasználók > Felhasználók** elemre.
3. Kattintson a **Kötegelt importálás** lehetőségre.
4. Bontsa ki a **Futtatás a háttérben** szakaszt.
4. Válassza az **Igen** lehetőséget a **Kötegelt feldolgozás** mezőben.
6. A **Kötegcsoport** mezőben adjon meg vagy válasszon ki egy értéket. Ez a lépés nem kötelező.  
7. Válassza ki az **Igen** lehetőséget a **Személyes** mezőben. Ez a lépés nem kötelező.  
8. Válassza az **Igen** lehetőséget a **Kritikus feladat** mezőben. Ez a lépés nem kötelező.  
9. Válasszon ki egy lehetőséget a **Figyelési kategória** mezőben.
10. Kattintson az **OK** gombra.

Az importálás befejezése után szerepköröket kell hozzárendelni a felhasználókhoz.

## <a name="run-in-a-sandbox-environment"></a>Futtatás védőfalkörnyezetben
1. Válassza a **Kötegelt importálás** lehetőséget.
2. Válassza ki az **OK** lehetőséget.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]