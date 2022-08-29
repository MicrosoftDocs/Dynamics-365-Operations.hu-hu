---
title: Az Adventure Works téma telepítése
description: Ez a témakör azt ismerteti, hogyan lehet telepíteni a Kalandoror munkatéma a következőben:Microsoft Dynamics 365 Commerce
author: anupamar-ms
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: f5c195694633c96a473f0f824c1f182903082bff
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274286"
---
# <a name="install-the-adventure-works-theme"></a>Az Adventure Works téma telepítése

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet telepíteni a Kalandoror munkatéma a következőben:Microsoft Dynamics 365 Commerce 

> [!IMPORTANT]
> Az Adventure Works téma és a modulok a Dynamics 365 Commerce 10.0.20-as kiadásában érhetők el. A Microsoft AppSource felületről érhetők el.

## <a name="prerequisites"></a>Előfeltételek

Az Adventure Works téma telepítése előtt szükség van egy olyan Dynamics 365 Commerce környezetre (a Commerce 10.0.20-as vagy újabb verzióra), amely tartalmazza a Retail Cloud Scale Unit (RCSU), Commerce online szoftverfejlesztő készlet (SDK) és a Commerce modulkönyvtár elemeket. A Commerce SDK és a modultár telepítésével kapcsolatos tudnivalókat lásd [: Fejlesztői környezet beállítása](e-commerce-extensibility/setup-dev-environment.md). 

## <a name="installation-steps"></a>A telepítés lépései

### <a name="install-the-adventure-works-theme-in-your-application"></a>Az Adventure Works téma telepítése az alkalmazásba

Az Adventure Works témacsomag a **dynamics365-commerce** feedben szolgáltatásban érhető el **@msdyn365-commerce-theme/adventureworks-theme-kit** néven. Bár az Adventure Works témacsomag része ennek az feednek, egy másik névtér alatt van. Ezért a névtér beállításjegyzék-rekordjainak hozzáadásához ezeket a lépéseket kell követni.

1. Frissítse a **.npmrc** fájlt úgy, hogy a következő beállításjegyzék-rekordot tartalmazza (ha a bejegyzés még nem szerepel):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Frissítse a **.yarnrc** fájlt úgy, hogy a következő beállításjegyzék-rekordot tartalmazza (ha a bejegyzés még nem szerepel):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Ha a csomagot helyi környezetben kell telepíteni, futtassa a parancsot a parancssorból, `yarn add THEME_PACKAGE@VERSION`**ahol az THEME_PACKAGE** témacsomag (@msdyn365-commerce-téma/kalandor-témacsomag), **és a VERZIÓ** a modultár használt verziója. Fontos, hogy a témacsomag és a modultár verziói megegyeznek. A megfelelő modultár-verziószám megkereséhez nyissa meg a package.json **·** **fájlt, és keresse meg az indulócsomag értékét a függőségek szakaszban**. A következő példában a package.json fájl a modultár 9.32-es Dynamics 365 Commerce verzióját használja, amely a 10.0.22-es verzióra mutat.  

```json
"dependencies": {
    "@msdyn365-commerce-modules/starter-pack": "9.32",
}
```

A következő példa bemutatja, hogyan lehet futtatni a `yarn add` Kalandoror téma 9.32-es verziójának hozzáadására parancsokat. A parancs automatikusan frissíti a package.json fájlt, hogy tartalmazza a függőséget.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit@9.32`

A modultár verziójának frissítésével kapcsolatos további tudnivalókat lásd az [SDK és a modultár frissítéseit](e-commerce-extensibility/sdk-updates.md). 

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
