---
title: Csatorna konfigurálása csatorna navigációs hierarchiájának használatára
description: Ez a témakör azt mutatja be, hogyan lehet konfigurálni egy csatornát a csatorna navigációs hierarchiájának használatára a Microsoft Dynamics 365 Commerce alkalmazásban.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3cf29bd423a2475b77e9076024b4da6864a31065da81de49f1b9a0f639243f1d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713992"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a>Csatorna konfigurálása csatorna navigációs hierarchiájának használatára


[!include [banner](includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet konfigurálni egy csatornát a csatorna navigációs hierarchiájának használatára a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A csatornanavigációs hierarchiák kategóriákba rendezik a termékeket, így a termékek böngészhetők az e-kereskedelmi helyeken webhelyeken vagy az pénztárakban (POS). A Kiskereskedelmi és online csatornákat csatornanavigációs hierarchiákkal kell konfigurálni.

## <a name="configure-the-channel"></a>A csatorna konfigurálása

Egy csatorna navigációs hierarchia használatára vonatkozó konfigurálásához kövesse az alábbi lépéseket.

1. A navigációs ablaktáblán ugorjon a **Modulok \> Kiskereskedelem és kereskedelem \> Csatornabeállítás \> Csatornakategóriák és termékattribútumok** lehetőségre.
1. Válassza ki a konfigurálni kívánt csatornát.
1. Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.
1. A **Kategóriahierarchia** legördülő listában válassza ki a megfelelő csatornanavigációs hierarchiát.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Az **Attribútum csoportban** adja meg azokat az attribútum-csoportokat, amelyek az összes csomópont globális attribútumai lesznek.

A következő kép bemutatja egy csatorna konfigurálását csatorna navigációs hierarchia használatára.

![Példa csatorna konfigurálására.](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a>Attribútum-metaadatok beállítása

Az attribútum metaadatainak beállítása lehetővé teszi az egyes csomópontok attribútumainak konfigurálását.

Az attribútum-metaadatok beállításához hajtsa végre az alábbi lépéseket.

1. Válassza a műveleti ablakban az **Attribútum-metaadatok beállítása** lehetőséget.
1. Mindegyik csomóponthoz válassz a **Csatorna termékattribútumai** lehetőséget.
1. Az **Attribútum megjelenítése a csatornán** lehetőséget állítsa be **Igen** értékre, és a **Finomítható** elemet is **Igen** értékre, ha engedélyezni szeretné a finomítókat a csatornán.
1. A csomópontok kívánt beállításainak konfigurálása után a **Művelet** ablaktáblában válassza a **Mentés** gombot a mentéshez.
1. Válassza ki a jobb felső sarokban látható **X** szimbólumot, ha a képernyőt a visszalépéshez a **Csatornakategóriák és termékattribútumok** lapra.

A következő képen látható csatorna termékattribútumok halmazának példája, amelyek konfigurálva vannak egy csatornakategória-csomóponton.

![Csatornaattribútumok egy csatornakategória-csomóponton.](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a>Változások közzététele

A változtatások életbe lépéséhez közzé kell tennie a változtatásokat.

A változatások közzétételéhez kövesse az alábbi lépéseket.

1. A műveleti ablaktáblán válassza a **Csatorna frissítéseinek közzététele** elemet.
1. A **Csatorna frissítéseinek közzététele** ablaktáblán válassza az **OK** lehetőséget.

A következő képen a csatornák frissítéseinek közzétételének módja látható.

![Csatornafrissítések közzététele.](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a>További erőforrások

[Csatorna navigációs hierarchiájának létrehozása](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]