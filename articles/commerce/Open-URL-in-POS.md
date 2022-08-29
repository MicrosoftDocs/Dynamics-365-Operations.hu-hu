---
title: URl megnyitása a pénztárban
description: Ez a témakör áttekintést nyújt a termék- és vevőkeresési funkciók javításairól Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.custom: 141393
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: ad82cf1039515e58d1717453ee3fb4e3dafd84fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276427"
---
# <a name="open-url-in-pos"></a>URl megnyitása a pénztárban

[!include [banner](includes/banner.md)]

Ez a témakör azt írja le, hogyan lehet konfigurálni egy GOMBOT a Dynamics 365 Commerce pénztárnál egy URL megnyitásához. Ez a funkció nem igényli a kód testreszabását, és nem-fejlesztői szereppel rendelkező személy által konfigurálható. 

Ez a funkció lehetővé teszi a pénztárban található gombok konfigurálását a gombrácstervező segítségével egy URL megnyitására. Jelenleg ez az alábbi konfigurációkban támogatott:

- Megnyitás új ablakban.
- Megnyitás a pénztáron belül.
- Natív alkalmazás megnyitása.

## <a name="open-in-new-window"></a>Megnyitás új ablakban

Ez a konfiguráció határozza meg, hogy az URL-t új ablakban vagy az alkalmazáson belül nyissa meg. Ha a konfiguráció szerint a rendszer a webes URL-t az alkalmazáson belül nyitja meg, az oldalsó navigációs panel és a pénztár felső sor látható, és végezhetők rajta felhasználói interakciók. Ha a konfiguráció szerint a rendszer egy új ablakban nyissa meg, az URL egy új alkalmazásablakban nyílik meg a Modern POS for Windows alkalmazásban, és új böngészőlapon minden más pénztárkliens esetén. A funkció engedélyezéséhez az URL-t konfigurálnia kell úgy, hogy a **Megnyitás új lapon** beállítás ki van választva.

## <a name="open-within-pos"></a>Megnyitás a pénztáron belül

A webes URL pénztáron belül való megnyitása jelenleg csak a Modern POS on Windows szolgáltatásban támogatott. A többi kliensen ez a lehetőség még fejlesztés alatt áll, és a jövőbeni frissítésekben tervezzük kiadni. A funkció engedélyezéséhez az URL-t konfigurálnia kell úgy, hogy a **Megnyitás új lapon** beállítás nincs kiválasztva.

## <a name="open-a-native-app"></a>Natív alkalmazás megnyitása

Ez a funkció lehetővé teszi, hogy meghatározzon olyan nem webes URL-ket, amelyek natív alkalmazást nyitnak meg. Például megadhat olyan URL-protokollokat, mint a MailTo, SIP, IM, vagy MSTEAMS, amelyeket a fogadó eszközön a megfelelő natív alkalmazással lehet kezelni. A funkció engedélyezéséhez az URL-t konfigurálnia kell úgy, hogy a **Megnyitás új lapon** beállítás ki van választva.

- Windows rendszert futtató számítógépekkel kapcsolatban tekintse át az [Exportálás vagy Importálás alapértelmezett alkalmazástársításai](/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) lehetőséget az alapértelmezett protokolltársítások kiválasztásához, ha a Telepítési lemezképek karbantartása és kezelése (DISM) rendszer használatával állítja be számítógépét.
- Ha MDM-et használ, mint például Intune-t a Windows számítógépei kezeléséhez, tekintse át az [Irányelv CSP - ApplicationDefaults](/windows/client-management/mdm/policy-csp-applicationdefaults) részt.
- Ha Ön fejlesztő, aki egyedi webhelyet épít, tekintse át az [Alapértelmezett alkalmazás indítása URI-hoz](/windows/uwp/launch-resume/launch-default-app) részt.

## <a name="open-a-native-app-seamlessly"></a>Natív alkalmazás zökkenőmentes megnyitása

A Windows, iOS és Android rendszerek lehetővé teszi az alkalmazások zökkenőmentesebb megnyitását, az alkalmazás-protokoll társítás alapján. Ha az alkalmazás még nincs beállítva, hogy kezelni tudja a webes böngészőből való megnyitást, akkor előfordulhat, hogy szüksége van egy fejlesztőre, aki ezt konfigurálja.

- Windows esetén tekintse át az: [Alkalmazások engedélyezése alkalmazás URI-kezelőket használó webhelyeknek](/windows/uwp/launch-resume/web-to-app-linking) részt.
- iOS esetén tekintse át az: [Univerzális hivatkozások fejlesztőknek](https://developer.apple.com/ios/universal-links/)részt.
- Az Android esetén tekintse át [Az Android alkalmazáshivatkozások kezelése](https://developer.android.com/training/app-links/) részt.

| Ügyfél                | Megnyitás új ablakban | Natív alkalmazás megnyitása | Megnyitás a pénztáron belül | Részletek                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| Modern POS Windows rendszeren | ✓\*                | ✓               | ✓              | \* Új Modern POS ablakban nyílik meg |
| Felhő pénztár             | ✓\*                | ✓               | X              | \* Új böngészőlapon nyílik meg        |
| Modern POS iOS rendszeren     | ✓\*                | ✓               | X              | \* Új böngészőlapon nyílik meg        |
| Modern POS Android rendszeren | ✓\*                | ✓               | X              | \* Új böngészőlapon nyílik meg        |

## <a name="before-you-begin"></a>Előzetes feladatok

Mielőtt hozzálátna, tekintse át, hogy hogyan lehet konfigurálni a következőt: [Képernyő-elrendezések a pénztár (POS) számára](pos-screen-layouts.md).

## <a name="open-url-in-pos"></a>URl megnyitása a pénztárban

Egy URL cím pénztárban való megnyitásának beállításához kövesse az alábbi lépéseket.

1. A központi irodában lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Képernyő-elrendezések** menüpontra.
2. Válassza a **Gombrácsok \> Tervező** lehetőséget.
3. Hozzon létre egy új gombot.
4. Válassza ki a **Gomb** tulajdonságait.
5. Műveletként válassza az **URL megnyitása** elemet.
6. Adja meg az URL-t, amelyet használni szeretne.
7. Állítsa be, hogy az URL-cím megnyitása új ablakban szeretné-e.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
