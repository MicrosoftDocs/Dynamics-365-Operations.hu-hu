---
title: Az SQL Server Reporting Services konfigurálása on-premises telepítésekhez
description: Ez a témakör információkat nyújt az SQL Server Reporting Services (SSRS) szolgáltatásról on-premises telepítés esetén.
author: PeterRFriis
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: perahlff
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 2577705b04beef1f8b03f83ed8536be2e6ab6e83
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683921"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>Az SQL Server Reporting Services konfigurálása on-premises telepítésekhez

[!include [banner](../includes/banner.md)]

Kövesse a témakörben található a lépéseket az SQL Server Reporting Services (SRRS) konfigurálásához a Microsoft Dynamics 365 Finance + Operations (helyszíni) telepítéséhez.

1. Nyissa meg a Reporting Services konfigurációkezelő alkalmazást.
2. Hagyja meg az alapértelmezett **Kiszolgálónév** értéket, amelynek a jelenlegi gép nevének kell lennie, valamint a **Jelentéskészítő kiszolgáló példánya** is legyen az alapértelmezett **MSSQLSERVER**.
3. Kattintson a **Kapcsolódás** lehetőségre.

    [![Jelentéskészítő szolgáltatások konfigurációs kapcsolata](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. Kattintson a **Szolgáltatásfiók** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.

    [![Szolgáltatásfiók lap](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. Kattintson a **Webszolgáltatás URL-címe** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.

    [![Webszolgáltatás URL-címe lap](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. Kattintson az **Adatbázis** fülre, és ellenőrizze, hogy az **Adatbázisnév** és a **Hitelesítő beállítások** megfelelnek az alábbi ábrán láthatóaknak.

    > [!NOTE]
    > Szüksége lesz új adatbázis létrehozására. Ehhez kattintson az **Adatbázis módosítása** lehetőségre, majd győződjön meg róla, hogy az új adatbázis neve a **DynamicsAxReportServer**.

    [![adatbázis lap](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. Kattintson a **Webportál URL-címe** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.

    > [!NOTE]
    > Rá kell kattintania az **Alkalmaz** lehetőségre a portál létrehozásához és megfelelő konfigurálásához.

    [![webportál url-címe lap](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    A portál beállítása után a **Webes portál** lap az alábbi ábrával fog megegyezni.

    [![webportál lap](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. Kattintson a jelentések URL-jére az SQL Server Reporting Services webportál megtekintéséhez.
9. A portálon hozzon létre egy új, **Dynamics** nevű mappát.

    [![dynamics mappa](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. A **Reporting Services konfigurációkezelőben** kattintson az **E-mail beállítások** lapfülre, és ellenőrizze, hogy a beállítások megfelelnek-e az alábbi ábrán láthatóaknak.

    [![e-mail beállítások lap](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. Kattintson a **Végrehajtó fiók** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.

    [![végrehajtó fiók lap](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    Ne módosítsa az alapértelmezett beállításokat a **Titkosítási kulcsok** lapon.

    [![titkosítási kulcsok lap](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. Kattintson az **Előfizetési beállítások** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.

    [![előfizetési beállítások lap](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    Ne módosítsa az alapértelmezett beállításokat a **Skálázott telepítés** lapon.

    [![skálázott telepítés lap](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    Ne módosítsa az alapértelmezett beállításokat a **Power BI-integráció** lapon.

    [![power BI-integráció lap](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. Kattintson a **Kilépés** ikonra a **Reporting Services konfigurációkezelő** bezárásához.

    [![a reporting services konfigurációkezelőjének bezárása](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)
