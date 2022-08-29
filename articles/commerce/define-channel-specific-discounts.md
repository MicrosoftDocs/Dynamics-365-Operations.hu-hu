---
title: Csatornaspecifikus engedmények definiálása
description: A kiskereskedők gyakran különböző engedményeket állítanak be a különböző csatornákon. Ez a cikk áttekinti az egyes csatornák engedményének létrehozásához szükséges fogalmakat.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.industry: Retail
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
ms.openlocfilehash: f426503a6897a73010b77082f4277b65545bfcc3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273554"
---
# <a name="define-channel-specific-discounts"></a>Csatornaspecifikus engedmények definiálása

[!include [banner](includes/banner.md)]

Ez a cikk áttekinti az egyes csatornák engedményének létrehozásához szükséges fogalmakat.

## <a name="channel-specific-discounts"></a>Csatornaspecifikus engedmények

A kiskereskedők gyakran különböző engedményeket ajánlanak a különböző csatornákon. Ezt tehetik a helyi piaci feltétetelek kezelése vagy a versenytárs kiskereskedők legyőzése érdekében.

A Commerce árcsoportok segítségével definiálja a csatornaspecifikus engedményeket. Az árcsoportok a következő entitások egy vagy több lehetőségéhez rendelhetők hozzá: csatornák, katalógusok, fiókok és hűségprogramok. A cikk a csatornákat tárgyalja, de az azonos koncepciók a katalógus engedményekre, fiók engedményekre és a hűséges engedményekre vonatkoznak.

## <a name="price-groups"></a>Árcsoportok

[![Árcsoportok.](./media/price-groups-1024x608.png)](./media/price-groups.png)

A fenti ábra bemutatja a tranzakciókban megtalálható (csatorna, katalógus, fiók, vevő, hűségkártya) entitások és a különféle konfigurálható engedménytípusok közötti kapcsolatot. Az összes tranzakció egy csatornában fordul elő, így a csatorna garantáltan rajta van egy tranzakción. A fennmaradó entitások megadása nem kötelező. Minden egyes alapadat lapon van egy hivatkozás a kapcsolódó árcsoportok lapjához, ahol megtekintheti az árcsoportokat és szükség szerint hozzá is adhat árcsoportokat. Az árcsoportok segítségével az entitások négy különböző típusát kapcsolják össze az engedményekkel, az ármódosításokkal és kereskedelmi megállapodásokkal. Azt ajánljuk, hogy tervezzen meg egy stratégiát, hogyan fogja az árcsoportjait elnevezni annak érdekében, hogy rendben tartsa őket. Például egy betű- vagy számelőtag vagy -utótag segítségével megkülönböztet különféle típusokat. Például 1-xxxxx a csatornaárcsoportok és 2-xxxxx a katalógusárcsoportok számára. Négy lekérdezési oldal van, amely valamennyi engedményekhez rendelt kereskedelmi entitásra fókuszál.

- **Csatorna csatorna árcsoportjai** – Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és csatornák listáját.
- **Katalógus árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és katalógusok listáját.
- **Hűség árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és hűségprogramok listáját.
- **Fiók árcsoportjai**– Ez a lap megjeleníti a minden egyes árcsoporthoz kapcsolódó engedmények és fiókok listáját.

## <a name="example-channel-discount-set-up"></a>Csatorna kedvezmény beállítás példája

A következő példa bemutatja egy csatorna engedmény beállításába bevont feladatokat.

1. Ebben a példában egy úgynevezett **Houston** csatornával rendelkezik, és egy **Vissza az iskolába** nevezett új engedményt fog létrehozni.
2. Mivel az árképzés és az engedmény stratégia csatorna engedmények lehetőségét tartalmazza, mindig létrehoz csatornaspecifikus árcsoportot egy csatorna létrehozásakor.
3. **Houston-PG** árcsoporttal rendelkezik és ez hozzá van rendelve a **Houston** csatornához.
4. Miután létrehozta az új **Vissza az iskolába** engedményt, akkor kattintson **Árcsoportok** az **Engedmény** lap tetején. Az **Árcsoportok engedménye engedmény** oldal jelenik meg. Ezután kattintson **Új** , és válassza ki a **Houston-PG** árcsoportot.
5. Ezután engedélyezheti a kedvezményt és űthelyezheti a csatornába.

## <a name="additional-resources"></a>További erőforrások

[Ármódosítások és engedmények](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
