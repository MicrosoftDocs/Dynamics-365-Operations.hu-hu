---
title: Dynamics 365 Commerce előzetes verziós környezet áttekintése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce előzetes verziós alkalmazásról.
author: v-chgri
manager: annbe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1ff96aeb5963df9ddee56783a089dad129bbb71c
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024683"
---
# <a name="dynamics-365-commerce-preview-environment-overview"></a>Dynamics 365 Commerce előzetes verziós környezet áttekintése


[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce előzetes verziós alkalmazásról.

## <a name="overview"></a>Áttekintés

A Commerce előzetes verziós környezet egy opcionális, átfogó előzetes verziós környezete a Dynamics 365 Commerce alkalmazásnak, amely lehetővé teszi a potenciális vásárlók számára a Commerce termék kipróbálását, mielőtt a nyilvánosság számára megjelenne.

Eltekintve néhány kisebb korlátozástól, amelyek nem befolyásolják a funkciókat és a működést, a Commerce előzetes verziós környezet biztosítja a teljes Commerce-élményt, és az ügyfelek és a megvalósító partnerek felhasználhatják a termék értékeléséhez, visszajelzéshez és illeszkedés-/hiányelemzés elvégzéséhez.

## <a name="limitations-of-the-commerce-preview-environment"></a>A Commerce előzetes verziós környezet korlátozásai

Bár a Commerce előzetes verziós környezet teljes körű Commerce szolgáltatásokat és funkciókat kínál, néhány kisebb korlátozást van érvényben:

- Bár a Commerce előzetes verziós környezet önmagában nem rendelkezik földrajzi korlátokkal, a környezet összetevői, például a Retail Cloud Scale Unit (RCSU) és az e-Commerce alkalmazások csak az Egyesült Államokban létesíthetők.
- A Commerce előzetes verziós környezet használata 30 napra korlátozódik az e-Commerce létesítésének napjától számítva.
- A Commerce előzetes verziós környezet csak olyan környezetben telepíthető és inicializálható, amely a demo topológiát használja, ahol a környezet minden összetevője egyetlen virtuális gépen (VM) van telepítve. Ennek a OneBox VM topológiának a fő korlátja a párhuzamos felhasználók száma, amit az előnézeti környezet támogatni tud.
- A Commerce előzetes verziós környezet csak a Commerce termék általános elérhetőségéig (GA) értékelhető. A GA után új demo környezetek lesznek elérhetők.

## <a name="get-started"></a>Első lépések

A Commerce előzetes verziós környezet létesítéséhez lásd: [Commerce előzetes verziós környezet kiépítése](provisioning-guide.md).

## <a name="additional-resources"></a>További erőforrások

[Egy Dynamics 365 Commerce előnézeti környezet létesítése](provisioning-guide.md)

[Dynamics 365 Commerce előzetes verziós környezet konfigurálása](cpe-post-provisioning.md)

[A Dynamics 365 Commerce előzetes verziós környezet választható funkcióinak konfigurálása](cpe-optional-features.md)

[Dynamics 365 Commerce előzetes verziós környezet GYIK](cpe-faq.md)
