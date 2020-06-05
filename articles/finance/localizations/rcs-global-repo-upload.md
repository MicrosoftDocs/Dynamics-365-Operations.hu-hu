---
title: ER-konfigurációk létrehozása az RCS-ben, és feltöltésük a globális tárba
description: Ez a témakör azt mutatja be, hogyan hozhatók létre a Microsoft Regulatory Configuration Services (RCS) elektronikus jelentéskészítési (ER) konfigurációi, és tölthetők fel a globális tárba.
author: JaneA07
manager: AnnBe
ms.date: 05/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0e194a8b777f984412d81e315f92ab4bb8a3b0c9
ms.sourcegitcommit: 204cec8ca2a6c4474d21dbcd408e369131a47856
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/13/2020
ms.locfileid: "3371249"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>ER-konfigurációk létrehozása a Regulatory Configuration Services (RCS) rendszerben, és feltöltésük a globális tárba

[!include [banner](../includes/banner.md)]

A Microsoft Regulatory Configuration Services (RCS) segítségével elektronikus jelentéskészítési (ER) konfigurációk készíthetők, majd közzétehetők a szervezeten belüli felhasználásra.

A következő lépések leírják, hogy a rendszergazda vagy az elektronikus jelentéskészítési fejlesztői szerepkörben lévő felhasználók hogyan hozhatják létre az RCS-példányban konfigurált ER-konfiguráció egy származtatott verzióját, majd hogyan tölthetik fel a származtatott konfigurációt a globális tárba. 

Mielőtt teljesítené ezeket az eljárásokat, végre kell hajtania a következő előfeltételeket:

- Nyisson meg egy RCS-példányt.
- Hozzon létre egy aktív konfigurációszolgáltatót. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

Arról is meg kell győződnie, hogy a vállalatnál RCS-környezet van kiépítve.

1. A Finance and Operations alkalmazásban lépjen a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.
2. Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – Külső konfiguráció** lehetőségre, és kövesse az RCS-környezet létrehozására vonatkozó instrukciókat.

Ha van már RCS-környezet létesítve a vállalat számára, akkor az oldal URL-címével érheti el a bejelentkezési beállítást.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Konfiguráció származtatott verziójának létrehozása az RCS-ben

1. Az **Elektronikus jelentéskészítés** munkaterületen ellenőrizze, hogy rendelkezik-e a szervezethez tartozó aktív konfigurációszolgáltatóval. 
2. Válassza a **Jelentéskészítési konfigurációk** elemet.
3. Válassza ki azt a konfigurációt, amelyből új verziót szeretne származtatni. A fa feletti szűrő mező segítségével tovább szűkítheti a keresés eredményeit.
4. Válassza a **Konfiguráció létrehozása** \> **Származtatás névből** lehetőséget.
5. Adjon meg egy nevet és egy leírást, majd válassza a **Konfiguráció létrehozása** lehetőséget egy új származtatott verzió létrehozásához.
6. Válassza ki az újonnan származtatott konfigurációt, adja meg a verzió leírását, majd kattintson az **OK** gombra. A konfiguráció állapota **Kész** értékre módosul.

![Új konfigurációverzió az RCS-ben](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_CompleteConfig.JPG)

> [!NOTE]
> A konfiguráció állapotának módosításakor előfordulhat, hogy a csatlakoztatott alkalmazásokhoz kapcsolódó ellenőrzési hibaüzenet jelenik meg. Ha ki szeretné kapcsolni a hitelesítést, válassza ki a Művelet panelen a **Konfigurációk** lapot, válassza a **Felhasználói paraméterek** lehetőséget, majd állítsa be a **Konfiguráció állapotváltozással és új alappal kapcsolatos érvényesítésének kihagyása** beállítást **Igen** értékre. 

## <a name="upload-a-configuration-to-the-global-repository"></a>Konfiguráció feltöltése a globális tárba

Ha új vagy származtatott konfiguráció szeretne megosztani a szervezettel, akkor feltöltheti azt a globális tárba.

1. Válassza ki a konfiguráció kész verzióját, majd válassza a **Feltöltés a tárba** parancsot.
2. Válassza ki a **Globális (Microsoft)** beállítást, majd válassza a **Feltöltés** elemet.

    ![Feltöltés a tárba beállításai](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Upload_to_GlobalRepo_options.JPG)

3. A megerősítő párbeszédpanelen válassza az **Igen** gombot. 
4. Szükség szerint frissítse a verzió leírását, majd kattintson az **OK** gombra. 

A konfiguráció állapota **Megosztás** értékre frissül, és a konfiguráció feltöltésre kerül a globális tárba. Innen a következő módokon dolgozhat vele:

- Importálhatja a Dynamics 365-példányába. További információ: [(ER) Konfigurációk importálása RCS-ből](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Megoszthatja egy harmadik féllel vagy külső szervezettel, lásd: [RCS elektronikus jelentéskészítési (ER) konfigurációk megosztása külső szervezetekkel](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/rcs-global-share-configuration.md)

![Származtatott Intrastat Contoso konfigurációverzió a globális tárban](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Config_upload_GlobalRepo.JPG)
