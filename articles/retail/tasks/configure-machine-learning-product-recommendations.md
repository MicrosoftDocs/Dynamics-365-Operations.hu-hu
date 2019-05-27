---
title: Gépi tanulási alapú termékajánlások konfigurálása
description: Ez az eljárás frissíti azokat az adatokat az entitástárban, amelyeket a termékajánlásokért felelős gépi tanulási rendszer használ, majd ezt követően engedélyezi a termékajánlásokat a pénztárügyfeleken.
author: ashishmsft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BIMeasurementDeployManagementEntityStore, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 700af913f18e23c66db53a92033def06818af1ec
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548439"
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

