---
title: Regulatory Configuration Service (RCS) – RCS-környezet törlése
description: Ez a témakör bemutatja, hogy a Regulatory Configuration Service (RCS) rendszegazdái hogyan törölhetik az RCS-környezeteket és a kapcsolódó adatokat.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: cf82abbe5493eac9665323738441fa016205e9ef
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355007"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Regulatory Configuration Service (RCS) – RCS-környezet törlése

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogy a Regulatory Configuration Service (RCS) rendszegazdái hogyan törölhetik az RCS-környezeteket és a kapcsolódó adatokat.

A témakörben ismertetett eljárás használatához a következő előfeltételeknek kell megfelelni:

- Az RCS-környezethez **adminisztrátori** szerepkörrel kell rendelkeznie.
- Az **adminisztrátor** szerepkörhöz **RCSDeleteEnvironmentDuty** szerepkört kell hozzárendelni.

## <a name="delete-an-rcs-environment"></a>RCS-környezet frissítése

1. Nyissa meg az RCS-t, és válassza ki az **Elektronikus jelentéskészítés** munkaterület csempéjét.
2. A **Kapcsolódó hivatkozások** szakaszban válassza az **RCS-környezet törlése** elemet.

    ![Az RCS-környezet törlése hivatkozás a Kapcsolódó hivatkozások szakaszban.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. A megjelenő párbeszédpanelen ellenőrizze a környezet törlésének hatókörével kapcsolatos üzeneteket.

    ![Az RCS-környezet törlése párbeszédpanelen megjelenő üzenetek.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > Az RCS-környezetek törlése nem vonható vissza.
    >
    > A művelet törli a kiválasztott RCS-környezetet és a hozzá kapcsolódó adatokat, például a globális adattárban tárolt funkciókat és konfigurációkat. A más szervezetekkel megosztott funkciók és konfigurációk megosztása megszűnik, és az elemek törlődnek, ha nincs függőségük. A függőséggel rendelkező funkciókat és konfigurációkat megszüntetettként jelöli meg a rendszer.

4. A megadott mezőben adja meg az RCS-környezet globálisan egyedi azonosítóját (GUID), és erősítse meg, hogy törölni szeretné a környezetet. A környezet GUID azonosítója a törlési üzenetben található.
5. Válassza a **Környezet törlése** lehetőséget.
    
Ezzel törli az RCS-környezetet és a hozzá kapcsolódó adatokat.

> [!IMPORTANT]
> Az RCS-környezet törlése után nem lehet visszaállítani az adatokat. Új RCS-környezet bármelyik elérhető RCS-régióban létrehozható.
