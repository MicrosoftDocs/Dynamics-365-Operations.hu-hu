---
title: Dynamics 365 Commerce értékelési környezet áttekintése
description: Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce értékelési környezetről.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c890d7c49b6607ab0cbad536bbf8a3649465a7c1
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193492"
---
# <a name="dynamics-365-commerce-evaluation-environment-overview"></a>Dynamics 365 Commerce értékelési környezet áttekintése

[!include [banner](includes/banner.md)]

Ez a témakör áttekintést nyújt a Microsoft Dynamics 365 Commerce értékelési környezetről.

> [!NOTE]
> A Commerce értékelési környezetek általában nem állnak rendelkezésre, és a partnerek és a vevők számára a kérelem alapján biztosítják. További információért lépjen kapcsolatba Microsoft-partnerének kapcsolattartójával.

A Commerce értékelési környezet egy opcionális, átfogó előzetes verziós környezete a Dynamics 365 Commerce alkalmazásnak, amely lehetővé teszi a partnerek és potenciális vásárlók számára a Commerce termék kipróbálását.

Az értékelési környezetek részben előre be vannak állítva, hogy csökkentsék a szükséges kiépítés utáni lépéseket.

Eltekintve néhány kisebb korlátozástól, amelyek nem befolyásolják a funkciókat és a működést, a Commerce értékelési környezet biztosítja a teljes Commerce-élményt, és az ügyfelek és a megvalósító partnerek felhasználhatják a termék értékeléséhez, visszajelzéshez és illeszkedés-/hiányelemzés elvégzéséhez.

## <a name="limitations-of-the-commerce-evaluation-environment"></a>A Commerce értékelési környezet korlátozásai

Bár a Commerce értékelési környezet teljes körű Commerce szolgáltatásokat és funkciókat kínál, néhány kisebb korlátozást van érvényben:

- Bár a Commerce értékelési környezet önmagában nem rendelkezik földrajzi korlátokkal, a környezet összetevői, például a Retail Cloud Scale Unit (RCSU) és az e-Commerce alkalmazások csak az Egyesült Államokban létesíthetők.
- A Commerce értékelési környezet használata 30 napra korlátozódik az e-Commerce létesítésének napjától számítva.
- A Commerce értékelési környezet csak olyan környezetben telepíthető és inicializálható, amely a demó topológiát használja, ahol a környezet minden összetevője egyetlen, felhőben szolgáltatott virtuális gépen (VM) van telepítve. Ennek a topológiának a fő korlátja a párhuzamos felhasználók száma, amit a környezet támogatni tud.

## <a name="get-started"></a>Első lépések

A Commerce értékelési környezet létesítéséhez lásd: [Commerce értékelési környezet kiépítése](provisioning-guide.md).

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Commerce értékelési környezet kiépítése](provisioning-guide.md)

[Dynamics 365 Commerce értékelési környezet konfigurálása](cpe-post-provisioning.md)

[BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben](cpe-bopis.md)

[Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása](cpe-optional-features.md)

[Dynamics 365 Commerce értékelési környezet GYIK](cpe-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
