---
title: Konzisztens szállítási mód kezelésének engedélyezése az e-kereskedelmi csatornákban
description: Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce lehet a egységes szállítási módkezelést engedélyezni az e-commerce csatornák költségáramlásával kapcsolatos lehetséges problémák kezelésére.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: f32f1915f8f7de1d5536b69b05bc74c6149dfda6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885585"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Konzisztens szállítási mód kezelésének engedélyezése az e-kereskedelmi csatornákban 

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan Microsoft Dynamics 365 Commerce lehet a egységes szállítási módkezelést engedélyezni az e-commerce csatornák költségáramlásával kapcsolatos lehetséges problémák kezelésére.

Az Dynamics 365 Commerce e-commerce csatornák alapértelmezés szerint nem alkalmaznak nem csak a nem csak a fejléc szintű költségeket. Ez a viselkedés az e-commerce csatornákon a következő problémák egyikét vagy mindkettőt okozhatja:

- A nem csak a fejléc szintű költségek nem jelennek meg.
- A szállítási módok díjai nem konzisztensek a szállítási mód kiválasztása és a pénztári rendelés összegzése között.

A problémák megoldásához **be kell kapcsolnia a egységes szállításimód-kezelési módot a csatorna funkcióban**. Ez a funkció gondoskodik arról, hogy a nem időzített fejléc szintű költségek megjelenjenek az e-commerce csatornákban, és hogy az értékesítési rendelések szállítási adatait ugyanazok a kérési munkafolyamatok egységesen kezelik.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>A egységes szállításimód-kezelés engedélyezése a csatorna funkcióban

A Commerce **Headquarters csatorna funkció konzisztens szállításimód-kezelésének** engedélyezéséhez kövesse ezeket a lépéseket.

1. Nyissa meg **a Szolgáltatáskezelés munkaterületét** (**Rendszerfelügyeleti \> munkaterületek \> funkciókezelése**).
1. Az elérhető funkciók listájában keresse meg és **válassza a Egységes szállításimód-kezelés engedélyezése a csatornában lehetőséget**.
1. A jobb oldali ablakban válassza az Engedélyezés **lehetőséget**.
