---
title: Az Adventure Works téma telepítése
description: Ez a témakör azt írja le, hogyan lehet telepíteni az Adventure Works témát a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ad704c6c3b95abcfd52e449a0ffbb4b82b236498ae8d2775c4e65811de3ef503
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6763836"
---
# <a name="install-the-adventure-works-theme"></a>Az Adventure Works téma telepítése

[!include [banner](includes/banner.md)]

Ez a témakör azt írja le, hogyan lehet telepíteni az Adventure Works témát a Microsoft Dynamics 365 Commerce alkalmazásban. 

> [!IMPORTANT]
> Az Adventure Works téma és a modulok a Dynamics 365 Commerce 10.0.20-as kiadásában érhetők el. A Microsoft AppSource felületről érhetők el.

## <a name="prerequisites"></a>Előfeltételek

Az Adventure Works téma telepítése előtt szükség van egy olyan Dynamics 365 Commerce környezetre (a Commerce 10.0.20-as vagy újabb verzióra), amely tartalmazza a Retail Cloud Scale Unit (RCSU), Commerce online szoftverfejlesztő készlet (SDK) és a Commerce modulkönyvtár elemeket. A Commerce SDK és a modultár telepítésének lépéseit lásd az [SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md) részben. 

## <a name="installation-steps"></a>A telepítés lépései

### <a name="install-the-adventure-works-theme-in-your-application"></a>Az Adventure Works téma telepítése az alkalmazásba

Az Adventure Works témacsomag a **dynamics365-commerce** feedben szolgáltatásban érhető el **@msdyn365-commerce-theme/adventureworks-theme-kit** néven. Bár az Adventure Works témacsomag része ennek az feednek, egy másik névtér alatt van. Ezért a névtér beállításjegyzék-rekordjainak hozzáadásához ezeket a lépéseket kell követni.

1. Frissítse a **.npmrc** fájlt úgy, hogy a következő beállításjegyzék-rekordot tartalmazza (ha a bejegyzés még nem szerepel):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Frissítse a **.yarnrc** fájlt úgy, hogy a következő beállításjegyzék-rekordot tartalmazza (ha a bejegyzés még nem szerepel):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Ha a csomag telepítéséhez a helyi környezetben, futtassa a következő parancsot a parancssorból. Ez a parancs automatikusan frissíti a package.json fájlt, hogy tartalmazza a függőséget.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit`

A **package.json** fájlban a témaverziót egy adott verzióra kell frissíteni.

> [!IMPORTANT]
> - A témaverziónak meg kell egyeznie a modultár verziójával, hogy minden funkció a várt módon működjön. 
> - A Commerce modultár és az SDK minimális verziója 10.0.20 (9.31) kell legyen. 

### <a name="add-the-font-files-for-the-adventure-works-theme"></a>Az Adventure Works témához használt betűtípusfájlok hozzáadása

Miután az Adventure Works téma telepítve van az alkalmazásban, hozzá kell adni az ahhoz szükséges betűfájlokat. A lépés befejezéséhez másolja az összes betűkészletfájlt a **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\public\webfonts** helyről a partneralkalmazás elérési útjára **\public\webfonts**.

### <a name="set-up-the-resources-for-the-adventure-works-theme"></a>Az Adventure Works témához használt erőforrások beállítása

A következő lépés a téma szükséges alapértelmezett erőforrásának frissítése. Ennek a lépésnek a befejezéséhez másolja a tartalmat a global.json fájlból **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\resources\modules** mappából a partneralkalmazás global.json fájljához az **\src\resources\modules** helyen. Ha a **\src\resources** célkönyvtár nem létezik, akkor teljes egészében átmásolható a **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks** forrákönyvtárból a **\src** célkönyvtárba.

### <a name="pull-updates-and-validate-the-theme"></a>Frissítések lekérése és a téma ellenőrzése

A legújabb SDK- és modultár-frissítések, valamint az egyéb függőségi frissítések lekérésével kapcsolatos további információért tekintse meg az [SDK modultár-frissítések](e-commerce-extensibility/sdk-updates.md#pull-updates) rész „Frissítések” lekérése szakaszát.

A legutóbbi függőségek lekérése után futtathatja a **yarn start** parancsot a csomópont-kiszolgáló fejlesztői környezetben való elindítása és az új Adventure Works-téma tesztelése érdekében. Az alkalmazás helyben való tallózása a `?theme=adventureworks` lekérdezési karakterlánc paraméterének használatával (például `https://localhost:4000/?theme=adventureworks`).

## <a name="additional-resources"></a>További erőforrások

[Adventure works téma](adventure-works-theme.md)

[Modultár áttekintése](starter-kit-overview.md)

[SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
