---
ms.openlocfilehash: 22911afd3a3da0ce3bcaeb7e42ab0096c868be547d559f14a91e09d6e6e12c08
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777064"
---
Adatbázisok környezetek között történő másolásához futtatnia kell a környezetlétesítő eszközt a másolt adatbázis teljes működőképessége előtt annak érdekében, hogy az összes Commerce-összetevő naprakész legyen.

> [!IMPORTANT]
> Javasoljuk, hogy futtassa ezt az eljárást, függetlenül attól, hogy Commerce-összetevőket használ-e vagy sem, mert a Commerce funkció minden környezetben megtalálható. 

Folytatás előtt győződjön meg arról, hogy teljesülnek a következő előfeltételek:
1. Ha a 2017. júliusi kiadást (más néven 7.2) 7.2.11792.56024 frissítésére van szükség, akkor az adatok frissítésének futtatása előtt alkalmazza a következő X++ gyorsjavításokat a célkörnyezetben. Ezek megakadályozhatják, hogy a frissítés során különböző hibák forduljanak elő:

    - KB 4036156 – Retail alverzió frissítése – „A változó számsorozata nincs beállítva.” Ez a javítási csomag a KB 4035399 és a KB 4035751 frissítéseket is tartalmazza. Felhívjuk figyelmét, hogy a csomag használatához legalább Platform Update 9 verzióval kell rendelkeznie. Ha nem biztos benne, telepítse a legfrissebb bináris fájlokat.
    
2. Ha a Microsoft Dynamics AX 2012-es verziót frissíti, akkor az adatfrissítés futtatása előtt a célkörnyezetében telepítse az X++ alkalmazás következő gyorsjavításait:
    - KB 4033183 – A Dynamics AX 2012 R2 vagy a Dynamics AX 2012 R3 Pre-CU8 nem kiskereskedelmi frissítése sikertelen a következő üzenettel: Az objektum nem található a dbo. RETAILTILLLAYOUTZONE esetében.
    - KB 4040692 – a Dynamics AX 2012 R3 Microsoft Dynamics 365 for Operations 7.2-es verzióra történő frissítése sikertelen: a RetailSalesLine duplikált index a SalesLineIdxen.
    - KB 4035490 – Teljesítménnyel kapcsolatos problémák a GeneralJournalAccountEntry MainAccount mezőfrissítési parancsfájl esetén.


A környezet-újralétesítési eszköz futtatásához kövesse az alábbi lépéseket.

1. A Közös eszköz könyvtárban válassza ki **Telepíthető szoftvercsomag** lehetőséget.
2. Töltse le a környezet-újralétesítési eszközt.
3. A projekt eszközkönyvtárában válassza ki **Telepíthető szoftvercsomag** lehetőséget.
4. Válassza ki az **Új** lehetőséget egy új csomag létrehozásához.
5. Írja be a csomag nevét és a leírását. A csomag neveként a **Környezet-újralétesítési eszköz** nevet használhatja.
6. Töltse fel a korábban letöltött csomagot.
7. A célkörnyezete **Környezet részletes adatai** lapján válassza a **Karbantartás** > **Frissítések alkalmazása** lehetőséget.
8. Válassza ki a korábban feltöltött környezet-újralétesítési eszközt, majd válassza az **Alkalmaz** lehetőséget a csomag alkalmazásához.
9. Kövesse nyomon a csomag telepítési folyamatát. 

A telepíthető csomag alkalmazásával kapcsolatos további tudnivalókat lásd: [Telepíthető csomag alkalmazása](../deployment/create-apply-deployable-package.md). A telepíthető csomag manuális alkalmazásával kapcsolatos további tudnivalókat lásd: [Telepíthető csomag telepítése](../deployment/install-deployable-package.md).
