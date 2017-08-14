---
title: "Az SQL Server Reporting Services konfigurálása on-premises telepítéshez"
description: "Ez a témakör információkat nyújt az SQL Server Reporting Services (SSRS) szolgáltatásról on-premises telepítés esetén."
author: kfend
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, UnifiedOperations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanisathish
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: b0bfaadabe960f31d7609512b7ad6eaf848afddc
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="configure-sql-server-reporting-services-for-an-on-premises-deployment"></a>Az SQL Server Reporting Services konfigurálása on-premises telepítéshez

Az ebben a témakörben található lépésekkel konfigurálhatja az SQL Server Reporting Services (SSRS) szolgáltatást az Ön Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises) telepítésének megfelelően.

1. Nyissa meg a Reporting Services konfigurációkezelő alkalmazást.
2. Hagyja meg az alapértelmezett **Kiszolgálónév** értéket, amelynek a jelenlegi gép nevének kell lennie, valamint a **Jelentéskészítő kiszolgáló példánya** is legyen az alapértelmezett **MSSQLSERVER**. 
3. Kattintson a **Kapcsolódás** lehetőségre.
   
   [![Jelentéskészítő szolgáltatások konfigurációs kapcsolata](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)
   
4. Kattintson a **Szolgáltatásfiók** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.

    [![Szolgáltatásfiók lap](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)
    
5. Kattintson a **Webszolgáltatás URL-címe** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal. 

    [![Webszolgáltatás URL-címe lap](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png) 
    
6. Kattintson az **Adatbázis** fülre, és ellenőrizze, hogy az **Adatbázisnév** és a **Hitelesítő beállítások** megfelelnek az alábbi ábrán láthatóaknak. **Megjegyzés:** szüksége lesz új adatbázis létrehozására. Ehhez kattintson az **Adatbázis módosítása** lehetőségre, majd győződjön meg róla, hogy az új adatbázis neve a **DynamicsAxReportServer**.

    [![adatbázis lap](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)
    
7. Kattintson a **Webportál URL-címe** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal. **Megjegyzés:** Rá kell kattintania az **Alkalmaz** lehetőségre a portál létrehozásához és megfelelő konfigurálásához.

    [![webportál url-címe lap](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)
    
  A portál beállítása után a **Webes portál** lap az alábbi ábrával fog megegyezni.
    [![webportál lap](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)
    
8. Kattintson a jelentések URL-jére az SQL Server Reporting Services webportál megtekintéséhez. 
9.  A portálon hozzon létre egy új, **Dynamics** nevű mappát.

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
    


