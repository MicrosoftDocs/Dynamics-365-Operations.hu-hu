---
title: Store Commerce alkalmazás mobil platformokhoz
description: Ez a témakör azt ismerteti, hogyan lehet Microsoft Dynamics 365 Commerce első lépésekben használni a Store Commerce alkalmazást az Android iOS-hez és a for iOS-hez.
author: stuharg
ms.date: 11/30/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2018-10-29
ms.openlocfilehash: dc952698a2a3301aff312e8310c58cbbb9cfe290
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815783"
---
# <a name="store-commerce-app-for-mobile-platforms"></a>Store Commerce alkalmazás mobil platformokhoz

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a cikk azt ismerteti, hogyan lehet első lépésekben Microsoft Dynamics 365 Commerce használni a Store Commerce alkalmazásokat az Android iOS-hez és az iOS-hez.

A Dynamics 365 Commerce for és Android az iOS mobilalkalmazások segítségével egyszerűen és egyértelművé tehetővé teszik a kiskereskedelmi környezetben használható teljes értékű mobil pénztári eszközök (POS- és pénztári eszközök) telepítését. A Store Commerce mobilalkalmazások [minden képességet és képességeit kihoznak a Windows Commerce](store-commerce.md) alkalmazásból, és jól teljesítenek az iOS Android - és telefon- és táblagépek széles skáláján. A Store Commerce mobilalkalmazások közvetlenül a Márt és a Sbaba alkalmazástárból is telepíthetők, és nincs szükség arra, hogy a fejlesztők új alkalmazáscsomagot hozzanak létre a telepítéshez vagy frissítéshez. 

A Store Commerce mobilalkalmazások teljes működési paritást megőriznek az aktuális Retail kiskereskedelmi alkalmazásokkal. A Store Commerce for iOS emellett egy külön hardverállomást is támogat, így az iOS-eszközök kommunikálhatnak a hálózati fizetési terminálokkal, a nyugtanyomtatókkal és a pénztárfiókokkal, anélkül, hogy megosztott hardverállomást telepíteének. 

> [!IMPORTANT]
> A Windows Áruház Commerce-alkalmazásai és Android  az iOS a következő generáló POS-alkalmazások Dynamics 365 Commerce. A Store Commerce-alkalmazások számos fejlesztést kínálnak az előző tevékenységeikhez képest, miközben megőrzik a teljes működési és funkció paritását. A Microsoft 2023 végén elavulta az MPOS-t Android és az iOS Retail POS-alkalmazásokat, és javasolja, hogy minden új POS-telepítéshez a Store Commerce vagy a Cloud POS (CPOS) alkalmazást használja. A meglévő vevőknek azt tervezik, hogy a Retail alkalmazásból a Store Commerce alkalmazásba áttelepítéseik. A további tudnivalókat lásd [a Modern POS áttelepítése a Store Commerce alkalmazásba](pos-extension/migrate-mpos-store-commerce.md). 

## <a name="app-architecture"></a>Alkalmazásarchitektúra

A Store Commerce mobilalkalmazások ugyanazt a topológiát használják, mint a Store Commerce for Windows-alkalmazás, amikor telepítik a módban. A Store Commerce mobilalkalmazások olyan shell-alkalmazások, amelyek közvetlenül a Commerce Scale Unit (STB) segítségével teszik elérhetővá a CPOS adatokat, és a KÖZPONTI COMMERCE és Commerce Headquarters alkalmazáson keresztül csatlakoznak a HEADless Commerce és Commerce headquarters alkalmazáshoz. A shell alkalmazásmodell lehetővé teszi a Store Commerce-alkalmazások számára egy külön hardverállomás közvetlen integrációját a fizetési terminállal, nyomtatóval, pénztárfiókkal és egyéb perifériás szolgáltatásokkal. Nem kell beállítani megosztott hardverállomást a hardvereszközök használatára. 

A Store Commerce mobilalkalmazás frissítéséhez frissítse a BELIT-t. Az alkalmazás minden új POS-funkciót és funkciót automatikusan felvett. Az STB frissítését a Commerce [Scale Unit (felhő) frissítéseit és bővítéseit lásd a Frissítések és bővítmények alkalmazása a Commerce Scale Unit (felhő) alkalmazásában](../../fin-ops-core/dev-itpro/deployment/update-retail-channel.md).

A shell-alkalmazások szolgáltatása az alkalmazás-áruház frissítéseit használja. Amikor egy alverzió eléri az általános elérhetőségi adatokat, a Microsoft közzéteszi azt az alkalmazás-áruházakban. A Microsoft az alverziófrissítések között javításokat is közzétehet a sürgős hibajavítások kiadása érdekében.

## <a name="prerequisites"></a>Előfeltételek

A Store Commerce mobilalkalmazások megkövetelik Dynamics 365 Commerce, különösen a Commerce Headquarters és a FOGJA összetevőit. Az alábbi táblázat felsorolja azokat a minimális operációs rendszer-verziókat és STB-verziókat Android , amelyekre szükség van az és az iOS mobilalkalmazások számára. 

| Előfeltételek | Android      | iOS  |
| ------------ | ------------ | ---- |
| Operációs rendszer verziója   | 7.0          | 15.0 |
| CSU-verzió  | 9.38.22266.8 | Később elvégzendő  |

## <a name="install-the-app"></a>Az alkalmazás telepítése

A Store Commerce mobilalkalmazásokat közvetlenül a Egész Store áruházból vagy App Store-ból lehet telepíteni. 

- [A Store Commerce alkalmazás a Android](https://aka.ms/storecommerceandroid)
- [Store Commerce alkalmazás az iOS-hez](https://aka.ms/storecommerceios)

Az Android app (.apk) és a App app (.ipa) Microsoft Dynamics csomagok a Lifecycle Services megosztott eszköztárából is letölthetők. 

## <a name="device-and-register-setup"></a>Eszköz és pénztárgép beállítása

A Pénztárgépeket csak akkor aktiválhatja a Store Commerce mobilalkalmazásokban, ha beállít egy eszközt és egy pénztárgépet a Commerce Headquarters alkalmazásban. További információ az Eszközök és jegyzékek [oldalon található](../implementation-considerations-devices.md). 

### <a name="device-setup"></a>Eszköz beállítása

Az alábbi lépések szerint hozhatja létre és állíthatja be az új eszközt.

1. A Commerce Headquarters beállítási eszközeit a **Retail and Commerce \> Channel setup \> POS rendszerében lehet \> beállítani**. 
1. Hozzon létre egy új eszközt, **és a telepített mobilalkalmazástól függően válassza a Modern POS - Android**  **vagy a Modern POS - iOS** típust. 

    > [!NOTE] 
    > A **Modern POS - Android**  és **Modern POS - iOS alkalmazástípusok az aktuális szoftveralkalmazások és iOS-alkalmazások**  Android telepítéséhez is használhatók. Az MPOS rendszer értékcsökkenése után **az ilyen alkalmazástípusok címkéi frissülnek a Store Commerce - Android**  és **a Modern POS - iOS rendszer számára**. 

### <a name="register-setup"></a>Jegyzék beállítása

Létrehozhat új pénztárgépet, és társíthatja a létrehozott eszközhöz, vagy társíthat egy meglévő pénztárgépet az új eszközhöz. A jegyzékekkel kapcsolatos további tudnivalókat lásd [a Pénztárak létrehozása és társítása oldalon](../tasks/create-associate-registers.md).

### <a name="screen-layout-setup"></a>Képernyő-elrendezés beállítása

Ha olyan képernyőelrendezést ad vissza, amely a Dynamics 365 Commerce licenchez mellékelt bemutatóadatok között szerepel, akkor a Store Commerce alkalmazás automatikusan kiválasztja a bele foglalt tömörítési elrendezést, ha az eszköz képernyő-felbontása 480 &times; 853 képpontnál kisebb a álló tájolásban. Ha azonban a képernyőelrendezést az akkretból hozza létre, vagy a mobileszköz nagyobb felbontást használ, mint amit a tömörítéses elrendezés támogat, akkor gondoskodnia kell arról, hogy olyan felbontást és gombrácsokat hozzon létre, amelyek megfelelőek ahhoz a telefonhoz vagy táblagéphez, amelybe telepítve van. A képernyőelrendezés-konfigurációkról a [POS felhasználói felületének vizuális konfigurációiban található további tájékoztatás](../pos-screen-layouts.md). 

Miután konfigurálta az eszközöket és a pénztárgépeket a Commerce Headquartersben, **menjen a Retail and Commerce Retail és Commerce \> ID \> Distribution Schedules** eszközökhöz, és futtassa a pénztárgép-feladatot.

## <a name="activate-a-device"></a>Eszköz aktiválása

A következő lépésekkel lehet aktiválni egy eszközt a Store Commerce mobilalkalmazásban.

1. Nyissa meg az alkalmazást a mobileszközön.
1. Adja meg a CPOS URL-címét, amelyet a környezet részletei oldalon talál a Lifecycle Services szolgáltatásban, **vagy** a Commerce Headquarters Csatornaprofilok lapján (**Retail and Commerce \> Channel setup Channel \> profiles**).
1. Az eszközök kezeléséhez engedéllyel rendelkező dolgozó hitelesítő adatainak használatával jelentkezzen be.
1. Válassza ki azt az üzletet, amely társítva van a Commerce Headquarters által létrehozott vagy újrahasznált pénztárgéphez.
1. Válassza ki a Commerce Headquarters által létrehozott eszközhöz társított pénztárgépet.
1. Az eszközt aktiválni kell. A pénztárgépre a kiválasztott üzlethez társított dolgozó kezelőazonosítójának és jelszavának használatával lehet bejelentkezni. 

Az eszköz aktiválására vonatkozó további tudnivalókat [lásd a Pénztár eszköz aktiválása során](retail-device-activation.md#activate-a-modern-pos-or-cloud-pos-device-by-using-guided-activation).

## <a name="feature-parity-with-store-commerce-for-windows"></a>A Store Commerce for Windows szolgáltatás paritása

A következő táblázat összehasonlítja a Store Commerce alkalmazás lehetőségeit a Windows rendszer és az iOS-platform Android között.

| Szolgáltatás                                                                               | Windows | Android | iOS |
| ------------------------------------------------------------------------------------- | ------- | ------- | --- |
| Dedikált hardverállomás                                                            | Igen     | Igen     | Igen |
| Megosztott hardverállomás                                                               | Igen     | Igen     | Igen |
| Kommunikáció hálózati perifériás szolgáltatásokkal (fizetési terminál, nyomtató és pénztárfiók) | Igen     | Igen     | Igen |
| OPOS-perifériák OLE-objektuma helyi hardverállomáson keresztül             | Igen     | Nem      | Nem  |
| Offline mód                                                                          | Igen     | Nem      | Nem  |

## <a name="additional-resources"></a>További erőforrások

[Store Commerce alkalmazás](store-commerce.md)

[A Store Commerce és a Cloud POS közötti választás](../mpos-or-cpos.md)

[A Store Commerce beállítási és telepítési problémáinak elhárítása](../troubleshoot/store-commerce-setup-installation.md)
