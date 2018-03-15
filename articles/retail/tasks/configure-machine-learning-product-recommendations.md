--- 
title: "Gépi tanulási alapú termékajánlások konfigurálása"
description: "Ez az eljárás frissíti azokat az adatokat az entitástárban, amelyeket a termékajánlásokért felelős gépi tanulási rendszer használ, majd ezt követően engedélyezi a termékajánlásokat a pénztárügyfeleken."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 277ffb879b80fe57deeaa2b52c1543baaf820274
ms.contentlocale: hu-hu
ms.lasthandoff: 02/07/2018

---
# <a name="configure-machine-learning-powered-product-recommendations"></a>Gépi tanulási alapú termékajánlások konfigurálása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás frissíti azokat az adatokat az entitástárban, amelyeket a termékajánlásokért felelős gépi tanulási rendszer használ, majd ezt követően engedélyezi a termékajánlásokat a pénztárügyfeleken. Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.

1. Ugrás a Rendszerfelügyelet > Beállítás > Entitástár elemre.
2. Keresse meg és jelölje ki a „RetailSales” rekordot a listán.
3. Kattintson a Frissítés gombra.
4. Kattintson az OK gombra.
5. Zárja be a lapot.
6. Ugrás a Kiskereskedelem > Központ beállítás > Paraméterek > Kiskereskedelmi paraméterek elemre.
7. Kattintson a Gépi tanulás fülre.
8. Válassza az „Igen” lehetőséget a Termékajánlatok engedélyezése mezőben.
    * Ha „Az ajánlatmodellek beolvasása sikertelen volt” üzenet jelenik meg, ez azért történik, mert a közelmúltban frissítette az entitástárat, és előfordulhat, hogy a rendszer még nem végzett az új adatok feldolgozásával. Várjon 2-3 órát, majd próbálkozzon újra.  
9. Kattintson a Mentés gombra.
10. Zárja be a lapot.


