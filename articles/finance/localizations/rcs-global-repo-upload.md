---
title: Hozzon létre ER-konfigurációkat a RCS-ben, és töltse fel őket a globális tárházba
description: Ez a cikk bemutatja, hogy hogyan lehet elektronikus jelentési (ER) konfigurációt létrehozni a Microsoft Regulatory Configuration Services (RCS) szolgáltatásban, és feltölteni azt a globális tárházba.
author: JaneA07
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: f73f7189ad82d85169a4e0df573dd26dab8bb009
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070600"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>ER-konfigurációk létrehozása a Regulatory Configuration Services (RCS) rendszerben, és feltöltésük a globális tárba

[!include [banner](../includes/banner.md)]

A Microsoft Regulatory Configuration Services (RCS) segítségével elektronikus jelentéskészítési (ER) konfigurációk készíthetők, majd közzétehetők a szervezeten belüli felhasználásra.

A következő lépések leírják, hogy a rendszergazda vagy az elektronikus jelentéskészítési fejlesztői szerepkörben lévő felhasználók hogyan hozhatják létre az RCS-példányban konfigurált ER-konfiguráció egy származtatott verzióját, majd hogyan tölthetik fel a származtatott konfigurációt a globális tárba. 

Mielőtt teljesítené ezeket az eljárásokat, végre kell hajtania a következő előfeltételeket:

- Hozzáférése a szervezet RCS-környezetéhez.
- Hozzon létre egy aktív konfigurációs szolgáltatót, és tegye aktívvá. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.

Gondoskodnia kell arról, hogy a szervezethez rcS-környezet legyen létesítve. Ha nincs rcS-példánya létesítve a szervezethez, a következő lépések segítségével használhatja ezt:

1. Egy pénzügyi és műveleti alkalmazásban használja a **Szervezet** \> **felügyelete – Munkaterületek** \> **elektronikus jelentéseit**.
2. A **Kapcsolódó hivatkozások / Külső hivatkozások mezőben válassza** **a Jogi szolgáltatások –** Konfiguráció lehetőséget, **majd** az ehhez szükséges beállításokat követve hajtsa végre a regisztrációhoz szükséges utasításokat.

Ha már létesített RCS-környezetet a szervezethez, az oldal URL-címével **férhet hozzá, és válassza ki a bejelentkezési lehetőséget**.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Konfiguráció származtatott verziójának létrehozása az RCS-ben

> [!NOTE]
> Ha az RCS első alkalommal van használva, akkor nem lesz elérhető konfiguráció, amelyből származtatható. Konfigurációt kell importálni a globális tárházból. További információért lásd: [ER-konfigurációk letöltése a Konfigurációs szolgáltatás globális tárolójából](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. **Jelentkezzen be az** RCS-be, és válassza ki az Elektronikus **jelentéskészítés munkaterületet**.
2. Győződjön meg róla, hogy van aktív konfigurációszolgáltató a szervezetnél aktívra állítva (lásd az előfeltételeket). 
3. Válassza a **Jelentéskészítési konfigurációk** elemet.
4. Válassza ki azt a konfigurációt, amelyből új verziót szeretne származtatni. A fa feletti szűrő mező segítségével tovább szűkítheti a keresés eredményeit.
5. Válassza a **Konfiguráció létrehozása** \> **Származtatás névből** lehetőséget.
6. Írjon be egy nevet és egy leírást, **majd** válassza a Konfiguráció létrehozása lehetőséget egy "Vázlat" állapotú új származtatott verzió létrehozásához.
7. Válassza ki az újonnan származtatott konfigurációt, és szükség esetén adja meg a konfigurációs formátumot. 
8. A módosítások befejezése **után** **a** Konfiguráció módosítása "Befejezve" állapotúra kell állítani, hogy közzé tudja tenni a tárházban. Válassza ki az **OK** lehetőséget.

![Új konfigurációverzió az RCS-ben.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> A konfiguráció állapotának módosításakor előfordulhat, hogy a csatlakoztatott alkalmazásokhoz kapcsolódó ellenőrzési hibaüzenet jelenik meg. Ha ki szeretné kapcsolni a hitelesítést, válassza ki a Művelet panelen a **Konfigurációk** lapot, válassza a **Felhasználói paraméterek** lehetőséget, majd állítsa be a **Konfiguráció állapotváltozással és új alappal kapcsolatos érvényesítésének kihagyása** beállítást **Igen** értékre. 

## <a name="upload-a-configuration-to-the-global-repository"></a>Konfiguráció feltöltése a globális tárba

Ha egy új vagy származtatott konfigurációt meg kell osztania a szervezettel, akkor a következő lépésekkel töltheti fel a globális tárházba:

1. Válassza ki a konfiguráció kész verzióját, majd válassza a **Feltöltés a tárba** parancsot.
2. Válassza ki a **Globális (Microsoft)** beállítást, majd válassza a **Feltöltés** elemet.

    ![Feltöltés a tárba beállításai.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. A megerősítő párbeszédpanelen válassza az **Igen** gombot. 
4. Szükség szerint frissítse a verzió leírását, majd kattintson az **OK** gombra. A verzió tetszés szerint feltölthető egy csatlakoztatott alkalmazásba vagy EGYSTB-tárházba is.  

A konfiguráció állapota "**Megosztott**" lesz, és a rendszer feltölti a konfigurációt a globális tárházba. Létrejön a feltöltött konfiguráció vázlatverziója is, amely akkor használható, ha a további módosítások szükségesek.

Miután a konfiguráció fel lett töltve a globális tárházba, a következőképpen lehet vele dolgozni:

- Importálhatja a Dynamics 365-példányába. További információ: [(ER) Konfigurációk importálása RCS-ből](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Megoszthatja egy harmadik féllel vagy külső szervezettel, lásd: [RCS elektronikus jelentéskészítési (ER) konfigurációk megosztása külső szervezetekkel](rcs-global-repo-share-configuration.md)

    ![A globális tárházban található származtatott Intrastat Contoso konfigurációs verzió.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Konfiguráció törlése a Globális adattárból
Hajtsa végre a következő lépéseket a szervezete által létrehozott konfiguráció törléséhez.

1. Az **Elektronikus jelentés** munkaterületen ellenőrizze, hogy konfigurációszolgáltató állapota **Aktív**. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
2. Válassza az aktív konfiguráció szolgáltatójának **adattár** elemét.
3. Válassza ki az adattár típusának a **Globális** értéket, majd válassza a **Megnyitás** lehetőséget.
4. A **Szűrő** gyorslapon keresse meg azt a konfigurációt, amelyet törölni szeretne a **Szűrő** funkció segítségével.
5. A **Verzió** gyorslapon válassza ki a törölni kívánt konfiguráció verziószámát, majd válassza a **Törlés** lehetőséget:

    ![Konfiguráció törlése a globális adattárból.](media/RCS_Delete_from_GlobalRepo.JPG)

6. A megerősítő párbeszédpanelen válassza az **Igen** gombot.

    ![Konfigurációverzió visszaigazolási üzenetének törlése.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
A konfigurációverziót törölve lesz, és egy megerősítő üzenet jelenik meg. 

> [!NOTE]
> A konfigurációkat csak az azokat létrehozó Konfigurációs szolgáltató tudja törölni. Ha egy másik szervezettel meg lett osztva a konfiguráció, akkor a konfiguráció törlése előtt a megosztást meg kell szüntetni.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

