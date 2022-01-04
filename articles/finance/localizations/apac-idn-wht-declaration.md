---
title: Forrásadó-jelentés Indonéziára
description: Ez a témakör bemutatja, hogyan konfigurálhatja és generálhatja az indonéziai forrásadó-jelentést.
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
ms.openlocfilehash: 6cf2f9240ea747054578c52343af34b15c250f38
ms.sourcegitcommit: f51e74ee9162fe2b63c6ce236e514840795acfe1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944139"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Forrásadó-jelentés Indonéziára (ID-00005)

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet beállítani és létrehozni azt a PPH forrásadó-fájlt, amelyet az indonéz jogi személyek használnak az e-Bupot alkalmazás forrástranzakcióinak bejelentésére.

Az indonéz adóhatóság (DGT) megállapítja, hogy a KPP Pratama-nál adóként nyilvántartásba vett adóköteles vállalkozóknak (PKP) a jövedelemadó 23. és/vagy 26. cikkének részvényeseivel/beszedőivel elektronikus úton kell bejelenteniük a jövedelemadó-bevallás 23. és 26. cikkét az e-Bupot kérelem alkalmazásával. 

- **23. cikk** A jelentés tartalmazza az összes olyan szállítótól származó visszatartási tranzakciót, ahol az elsődleges cím ország/régió kódja Indonézia kódja.
- **26. cikk** A jelentés tartalmazza az összes olyan szállítótól származó visszatartási tranzakciót, ahol az elsődleges cím ország/régió kódja nem Indonézia kódja.

## <a name="prerequisites"></a>Előfeltételek

- A jogi személy elsődleges címének Indonéziában kell lennie.
- A **Szolgáltatáskezelési** munkaterületen engedélyezni kell a **globális forrásadó** funkciót. A funkciók engedélyezésével kapcsolatos további tudnivalókat lásd: [Funkciókezelés áttekintése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="download-electronic-reporting-configurations"></a>Elektronikus jelentéskészítési konfigurációk letöltése

Az importálási fájl létrehozása elektronikus jelentési (ER) konfigurációkon alapul. A konfigurálható jelentésekkel kapcsolatos funkciókról és fogalmakról további információkat itt talál: [Elektronikus jelentéskészítés](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Éles és felhasználói elfogadási tesztelési (UAT) környezetek esetén kövesse az [Elektronikus jelentési konfigurációk letöltése az életciklus-szolgáltatásokból című témakör utasításait.](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)

Az importálási fájl létrehozásához töltse fel a következő konfigurációkat az adattárból:

- **Adóbevallás model.version.93.xml** vagy újabb verzió
- **Adóbevallási modell mapping.version.93.153.xml** vagy egy későbbi verzió
- **Milyen PPh sémaimportálás (ID).version.93.14** vagy újabb verzió

## <a name="set-up-general-ledger-parameters"></a>Főkönyvi paraméterek beállítása

1. Lépjen **a** \> **Adóbeállítás** \> **főkönyvi paraméterei** elemre.
2. A **Forrásadó** lap **What deklarációs formátumleképezés** mezőjében válassza a Mi **PPh sémaimportálás (ID)** lehetőséget. 
3. A **·** \> **·** \> **·** \> **Kode Bukti Potong forrásadó-bevételtípus beállításához lépjen az Adóbeállítás forrásadó-forrásadó-bevételtípusra,** **majd** rendelje hozzá a kódokat a kapcsolódó cikkadó-csoportokhoz. A kódok szükségesek az integrációs fájl létrehozásához az e-Bupot alkalmazás használatával. 

## <a name="generate-the-withholding-import-file"></a>A forrásimportáló importálási fájl létrehozása

Az e-Bupot fájl egy adott időszakra történő előkészítésének és létrehozásának folyamata az elszámolási vagy utáni fizetési adófeladat során feladott forrásadó-tranzakciókon alapul.

A fájl létrehozásához kövesse az alábbi lépéseket.

1. Lépjen **az** \> **adóbevallások** \> **forrásadó-ÁF** \> **importfájl e-bupot 23 és 26**.
2. Válassza ki a jelentés "from" és "to" dátumát, majd válassza ki az elszámolási időszakot.
3. Adja meg a tranzakció dátumát, majd válassza a **OK** lehetőséget.
4. Válassza ki a nyelvet. Minden jelentést lefordítanak amerikai angol **(en-us)** és indonéz **(id**).
5. Válassza ki a vállalkozás típusát, majd adja meg a csekk- és bizonylatszámokat. 
6. Ellenőrizze, hogy a jelentést a menedzser írta-e alá. Ez az információ a fájlban jelent. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
