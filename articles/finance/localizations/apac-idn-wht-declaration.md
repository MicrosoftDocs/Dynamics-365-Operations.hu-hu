---
title: Adóelőleg-jelentés Indonéziában
description: Ez a cikk bemutatja, hogyan kell konfigurálni és generálni az indonéz adóelőleg-jelentést.
author: sndray
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: sndray
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8acd9442ff4f0b7c19e3b4fcf211acce002e43d5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883181"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Adóelőleg-jelentés Indonéziában (ID-00005)

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan lehet beállítani és létrehozni az indonéz jogi személyek által az e-Bupot alkalmazásban az adóelőleg-tranzakciók jelentéséhez használt PPH-adóelőleg-fájlt.

Az indonéz adóhatóság (EFT) határozza meg, hogy a KPP Prtama (PKP) által a jövedelemadó (PPh) 23. és/vagy 26. cikke (23. és/vagy 26. cikk) adóőrzőként/-gyűjtőként regisztrált adóköteles adóhatóságának (PKP) elektronikus úton kell jelentenie a Jövedelemadó-bevallás 23. és 26. cikkét az e-Bupot alkalmazás segítségével. 

- **23 . cikk** – a jelentés tartalmaz minden olyan szállítótól származó adóelőleg-tranzakciót, amelyekben az elsődleges cím ország-/régiókódja Az Indonéz terület kódja.
- **26** . cikk – a jelentés olyan szállítók összes adóelőleg-tranzakcióját tartalmazza, amelyekben az elsődleges cím ország-/régiókódja nem Indonéz tartomány kódja.

## <a name="prerequisites"></a>Előfeltételek

- A jogi személy elsődleges címének Indonéziában kell lennie.
- A Szolgáltatáskezelés munkaterületén **engedélyezni** kell a Globális adóelőleg **szolgáltatást.** A funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="download-electronic-reporting-configurations"></a>Elektronikus jelentéskészítési konfigurációk letöltése

Az importfájl generálása az elektronikus jelentési (ER) konfigurációkon alapul. A konfigurálható jelentésekkel kapcsolatos funkciókról és fogalmakról további információkat itt talál: [Elektronikus jelentéskészítés](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

A termelési és felhasználói elfogadási tesztelési (UAT) környezetekben kövesse [az Elektronikus jelentéskészítési konfigurációk letöltése a Lifecycle Services szolgáltatásból útmutatót](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Az importfájl létrehozásához töltse fel a tárházból a következő konfigurációkat:

- **Adóbevallási modell.version.93.xml vagy** újabb verzió
- **Adóbevallási modell mapping.version.93.153.xml** vagy újabb verzió
- **Milyen PPh séma importálása (ID).version.93.14** vagy újabb verzió

## <a name="set-up-general-ledger-parameters"></a>Főkönyvi paraméterek beállítása

1. Ugrás az **Adóbeállítás** \> **főkönyvi** \> **paramétereihez.**
2. Az Adóelőleg **lap** **Mi bevallás** **formátum-hozzárendelési mezőjében válassza ki a Mi PPh séma importálását (ID)**. 
3. Az Adóelőleg-adóelőleg **·** \> **·** \> **·** \> **·** **bevételtípusának** az Adóelőleg-bevallás bevételtípusának beállításához menjen el az Adóelőleg-adóelőlegek adóelőleg-típusának beállításához, és rendelje hozzá a kódokat a kapcsolódó cikk adóelőleg-csoportjaihoz. A kódokat az e-Bupot alkalmazás segítségével kell generálni az integrációs fájlhoz. 

## <a name="generate-the-withholding-import-file"></a>Az adóelőleg-importfájl létrehozása

Az e-Bupot-fájl egy adott időszakra történő előkészítésének és előállításának folyamata a kifizetés adóelőleg-feladat során feladott adóelőleg-tranzakciókon alapul.

A fájl létrehozásához hajtsa végre a következő lépéseket.

1. Ugrás az **adóelőleg-adóelőleg-importfájlhoz** \> **·** \> **·** \> **(e-bupot 23 és 26).**
2. Válassza ki a jelentés "a" és a "to" dátumát, majd válassza ki a kiegyenlítési időszakot.
3. Adja meg a tranzakció dátumát, majd válassza az **OK gombra**.
4. Válassza ki a nyelvet. Minden jelentés angol (**en-us**) és indonéz nyelvre (id) van **lefordítva**.
5. Válassza ki az üzleti típust, majd adja meg a csekk- és dokumentumszámokat. 
6. Ellenőrizze, hogy a jelentést aláírta-e a vezető. Ez az információ a fájlban van jelentve. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
