---
title: Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése
description: Ez a témakör a kötegelt nyomon követésű cikkek továbbfejlesztett kezelését mutatja be a kimutatások feladási folyamata során a Microsoft Dynamics 365 Commerce-ben.
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 513b6ca84fa71e851a5a3e4275e0b6572789e1eb
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485783"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Kötegelt nyomkövetésű cikkek továbbfejlesztett kezelése

[!include [banner](includes/banner.md)]

Ez a témakör a kötegelt nyomon követésű cikkek továbbfejlesztett kezelését mutatja be a kimutatások feladási folyamata során a Microsoft Dynamics 365 Commerce-ben.

A Dynamics 365 Commerce pénztár (POS) alkalmazásban a kötegelt nyomkövetésű cikkek kötegszámai nem rögzíthetők az értékesítés pillanatában. Bizonyos konfigurációk esetén azonban amikor az értékesítéseket a Commerce központban vevői rendeléseken vagy kimutatásfeladáson keresztül adják fel, a Commerce arra számít, hogy a kötegelt nyomkövetésű cikkekhez léteznek érvényes kötegszámok, és ezeket használják majd a számlázási folyamat során.

Ha a termékekhez léteznek érvényes kötegszámok, a rendszer ezeket használja mind a vevői rendelések számlázási folyamata, mind pedig a kimutatásfeladásból származó értékesítési rendelés számlázási folyamata során. Ha a termékekhez nem állnak rendelkezésre érvényes kötegszámok, a vevői rendelés számlázásának feladása nem lehetséges, és a POS-felhasználó hibaüzenetet kap. Ekkor a kimutatás feladása hibaállapotba kerül, még akkor is, ha a termékeknél be van kapcsolva a negatív készlet.

A Commerce fejlesztései segítenek biztosítani, hogy amikor negatív készlet van bekapcsolva a kötegelt nyomon követésű cikkekhez, a vevői rendelés és az értékesítési rendelés kimutatásfeladáson keresztül történő számlázása ne legyen zárolva az adott cikkekhez, ha a készlet 0 (nulla) vagy ha nincs elérhető kötegszám. A továbbfejlesztett funkció alapértelmezett kötegazonosítót használ az értékesítési sorokhoz, ha nem találhatók kötegszámok.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>Határozza meg a vevői rendelésekhez használt alapértelmezett kötegazonosítót

A vevői rendelésekhez használt alapértelmezett kötegazonosító meghatározásához kövesse az alábbi lépéseket.

1. A Commerce központban lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce paraméterek** menüpontra.
1. A **Vevői rendelések** lap **Rendelés** gyorslapján adjon meg egy értéket az **Alapértelmezett kötegazonosító** mezőben.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>Határozza meg az értékesítési rendelések kimutatásfeladáson keresztüli számlázásakor használt alapértelmezett kötegazonosítót

Az értékesítési rendelések kimutatásfeladáson keresztüli számlázásakor használt alapértelmezett kötegazonosító meghatározásához kövesse az alábbi lépéseket.

1. A Commerce központban lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce paraméterek** menüpontra.
1. A **Feladás** lap **Készletfrissítés** gyorslapján adjon meg egy értéket az **Alapértelmezett kötegazonosító** mezőben.

> [!NOTE]
> - Az alapértelmezett kötegazonosító funkció csak akkor áll rendelkezésre, ha a megadott tárolási raktárhoz és cikkekhez engedélyezve van a speciális raktárkezelés. Egy későbbi kiadásban az alapértelmezett kötegazonosító funkció már olyan esetekben is támogatott lesz, ahol nincs engedélyezve a speciális raktárkezelés.
> - A kötegelt nyomkövetésű cikkek továbbfejlesztett kezelésének támogatása a nem speciális raktárkezelési esetek kimutatásfeladása során a Commerce 10.0.5 kiadásában bevezetett funkció.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
