---
title: Továbbfejlesztett banki egyeztetés importálásának beállítása az Elektronikus jelentés segítségével
description: Ez a témakör bemutatja az Elektronikus jelentéskészítés segítségével a BAI2-kivonatok továbbfejlesztett banki egyeztetési importálási folyamatát.
author: panolte
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 39f1d8ba561ab0e36346f1dfb4f70df318c92a37
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544548"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Továbbfejlesztett banki egyeztetés importálásának beállítása az Elektronikus jelentés segítségével

[!include [banner](../includes/banner.md)]

A Speciális banki egyeztetési funkció lehetővé teszi az elektronikus banki kivonatok importálását Microsoft Dynamics és automatikus egyeztetését a 365 Pénzügy banki tranzakcióival. Ez a témakör bemutatja a BAI2 banki kivonatok importálási funkcióinak beállítását.

## <a name="set-up-the-electronic-reporting-configuration"></a>Az elektronikusjelentés-konfiguráció beállítása

1. Ugrás a Munkaterületek **elektronikus \> jelentéséhez**
2. A Microsoft **konfigurációs szolgáltató csempe** tárházát **jelölje ki**.
3. Válassza ki a **Globális**, majd a **Megnyitás** lehetőséget.
4. Ha kapcsolatot kell létesíteni a tárházzal, jelölje ki a kék kapcsolatot a párbeszédpanelen.
5. A konfigurációs listában keresse meg a **\> BAI2 banki kivonatmodellját**.
6. Válassza a **BAI2 formátumot**.
7. Válassza ki **a legújabb** verziót a Verziók gyorsgombra, majd válassza az Importálás **lehetőséget**.

## <a name="set-up-the-bank-statement-format"></a>A banki kivonat formátumának beállítása

1. Ugrás a Készpénz- **és bankkezelés beállítása \> - \> Speciális banki egyeztetés beállítása - \> Banki kivonat formátuma**
2. Válassza az **Új** lehetőséget.
3. Állítsa be **a Kimutatás formátuma és** **Neve mezőit**.
4. Jelölje be az **Általános elektronikus importálási formátum jelölőnégyzetet**.
5. Az Importformátum **konfigurációs mezőjének** beállítása **a BAI2 formátumra**.

## <a name="set-up-the-bank-account"></a>Bankszámla beállítása

1. Menjen a **Készpénz és bankkezelés \> Bankszámlák \> Bankszámlák menüpontra**.
2. Nyissa meg a bankszámlát.
3. Az Egyeztetés **gyorsgombon** állítsa **a Speciális banki egyeztetési** beállítást Igen **beállításra**.
4. Állítsa a **Kimutatás formátummezőt** a korábban **létrehozott BAI2-formátumra**.

## <a name="import-the-bank-statement"></a>A banki kivonat importálása

1. Ugrás a Készpénz- **és bankkezelés banki \> kivonategyeztetési \> banki kivonataihoz**.
2. A Banki kivonatok lap **tetején** válassza az **Import kivonatot**.
3. A Bankszámla **mező beállítása** a kivonatban a bankszámlához.
4. Állítsa a **Kimutatás formátummezőt** a korábban **létrehozott BAI2-formátumra**.
5. Válassza a **Tallózás** lehetőséget, majd válassza a **BAI-fájlt**.
6. Válassza a **Feltöltés** elemet.
7. A **kijelölt fájl importálása az OK** gombra.
