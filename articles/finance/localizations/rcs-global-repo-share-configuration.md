---
title: RCS/globális tárak ER-konfigurációinak megosztása külső szervezetekkel
description: Ez a cikk bemutatja, hogy hogyan oszthatja meg az elektronikus jelentéskészítési (ER) konfigurációkat a Microsoft Regulatory Configuration Services (RCS)/a globális tárház közvetlen külső szervezetekkel.
author: JaneA07
ms.date: 05/04/2020
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
ms.openlocfilehash: 976a86aee75581d1afa764bea049b6c0eaecf9f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888923"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>A Regulatory Configuration Services (RCS) globális tár elektronikus jelentéskészítési (ER) konfigurációinak megosztása külső szervezetekkel.

[!include [banner](../includes/banner.md)]

A Microsoft Regulatory Configuration Services (RCS) segítségével megoszthatók az elektronikus jelentéskészítési (ER) konfigurációk, majd közzétehetők külső szervezetek számára.

A következő lépések leírják, hogy hogyan oszthatja meg egy RCS-felhasználó egy RCS-példányban konfigurált ER-konfiguráció egy verzióját egy külső szervezettel. Mielőtt teljesítené ezeket az eljárásokat, végre kell hajtania a következő előfeltételeket:

- Nyisson meg egy RCS-példányt.
- Hozzon létre egy aktív konfigurációszolgáltatót. További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.
- Hozzon létre és töltsön fel egy új verziót egy ER-konfigurációból. További információ: [Elektronikus jelentéskészítési (ER) konfiguráció új verziójának létrehozása és feltöltése](rcs-global-repo-upload.md).

Arról is meg kell győződnie, hogy a vállalatnál RCS-környezet van kiépítve.

1. A Pénzügy és műveletek alkalmazásban használja a Szervezet **felügyelete** \> **– Munkaterületek** \> **elektronikus jelentéseit**.
2. Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – Külső konfiguráció** lehetőségre, és kövesse az RCS-környezet létrehozására vonatkozó instrukciókat.

Ha van már RCS-környezet létesítve a vállalat számára, akkor az oldal URL-címével érheti el a bejelentkezési beállítást.

## <a name="verify-the-configuration-that-you-want-to-share"></a>A megosztani kívánt konfiguráció ellenőrzése

Hajtsa végre az alábbi lépéseket, és győződjön meg arról, hogy a megosztani kívánt konfiguráció már fel van töltve a globális tárba.

1. Az **Elektronikus jelentés** munkaterületen válassza ki a **Tárak** lehetőséget a konfigurációszolgáltatój esetében.

    ![Konfigurációszolgáltatók.](media/1_RCS_Repo_for_config_provider.JPG)

2. Válassza ki a **Globális tár** \> **Megnyitás** lehetőséget.
3. Keresse meg a megosztani kívánt konfigurációt. A szűrő mező segítségével tovább szűkítheti a keresés eredményeit. Ha nem találja a konfigurációt a globális tárban, hajtsa végre az [Elektronikus jelentéskészítési (ER) konfiguráció új verziójának létrehozása és feltöltése](rcs-global-repo-upload.md) rész lépéseit.

## <a name="share-er-configurations-with-external-organizations"></a>ER-konfigurációk megosztása külső szervezetekkel

Miután létrehozta a konfigurációt a konfigurációszolgáltatója alatt, a **Globális konfigurációtár** oldalon található **Megosztva a következővel:** gyorslappal megoszthatja azt közvetléenül egy külső szervezettel.

1. Az **Elektronikus jelentés** munkaterületen válassza ki a **Tárak** lehetőséget a konfigurációszolgáltatój esetében.
2. Válassza ki a **Globális tár** \> **Megnyitás** lehetőséget. 
3. Válassza ki a megosztani kívánt konfigurációt.
4. Az **Megosztva a következővel:** gyorslapon válassza a **Szervezet** lehetőséget.

    ![Megosztás gyorslappal.](media/1_RCS_Repo_for_Share_with_org.JPG)

5. A párbeszédpanelen írja be a külső szervezet domainnevét, majd kattintson az **OK** gombra.

    ![Mentse a konfiguráció verzióját a külső szervezet párbeszédpanellel.](media/1_RCS_Repo_for_Share_with_form.JPG)

A konfiguráció megosztásra kerül a külső szervezettel, és a szervezet számára elérhető a globális tárban. Innen importálható a szervezet RCS-példányába vagy annak Pénzügyi és Műveleti alkalmazásaiba.

6. Ha egy külső szervezettel korábban megosztott konfigurációt megosztását vissza szeretné vonni, válassza ki a konfigurációt, majd kattintson a **Megosztás visszavonása** elemre , majd válassza az **OK** gombot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]