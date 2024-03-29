---
title: Könyvelésre váró dokumentumok
description: Ez a cikk ismerteti, hogy hogyan kell használni a funkcionalitást a Könyvelésre váró dokumentumok oldalon.
author: ryanCCarlson2
ms.date: 09/02/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: f37d46659b2fc5bf9933719811a7b90cc4e80f52
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709249"
---
# <a name="documents-pending-accounting"></a>Könyvelésre váró dokumentumok

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti, hogy hogyan kell használni a funkcionalitást a **Könyvelésre váró dokumentumok** oldalon.

A Microsoft Dynamics 365 Finance 10.0.30-ban elérhető a **Forrásbizonylatok könyvelési keretrendszerének továbbfejlesztett teljesítménye** funkció. Ez a funkció javítja a forrásbizonylatokkal engedélyezett dokumentumfeladások feladási folyamatát a szabadszöveges számlák esetében.

Ha ez a funkció engedélyezve van, akkor az analitikus dokumentum feladása a könyvelés-generálási vagy *naplózási* folyamattól függetlenül történik, így a főkönyvbe átkerülnek a könyvelési adatok részletei. Például a szabadszöveges számla feladási folyamata során a **Kinnlevőségek** modulban szereplő vevői számlát a teljes könyvelés létrehozása előtt rögzíti a rendszer. Ezzel a továbbfejlesztett teljesítmény funkcióval gyorsabban lehet rögzíteni a vevői számlákat, ha a könyvelés generálása késik.

A **Könyvelésre váró dokumentumok** lapon a következő gombok érhetők el.

- **Könyvelés generálása** – Egy olyan dokumentum elküldése, amelynél jelenleg függőben van a számla generálása a naplózáshoz.
- **Felosztások megtekintése** – A listában kiválasztott dokumentum könyvelési felosztásának megtekintése.
- **Hibanapló megtekintése** – Olyan hibaüzenet-részletek megtekintése, amelyek olyan dokumentumnál léteznek, amelyeknél a könyvelési állapot hibát jelez. Ugyanezeket a hibaüzenet-részleteket megtekintheti úgy is, hogy rákattint a dokumentumsor **Hibanapló** hivatkozására.

A könyvelés generálását a **Könyvelési keretrendszer feldolgozója** nevű folyamatautomatizálási háttérfolyamat végzi el. Az összes folyamatautomatizálási beállítással és konfigurációval kapcsolatos további információhoz lásd a [Folyamatautomatizálás](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md) részt.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
