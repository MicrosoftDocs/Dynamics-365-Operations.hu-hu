---
title: TDS kiszámítása vállalatközi tranzakciókhoz
description: Ez a témakör azt a folyamatot írja le, amelyet a Forrásnál levont adó (TDS) kiszámítására használnak a vállalatközi tranzakciókhoz a fázisokban.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: c978c84891a0c1ce5a079484eec24590283027c4
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407922"
---
# <a name="tds-calculation-on-intercompany-transactions"></a>TDS kiszámítása vállalatközi tranzakciókhoz

[!include [banner](../includes/banner.md)]

Ez a témakör azt a folyamatot írja le, amelyet a Forrásnál levont adó (TDS) kiszámítására használnak a vállalatközi tranzakciókhoz a fázisokban.

Vállalatközi beszerzési vagy értékesítési rendelés létrehozásakor a vevő vagy szállító számára meghatározott alapértelmezett TDS-csoport szolgál a TDS-összeg kiszámítására. A TDS-összeg a számla könyvelése után kerül feladásra a visszatéríthető vagy fizetendő számlákra.

A vállalatközi értékesítési rendelés vagy beszerzési rendelés automatikusan létrejön az eredeti megrendeléshez vagy értékesítési megrendeléshez. Az alapértelmezett TDS-csoport megjelenik a vállalatközi rendelésben, így a TDS kiszámítható. A TDS-csoport módosítható. A számla csak akkor könyvelhető, ha az automatikusan létrehozott vállalatközi megrendelés nettó számlaösszege megegyezik az eredeti megrendelés nettó számlaösszegével. (A nettó összeg a számla összege a TDS levonása után.)

Például egy értékesítési számla jön létre 50 000 értékben és a **10%-os** TDS csoport van csatolva hozzá. A könyvelt számla összege 45 000, az értékesítési számla feladott TDS-összege pedig 5000. A vállalatközi értékesítési rendeléshez automatikusan létrejön egy beszerzési rendelés, amelyhez a **10%-os** TDS-csoport van csatolva. Ha a TDS csoportot **15%-ra** módosítja, nem tudja könyvelni a számlát, mert az automatikusan létrehozott vállalatközi értékesítési rendelés nettó számlaösszege nem egyezik meg az eredeti értékesítési rendelés nettó számlaösszegével.

A vállalatközi számlához létrehozott fizetési napló automatikusan könyvelve lesz. Ez a fizetési napló csak akkor könyvelhető, ha a rajta lévő nettó fizetési összeg megegyezik az eredeti fizetési naplóban található nettó fizetési összeggel.
