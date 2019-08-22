---
title: Hozzáférési jogok konfigurálása egy költségobjektum-ellenőr számára
description: Ezzel az eljárásal konfigurálhatja a hozzáférési jogokat egy költségobjektum-ellenőr számára.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b7356706ea80c97fdf5b73faf32134a4aebacbb
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841441"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>Hozzáférési jogok konfigurálása egy költségobjektum-ellenőr számára

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ezzel az eljárásal konfigurálhatja a hozzáférési jogokat egy költségobjektum-ellenőr számára. Ez a felvétel az USP2 bemutató vállalati adatait használja.


## <a name="assign-the-cost-object-controller-role"></a>Költségobjektum-ellenőr szerepkör hozzárendelése
1. Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűkítsen a Felhasználónév mezőben az „aliz” szót beírva.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a Szerepkörök hozzárendelése elemre.
5. Keresse meg és jelölje ki a kívánt rekordot a listán.
6. Kattintson az OK gombra.

## <a name="enable-access-list-security"></a>Hozzáférési lista biztonságának engedélyezése
1. Lépjen a Költségkönyvelés > Dimenziók > Dimenzióhierarchiák pontra.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
    * Válassza ki a szervezetet.  
3. Kattintson a Szerkesztés lehetőségre.
4. A Hozzáférési lista hierarchia mezőben válassza az Igen lehetőséget.
5. Kattintson a Hierarchia megtekintése lehetőségre.

## <a name="assign-access-rights-to-user"></a>Hozzáférési jogok hozzárendelése a felhasználóhoz
1. Kattintson az Új lehetőségre.
2. A listában jelölje meg a kiválasztott sort.
3. A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza a Rendszergazda lehetőséget.  
4. A fán válassza a Szervezet>Vezérigazgató>Pénzügyi igazgató>FIM lehetőséget.
5. Kattintson az Új lehetőségre.
6. A listában jelölje meg a kiválasztott sort.
7. A Felhasználói azonosító mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki az Aliz lehetőséget.  
8. Kattintson a Mentés gombra.

## <a name="enable-access-rights-in-cost-accounting"></a>Hozzáférési jogok engedélyezése a Költségkönyvelésben
1. Lépjen a Költségkönyvelés > Beállítás > Paraméterek lehetőségre.
2. Kattintson az Általános fülre.
3. Válassza az Igen lehetőséget ki a Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése mezőben.
4. Kattintson a Mentés gombra.
5. Zárja be a lapot.
6. Lépjen a Költségkönyvelés > Beállítás > Költségellenőrzési munkaterület konfigurációja lehetőségre.
7. Kattintson a Szerkesztés lehetőségre.
8. Válassza az Igen lehetőséget a Közzétéve mezőben.
    * Ha Igen értékre állítja ezt a beállítást, a következő négy szerepkör valamelyikéhez hozzárendelt felhasználó láthatja a Költség-ellenőrzési munkaterület jelentéseit: költségkönyvelés-kezelő, költségkönyvelő, költségkönyvelő adminisztrátor vagy költségobjektum-ellenőr. Ha Nem értékre állítja ezt a beállítást, a következő szerepkörök valamelyikéhez hozzárendelt felhasználó láthatja a jelentéseket: költségkönyvelés-kezelő, költségkönyvelő és költségkönyvelő adminisztrátor.    
9. Kattintson a Mentés gombra.

