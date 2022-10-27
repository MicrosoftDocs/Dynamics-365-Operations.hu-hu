---
title: Banki napló összetett entitás frissítése
description: Ez a cikk felsorolja azokat a lépéseket, amelyek szükségesek ahhoz, hogy a BankTransactionType mezőt hozzá kell adni az összetett BankJournalEntity tulajdonsághoz.
author: angelad116
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer
ms.reviewer: kfend
ms.custom: 221654
ms.assetid: adb8146b-eb21-4be2-a338-a5b299fcc9a0
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1855f9680ba6bcf8eb46608882a128b4a21f0dac
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2022
ms.locfileid: "9715203"
---
# <a name="update-the-bank-journal-composite-entity"></a>Banki napló összetett entitás frissítése

[!include [banner](../includes/banner.md)]

Ez a cikk felsorolja azokat a lépéseket, amelyek szükségesek ahhoz, hogy a BankTransactionType mezőt hozzá kell adni az összetett BankJournalEntity tulajdonsághoz.

A következő lépések segítségével az összetett BankJournalEntity lehetőséghez adja hozzá a további BankTransactionType mezőt.

1.  Állítsa össze és szinkronizálja a következő banki napló összetett entitásokat, entitásokat és előkészítési táblákat:
    -   Összetett entitás\\BankJournalEntity
    -   Entitás\\BankJournalHeaderEntity
    -   Entitás\\BankJournalLineEntity
    -   Tábla\\BankJournalHeaderStaging
    -   Tábla\\BankJournalLineStaging

2.  Adatok kezelése\\adatprojektek
    -   Jelenítse meg a **Banki tranzakció** típusát a **Forrásadatok** elrendezésben.
        -   Forrásadatok formátuma = XML-elem
        -   Entitás neve = Banki napló
        -   Adatfájl feltöltése = SampleBankJournalCompositeEntity.xml új verziója
        -   Kattintson az **Igen** gombra a meglévő fájl felülírásához.
        -   Kattintson az **Igen** lehetőségre a hozzárendelés elejétől kezdve történő létrehozásához.
        -   Győződjön meg róla, hogy hozzárendelte a Banki tranzakció típusát.
            -   Kattintson a **Leképezés megtekintése** lehetőségre a Sor entitáson.
            -   Ellenőrizze, hogy a Banki tranzakció típusa hozzá van-e rendelve a forrásból az előkészítéshez.

3.  Importálja az új kivonatot.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
