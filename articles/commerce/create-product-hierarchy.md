---
title: Új termékhierarchia létrehozása
description: Ez a témakör azt ismerteti, hogyan lehet új termékhierarchiát létrehozni a következőben:Microsoft Dynamics 365 Commerce
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 54a29381bb9231766d76b653904339d4bd60c257
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270127"
---
# <a name="create-a-new-product-hierarchy"></a>Új termékhierarchia létrehozása


[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet új termékhierarchiát létrehozni a következőben:Microsoft Dynamics 365 Commerce

## <a name="overview"></a>Áttekintés

A Dynamics 365 Commerce rendszer támogatja a többszörös kiskereskedelmi csatornák használatát. Ezek a kiskereskedelmi csatornák lehetnek online áruházak, hívásközpontok és kiskereskedelmi áruházak (más néven rendes, nem online üzletek). A kiskereskedelmi üzletek csatornái saját fizetési módokkal, árcsoportokkal, (POS) pénztárgépekkel, bevételi és kiadási számlákkal, valamint munkatársakkal rendelkezhetnek. Az összes ilyen elemet be kell állítania, kiskereskedelmi üzlet csatornájának létrehozása előtt. 

A Commerce termékhierarchiája használatos a szervezet kiskereskedelmi termékhierarchiájának létrehozásához. A Commerce termékhierarchiáját használhatja árusítási, árképzési és promóciók, jelentések és a szortiment tervezési használható. Csak egy Commerce termékhierarchia rendelhető hozzá szervezetenként.

## <a name="create-and-configure-a-product-hierarchy"></a>Termékhierarchia létrehozása és konfigurálása

Commerce termékhierarchia létrehozásához és konfigurálásához kövesse ezeket a lépéseket.

1. A navigációs ablaktáblán lépjen ide: **Modulok \> Kiskereskedelmi és kereskedelem \> Termékek és kategóriák \> Commerce termékhierarchia**.
1. Ha még nincs hierarchia, akkor a **Műveleti ablaktáblán** válassza az **Új** lehetőséget a hierarchia gyökerének létrehozásához.
1. Az **Általános** alatt:
    1. A **Név** mezőben adjon meg egy nevet.
    1. Adjon meg egy leírást a **Leírás** mezőben.
    1. A **Rövid neve** mezőbe írjon be egy rövid nevet.
    1. Az **Aktív** elemet állítsa **Igen** értékre.

## <a name="add-hierarchy-nodes"></a>Hierarchia-csomópontok hozzáadása

Hierarchiacsomópontok hozzáadásához kövesse az alábbi lépéseket.

1. A Műveleti ablaktáblában kattintson a **Kategóriahierarchia szerkesztése** elemre.
1. Válassza ki azt a szülőtartomány-csomópontot, amelyhez hozzá szeretné adni az új csomópontot, majd válassza ki az **Új kategória-csomópont** lehetőséget.
1. Az **Általános** szakaszban adja meg a **Név**, **Leírás**, **Rövid név** és **Kulcsszavak** adatokat.
1. Az **Általános** alatt:
    1. A **Név** mezőben adjon meg egy nevet.
    1. Adjon meg egy leírást a **Leírás** mezőben.
    1. A **Rövid neve** mezőbe írjon be egy rövid nevet.
    1. A **Kulcsszavak** mezőbe írja be a megfelelő kulcsszavakat.
    1. A **Megjelenítési sorrend** mezőbe a megjelenítési sorrendet jelölő számot (opcionális).
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. További csomópontok hozzáadásához ismételje meg a fenti lépéseket.

A következő kép bemutatja egy új termékhierarchia-csomópont létrehozását.

![Termékhierarchia létrehozása.](media/create-product-hierarchy.png)

## <a name="other-settings"></a>Egyéb beállítások

A kategória-attribútumok csoportjait igény szerint is hozzá lehet rendelni az egyes csoportokhoz.  

## <a name="additional-resources"></a>További erőforrások

[Commerce-hierarchiák](retail-hierarchies.md)

[Termékkategóriák és termékek kezelése ](category-management-product-creation.md)

[Árusítási entitások rendezési sorrendjének módosítása](custom-order-categories-nav-retail-prod-hierarchy.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
