---
title: Cím hozzáadása szolgáltatási rendeléshez
description: Ez a témakör azt ismerteti, hogyan lehet vevői címet hozzáadni egy szervizrendeléshez.
author: sorenva
ms.date: 06/15/2020
ms.topic: article
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c485c50bab7c2e945aa0f0fc0601008dcebd3328
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015725"
---
# <a name="add-an-address-to-a-service-order"></a>Cím hozzáadása szolgáltatási rendeléshez

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet vevői címet hozzáadni egy szervizrendeléshez. A szervizrendelések létrehozásakor abból a projektből veszi át a program a címadatokat, amelyhez a szervizrendelés csatolva van. Azonban kiválaszthat egy másodlagos helyet azon címek közül, amelyek már szerepelnek a Microsoft Dynamics AX rendszerben vevők, szállítók, helyek, raktár, szolgáltatási rendelések és projektek esetén.

Létre is hozhat új címeket. Alapértelmezés szerint az új cím átkerül a projekthez. Azonban megadhatja, hogy az új címnek csak a szolgáltatás jelenlegi példánya esetén van jelentősége. Ebben az esetben az új cím nem kerül át a projekthez.

## <a name="create-a-customer-address-for-a-service-order"></a>Vevő cím létrehozása egy szervizrendeléshez

Egy cím hozzáadásához a szervizrendeléshez, tegye a következőket:

1. Ugrás a Szolgáltatáskezelés **szervizrendelések** \> **szervizrendeléséhez** \> **·**

1. Nyissa meg azt a szervizrendelést, amelyhez címet szeretne létrehozni.

1. Nyissa meg a **Fejléc** lapot.

1. Bontsa ki **a** Cím gyorstáblát, majd válassza a Cím **hozzáadása** gombra a Gyorspult eszköztáron.

1. Adja meg **a cím egyedi** nevét az Új cím párbeszédpanelen, és töltse ki a többi mezőt. 

    > [!WARNING]
    > Ha egy létező cím nevével megegyező nevet ad meg, akkor a többi mezőbe beírt adatok felülírják a már meglévő címhez tartozó adatokat.

1. Az **új cím szervizrendelésbe való másolása az OK** gombra való másoláshoz.

## <a name="specify-an-alternative-address-on-a-service-order"></a>Másodlagos cím megadása egy szervizrendelésen

Egy másodlagos cím hozzáadásához a szervizrendeléshez, tegye a következőket:

1. Ugrás a Szolgáltatáskezelés **szervizrendelések** \> **szervizrendeléséhez** \> **·**

1. Nyissa meg azt a szervizrendelést, amelyhez másodlagos címet szeretne megadni.

1. Nyissa meg a **Fejléc** lapot.

1. Bontsa ki **a** Cím gyorstáblát, majd válassza az **Eszköztár** Egyéb címét.

1. A Címválasztás **párbeszédpanelen** válassza **ki** a Szervizrendeléseket a lap fölötti legördülő listából.

1. Válasszon ki egy címet, majd a **szervizrendelésbe való másoláshoz kattintson az OK** gombra.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]