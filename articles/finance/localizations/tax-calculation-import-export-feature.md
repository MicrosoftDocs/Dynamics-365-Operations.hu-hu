---
title: Adószámítások importálása és exportálása
description: Ez a témakör az adószámítási szolgáltatás importálási és exportálási funkcióival kapcsolatban tartalmaz tájékoztatást.
author: Kai-Cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-11-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 76ea99510455e984d94a93d87ee788fdcf00c376
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891357"
---
# <a name="import-and-export-tax-calculations"></a>Adószámítások importálása és exportálása

Ez a témakör az adószámítási szolgáltatás importálási és exportálási funkcióival kapcsolatban tartalmaz tájékoztatást. Ez a funkció rugalmas és hatékony konfigurálást biztosít.

## <a name="import-and-export-tax-codes"></a>Adókódok importálása és exportálása

### <a name="export-templates"></a>Sablonok exportálása

1. Jelentkezzen be a [szabályozó konfigurációs szolgáltatásba (RCS)](https://marketing.configure.global.dynamics.com/).
2. A **Globalizációs funkciók** munkaterületén válassza a Funkciók **lehetőséget**, majd válassza az **Adószámítás** csempe lehetőséget.
3. Válasszon ki egy meglévő funkciót, vagy [hozzon létre egy új](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs) szolgáltatást.
4. A **Verziók** rácsban válassza a **Szerkesztés** lehetőséget.
5. Az **Adószámítás** funkciólapon állítsa be [a konfiguráció](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs) verzióját.
6. Az **Adókódok** lapon válassza az Importálás **lehetőséget**.
7. A **·** **TaxCodesTemplate.zip fájl letöltéséhez válasszon egy adókódsablon** exportálását.
8. A **TaxCodesTemplate.zip kódot nem lehet** kibontani. Az adókódsablonok tömörítése a Számítás **eredete értéknek megfelelően külön** történik.
9. A NETTÓ **összeg.zip szerint kibontva a következő, vesszővel elválasztott** (CSV) fájlokat kapják:

    - **TaxCode.csv** – az adókódok beírása.
    - **TaxLimit.csv – adja meg** az egyes adókódok adókorlátját.
    - **TaxRate.csv – adja meg** az egyes adókódokra vonatkozó adómértékeket.

> [!NOTE]
> Alapértelmezés szerint a mintaadó kódhoz **bejegyzései** érhetők el a sablonokban. Ha a Minta adókód nem **távolítható el a CSV-fájlokból, akkor a rendszer importálja** a szolgáltatásba.

### <a name="import-tax-codes"></a>Importadókódok

A következő lépések szerint importálhatja a sablonban található **mintaadókódot** az adószámítási funkcióba.

1. Válassza az Importálás lehetőséget az RCS rendszer Adószámítási **funkciólapjának** **Adókódok** **lapján**.
2. Válassza a Tallózás lehetőséget, keresse meg és válassza ki a **TaxCode**.csv fájlt, majd válassza ki az Adókódot **a** **Céltábla** **mezőben**.
3. Az **áfakód** importálása az OK gombra.
4. Keresse meg és válassza ki a **TaxRate.csv fájlt, majd a Cél tábla mezőben válassza** ki **az** **adókulcsot.**
5. Az **áfakulcs** importálása az OK gombra.
6. Keresse meg és válassza ki a **TaxLimit.csv fájlt, majd a Cél tábla mezőben válassza** ki **az** **Adókorlátot.**
7. Az **adókorlát** importálása az OK gombra.

Közvetlenül is importálhatja azt az irányítószámot, amely mindhárom CSV-fájlt tartalmazza. Ily módon gyorsan és egyszerűen elvégezhető az importálás.

1. Válassza az Importálás lehetőséget az RCS rendszer Adószámítási **funkciólapjának** **Adókódok** **lapján**.
2. Válassza a Tallózás lehetőséget, keresse meg és válassza ki a Nettó összeg.zip fájl **alapján** **fájlt**, majd válassza az **OK** gombra.

### <a name="export-tax-codes"></a>Exportadókódok

1. Válassza az Exportálás lehetőséget az RCS rendszer Adószámítási **funkciólapjának** **Adókódok** **lapján**.

    Az Exportálás gomb akkor érhető el, ha az adókódok rácsában legalább **egy** **adókód** van.

2. Az OK gombra való beállítás esetén az irányítószámokat is exportálhatja az **irányítószámok** közül.

> [!NOTE]
> Az exportált fájl segítségével lehet adókódokat importálni a megfelelő szolgáltatásba.

## <a name="import-and-export-applicability-rules"></a>Alkalmazhatósági szabályok importálása és exportálása

### <a name="export-applicability-rules"></a>Alkalmazhatósági szabályok exportálása

1. Bejelentkezés az [RCS](https://marketing.configure.global.dynamics.com/) alkalmazásba.
2. A **Globalizációs funkciók** munkaterületén válassza a Funkciók **lehetőséget**, majd válassza az **Adószámítás** csempe lehetőséget.
3. Válasszon ki egy meglévő funkciót, vagy [hozzon létre egy új](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs) szolgáltatást.
4. A **Verziók** rácsban válassza a **Szerkesztés** lehetőséget.
5. Az **Adószámítás** funkciólapon állítsa be [a konfiguráció](global-get-started-with-tax-calculation-service.md#set-up-tax-calculation-in-rcs) verzióját.
6. Az Adócsoport alkalmazhatósága lapon jelölje ki a sorokat az Adócsoport-alkalmazhatósági **rács** beállítása **táblázatban**.
7. Válassza a **Megnyitás Microsoft Office** a gombon, majd válassza az **Adószolgáltatás dinamikus alkalmazhatósági** mátrixát.

    [![Alkalmazhatósági szabályok Microsoft Excel exportálása az adószámítási funkcióoldalra](./media/tax-cal-import-export-1.png)](./media/tax-cal-import-export-1.png)

8. Válassza **a Letöltés** lehetőséget, ha a kiválasztott sorokat egy munkalapra szeretné Microsoft Excel exportálni.

### <a name="import-applicability-rules"></a>Alkalmazhatósági szabályok importálása

A letöltött Excel-munkalap az Adócsoport-beállítási rács szerkezetét **tartalmazza**. Az új szabályokat közvetlenül a munkalapra lehet felvenni. Ha végzett, a következő lépésekkel importálhatja vissza az új szabályokat az Adócsoport-alkalmazhatósági **rács** beállítása rácsba.

1. Az Excel-munkalapon válassza ki és másolja az importálni kívánt sorokat.
2. Az RCS rendszer Adószámítás funkciólapjának Adócsoport alkalmazhatósági lapján válassza a Hozzáadás lehetőséget, ha üres rekordot szeretne beszúrni az Adócsoport-alkalmazhatósági rács **alsó** **·** **·** **részén**.
3. A **ctrl+V** billentyűkombinációval beillesztheti a másolt sorokat a rácsba.
4. Válassza a **Mentés** lehetőséget.
