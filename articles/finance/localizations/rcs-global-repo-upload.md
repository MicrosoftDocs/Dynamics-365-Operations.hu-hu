---
title: ER-konfigurációk létrehozása az RCS-ben, és feltöltésük a globális tárba
description: Ez a témakör azt mutatja be, hogyan hozhatók létre a Microsoft Regulatory Configuration Services (RCS) elektronikus jelentéskészítési (ER) konfigurációi, és tölthetők fel a globális tárba.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f45749e1bf26eb6f19f326ba8bd15c08436943ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5218806"
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

![Új konfigurációverzió az RCS-ben](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> A konfiguráció állapotának módosításakor előfordulhat, hogy a csatlakoztatott alkalmazásokhoz kapcsolódó ellenőrzési hibaüzenet jelenik meg. Ha ki szeretné kapcsolni a hitelesítést, válassza ki a Művelet panelen a **Konfigurációk** lapot, válassza a **Felhasználói paraméterek** lehetőséget, majd állítsa be a **Konfiguráció állapotváltozással és új alappal kapcsolatos érvényesítésének kihagyása** beállítást **Igen** értékre. 

## <a name="upload-a-configuration-to-the-global-repository"></a>Konfiguráció feltöltése a globális tárba

Ha új vagy származtatott konfiguráció szeretne megosztani a szervezettel, akkor feltöltheti azt a globális tárba.

1. Válassza ki a konfiguráció kész verzióját, majd válassza a **Feltöltés a tárba** parancsot.
2. Válassza ki a **Globális (Microsoft)** beállítást, majd válassza a **Feltöltés** elemet.

    ![Feltöltés a tárba beállításai](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. A megerősítő párbeszédpanelen válassza az **Igen** gombot. 
4. Szükség szerint frissítse a verzió leírását, majd kattintson az **OK** gombra. 

A konfiguráció állapota **Megosztás** értékre frissül, és a konfiguráció feltöltésre kerül a globális tárba. Innen a következő módokon dolgozhat vele:

- Importálhatja a Dynamics 365-példányába. További információ: [(ER) Konfigurációk importálása RCS-ből](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Megoszthatja egy harmadik féllel vagy külső szervezettel, lásd: [RCS elektronikus jelentéskészítési (ER) konfigurációk megosztása külső szervezetekkel](rcs-global-repo-share-configuration.md)

    ![Származtatott Intrastat Contoso konfigurációverzió a globális tárban](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Konfiguráció törlése a Globális adattárból
Hajtsa végre a következő lépéseket a szervezete által létrehozott konfiguráció törléséhez.

1. Az **Elektronikus jelentés** munkaterületen ellenőrizze, hogy konfigurációszolgáltató állapota **Aktív**. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
2. Válassza az aktív konfiguráció szolgáltatójának **adattár** elemét.
3. Válassza ki az adattár típusának a **Globális** értéket, majd válassza a **Megnyitás** lehetőséget.
4. A **Szűrő** gyorslapon keresse meg azt a konfigurációt, amelyet törölni szeretne a **Szűrő** funkció segítségével.
5. A **Verzió** gyorslapon válassza ki a törölni kívánt konfiguráció verziószámát, majd válassza a **Törlés** lehetőséget:

    ![Konfiguráció törlése a globális adattárból](media/RCS_Delete_from_GlobalRepo.JPG)

6. A megerősítő párbeszédpanelen válassza az **Igen** gombot.

    ![Konfigurációverzió visszaigazolási üzenetének törlése](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
A konfigurációverziót törölve lesz, és egy megerősítő üzenet jelenik meg. 

> [!NOTE]
> A konfigurációkat csak az azokat létrehozó Konfigurációs szolgáltató tudja törölni. Ha egy másik szervezettel meg lett osztva a konfiguráció, akkor a konfiguráció törlése előtt a megosztást meg kell szüntetni.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]