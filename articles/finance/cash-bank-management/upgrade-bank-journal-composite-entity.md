---
title: Banki napló összetett entitásának frissítése
description: A következő lépéseket kell elvégeznie ahhoz, hogy az összetett BankJournalEntity lehetőséghez további BankTransactionType mezőt adjon hozzá.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 974d6b3b11df92debdec26860fd9eea00a9f2313
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188027"
---
# <a name="update-the-bank-journal-composite-entity"></a>Banki napló összetett entitásának frissítése

[!include [banner](../includes/banner.md)]

A következő lépéseket kell elvégeznie ahhoz, hogy az összetett BankJournalEntity lehetőséghez további BankTransactionType mezőt adjon hozzá.

A következő lépések segítségével az összetett BankJournalEntity lehetőséghez adja hozzá a további BankTransactionType mezőt.

1.  Állítsa össze és szinkronizálja a következő banki napló összetett entitásokat, entitásokat és előkészítési táblákat:
    -   Összetett entitás\\BankJournalEntity
    -   Entitás\\BankJournalHeaderEntity
    -   Entitás\\BankJournalLineEntity
    -   Tábla\\BankJournalHeaderStaging
    -   Tábla\\BankJournalLineStaging

2.  Adatok kezelése\\adatprojektek
    -   Jelenítse meg a **Banki tranzakció**típusát a **Forrásadatok**elrendezésben.
        -   Forrásadatok formátuma = XML-elem
        -   Entitás neve = Banki napló
        -   Adatfájl feltöltése = SampleBankJournalCompositeEntity.xml új verziója
        -   Kattintson az **Igen** gombra a meglévő fájl felülírásához.
        -   Kattintson az **Igen** lehetőségre a hozzárendelés elejétől kezdve történő létrehozásához.
        -   Győződjön meg róla, hogy hozzárendelte a Banki tranzakció típusát.
            -   Kattintson a **Leképezés megtekintése** lehetőségre a Sor entitáson.
            -   Ellenőrizze, hogy a Banki tranzakció típusa hozzá van-e rendelve a forrásból az előkészítéshez.

3.  Importálja az új kivonatot.




