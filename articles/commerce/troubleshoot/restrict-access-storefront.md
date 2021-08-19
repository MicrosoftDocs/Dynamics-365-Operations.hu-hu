---
title: Az üzlethez való hozzáférés korlátozása tesztelés vagy fejlesztés során
description: Ez a témakör leírja, hogyan korlátozhatja a hozzáférést a Microsoft Dynamics 365 Commerce-üzlethez belső tesztelés vagy fejlesztés során.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: db3317c01cab2e123f3c2927c359f9e00b98bd8a2d5e851c2c20cb4763db1c49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716783"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a>Az üzlethez való hozzáférés korlátozása tesztelés vagy fejlesztés során

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogyan korlátozhatja a hozzáférést a Microsoft Dynamics 365 Commerce-üzlethez belső tesztelés vagy fejlesztés során.

## <a name="description"></a>Leírás

Belső tesztelés vagy aktív fejlesztés során érdemes korlátozni a webhelyhez való hozzáférést, hogy a külső felhasználók ne férjenek hozzá a közzétett üzletoldalakhoz.

## <a name="resolution"></a>Felbontás

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a>Azure AD B2C beállítása szokásos felhasználói folyamatok használatával

Az Azure Active Directory B2C (Azure AD B2C) rendszer e-kereskedelmi webhelyhez való beállítását lásd: [B2C-bérlő beállítása a Commerce alkalmazásban](../set-up-b2c-tenant.md).

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a>Az üzletoldalak felhasználói elérésének korlátozása és új felhasználók létrehozásának blokkolása

A Commerce webhelyszerkesztőben a következő lépésekkel korlátozhatja a felhasználók hozzáférését az üzletoldalakhoz.

1. Nyissa meg a webhelyét.
1. Válassza ki az **Oldalak** lehetőséget, majd válassza ki azt az oldalt, amelyre korlátozni kell a felhasználói hozzáférést.
1. Válassza ki a modult vagy a részlethelyet, majd válassza a **Szerkesztés** lehetőséget.
1. A tulajdonságok ablaktáblában válassza a **Bejelentkezés szükséges?** jelölőnégyzetet, majd válassza a **Szerkesztés befejezése** lehetőséget.
1. Válassza a **Közzététel** lehetőséget.

A következő lépések szerint tilthatja le új felhasználók létrehozását az Azure AD szolgáltatásban.

1. Lépjen ide: [Azure Portal](https://portal.azure.com/).
1. Válassza ki a webhely elérése érdekében létrehozott Azure AD B2C-alkalmazást.
1. A bal oldali navigációs részben válassza ki a **Felhasználói folyamatok** lehetőséget.
1. A **Felhasználói folyamatok** oldal tetején válassza az **Új felhasználói folyamat** elemet.
1. A **Felhasználói folyamattípus kiválasztása** oldalon válassza az **Előzetes verzió** lehetőséget.
1. A lap középső részén válassza ki a **v2 bejelentkezés** lehetőséget. Ezután a [B2C-bérlő beállítása a Commerce alkalmazásban](../set-up-b2c-tenant.md) fejezet lépéseit követve konfigurálhatja a folyamatot a webhelye általános felhasználói folyamataként az Azure AD B2C számára a tesztelés vagy fejlesztés során.

## <a name="additional-resources"></a>További erőforrások

[B2C-bérlő beállítása a Commerce alkalmazásban](../set-up-b2c-tenant.md)

[Felhasználói bejelentkezéshez használt egyéni oldalak beállítása](../custom-pages-user-logins.md)
