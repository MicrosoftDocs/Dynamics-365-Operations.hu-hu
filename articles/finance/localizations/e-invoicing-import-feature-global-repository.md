---
title: Funkciók importálása a globális tárházból
description: Ez a cikk bemutatja, hogy hogyan importálhat globalizációs funkciókat a globális tárházból.
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 5a72673e17c5653d43b60d3348d5518e09c40a15
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278311"
---
# <a name="import-features-from-the-global-repository"></a>Funkciók importálása a globális tárházból

[!include [banner](../includes/banner.md)]

A globális tárház a konfigurációs szolgáltatóval megosztott elektronikus számlázási funkciókat tartalmazza. A Microsoft által biztosított összes elektronikus számlázási funkció meg van osztva az összes vállalattal. Automatikusan hozzáfér minden olyan elektronikus számlázási funkcióhoz, amely a Microsoft által közzétett és közzétett a globális tárházban.

Ha elindítani a konfigurációs szolgáltatóval megosztott elektronikus számlázási funkciókat, importálja azokat a globális tárházból az RcS (Regulatory Configuration Service) saját példányába. Ezután tekintse át a funkció részleteit, például az Elektronikus jelentés (ER) konfigurációit és a feldolgozási csővezetékeket.

## <a name="import-a-feature-from-the-global-repository"></a>Funkció importálása a globális adattárból

1. Jelentkezzen be a RCS-fiókba.
2. A **Globalizációs funkció** munkaterületen a **Funkciók** szakaszban válassza ki az **Elektronikus számlázás** csempét.
3. Az **Importálás lehetőség** kiválasztásával megnyithatja **az Importálás szolgáltatást a globális tárház-keresésből**.
4. Ha tallózással szeretne böngészni a globális tárház egy adott konfigurációszolgáltató számára elérhető elektronikus számlázási funkciói között, a Szinkronizálás lehetőség választásával szinkronizálja a szervezet RCS-példányát **·**. A szinkronizálás befejezése után az elérhető elektronikus számlázási funkciók listája a globális tárházról frissül. Ez a frissítés eltarthat néhány percig.
5. Válassza ki az importálni kívánt szolgáltatást, majd válassza az Importálás **lehetőséget**.

Az importált elektronikus számlázás funkció megtekintéséhez győződjön meg arról, hogy a megfelelő konfigurációs szolgáltató van kiválasztva. Alapértelmezés szerint az aktív konfigurációs szolgáltató által létrehozott funkciókat automatikusan kiszűri a rendszer. A szűrő módosításával megtekintheti más szolgáltatók, például a Microsoft konfigurációs szolgáltató által létrehozott funkciókat.

Mostantól dolgozhat az importált funkcióval. Az importált funkció sablonként való használatával áttekintheti a részleteket, és új funkciókat hozhat létre.

> [!NOTE]
> A funkciók csak akkor módosíthatók, ha az aktuálisan aktív konfigurációs szolgáltató hozta létre. Az új funkciók az eredeti funkció alapként való használatával hozhatók létre. Ezután meg lehet adni a szükséges módosításokat, vagy be lehet állítani a paramétereket.

Ha a Microsoft vagy egy másik vállalat, amely a globalizációs funkciókat és az importált vállalat funkcióit részvénykedi, **·** **·** **a** Globalizációs funkciók munkaterületének Kapcsolódó beállítások szakaszában található Funkciófrissítések ellenőrzése beállításával ellenőrizheti a frissített verziókat.

Ha azt látja, hogy a sablonként használt funkciók frissítései vannak, akkor új verziót is importálhat, miután szinkronizálta a globális tárházban közzétett funkciók listáját.
