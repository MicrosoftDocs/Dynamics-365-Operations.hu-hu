---
title: Továbbfejlesztett banki egyeztetés importálásának beállítása az Elektronikus jelentés segítségével
description: Ez a témakör bemutatja az Elektronikus jelentéskészítés segítségével a továbbfejlesztett banki egyeztetés importálási folyamatának beállítását.
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
ms.openlocfilehash: 30530a9870ba2ff0546237d2698d1675afa78104
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770194"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Továbbfejlesztett banki egyeztetés importálásának beállítása az Elektronikus jelentés segítségével

[!include [banner](../includes/banner.md)]

A Speciális banki egyeztetési funkció lehetővé teszi az elektronikus banki kivonatok importálását Microsoft Dynamics és automatikus egyeztetését a 365 Pénzügy banki tranzakcióival. Ez a témakör bemutatja a banki kivonatok importálási funkcióinak beállítását. A banki kivonat importálási beállítások az elektronikus banki kivonat formátumától függően változnak. Microsoft Dynamics A 365 Finance három banki kivonatformátumot támogat: ISO20022, MT940 és BAI2. 

## <a name="set-up-the-electronic-reporting-configuration"></a>Az elektronikusjelentés-konfiguráció beállítása

1. Ugrás a Munkaterületek **elektronikus \> jelentéséhez**
2. A Microsoft **konfigurációs szolgáltató csempe** tárházát **jelölje ki**.
3. Válassza ki a **Globális**, majd a **Megnyitás** lehetőséget.
4. Ha kapcsolatot kell létesíteni a tárházzal, jelölje ki a kék kapcsolatot a párbeszédpanelen.
5. A konfigurációs listában keresse meg a **\> BAI2** banki kivonatmodellját.
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


## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>A banki kivonat formátumainak és a technikai elrendezések példái
Az alábbiakban a továbbfejlesztett banki egyeztetési importfájl technikai elrendezésű definicóinak példáit és a három kapcsolódó banki kivonat példafájljait találhatja: [Importfájl-példák](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Technikai elrendezésdefiníció                             | Banki kivonat példafájl          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)     |
| DynamicsAXISO20022Layout | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)     |

