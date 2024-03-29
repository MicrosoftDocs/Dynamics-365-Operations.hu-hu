---
title: Dedikált fizetési terminálok és utasítások a nyomtatónak és a pénztárgépfióknak
description: Ez a cikk tájékoztatást ad arról, hogy van-e külön fizetési terminálja, és kéri a felhasználót, hogy válasszon ki egy pénztárfiókot és egy nyugtanyomtatót.
author: BrianShook
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 7c010448e43bbfb1f949508ce1b62bd07f3107e1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874921"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>Dedikált fizetési terminálok és utasítások a nyomtatónak és a pénztárgépfióknak

[!include [banner](includes/banner.md)]

Ez a cikk tájékoztatást ad arról, hogy van-e külön fizetési terminálja, és kéri a felhasználót, hogy válasszon ki egy pénztárfiókot és egy nyugtanyomtatót.

## <a name="overview"></a>Áttekintés

A korszerű kiskereskedők az üzletbeli fizetési élmény javításának módjait keresik. Az elektronikus fizetéssel történő papír nélküli pénztárfolyamatok irányába mutató trendek nem csak a vásárlási élmény gördülékenségét segítik elő, de ezeknek köszönhetően nem kell minden bolti dolgozónak a perifériás eszköz teljes készletével rendelkeznie.

A Microsoft Dynamics 365 Commerce ezeket a trendeket úgy támogatja, hogy lehetővé tesz egy olyan esetet, amikor egy pénztár (POS) eszköz állandóan hozzárendelt dedikált fizetési terminállal rendekezik, azonban nem rendelkezik saját nyugtanyomtatóval vagy pénztárgépfiókkal. Amikor a munkatársaknak nyugtát kell nyomtatniuk, vagy készpénzes fizetést fogadnak, a rendszer felkéri őket egy hardverállomás kiválasztására, ahol azok az eszközök be vannak állítva.

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Regisztrál | A POS pénztárgép példányának konfigurálására használt entitás. |
| Eszköz | Egy POS pénztárgép fizikai példányának és a hozzárendelt Modern POS alkalmazásnak a megjelenítése. |
| Dedikált hardverállomás | A Modern POS for Windows és a Modern POS for Android alkalmazás beépített hardverállomás üzleti logikával rendelkezik. |
| Drawer kick (d/k) port | Egy hagyományos módszer a pénzfiókok nyugtanyomtatóhoz való csatlakoztatására. |
| Hálózati perifériák | Beépített támogatás a hálózatban engedélyezett kifizetési terminálokhoz, nyugtanyomtatókhoz és pénztárgépfiókokhoz. |

## <a name="supported-pos-clients-and-devices"></a>Támogatott POS-ügyfelek és eszközök

Az ebben a cikkben ismertetett funkciókat támogatja a Modern POS for Windows, és a Modern POS for POS pos Android ügyfelek.

Ez a funkció támogatja a hálózatban engedélyezett fizetési terminálokat és a nyugtanyomtatókat. A pénztárgépfiókok támogatásához csatlakoztassa a pénztárgépfiókot a hálózatra engedélyezett nyugtanyomtatóhoz a d/k porton keresztül.

Ehhez a funkcióhoz azonnal használható támogatást biztosít a [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](./dev-itpro/adyen-connector.md?tabs=8-1-3). Előfordulhat azonban, hogy a fizetések esetében Commerce szoftverfejlesztői készlet (SDK) egyéb fizetési összekötőket támogat. A támogatott nyugtanyomtatók közé tartoznak a Star Micronics és az Epson hálózatkompatibilis nyugtanyomtatói.

Ha be szeretné állítani a Star Micronics nyugtanyomtatókat, használja a Star Micronics nyomtató segédprogramot az eszköz konfigurálásához, hogy a hálózaton keresztül is használható legyen. Ez a segédprogram biztosítja az eszköz IP-címét is.

Az Epson nyugtanyomtatóinak beállításához használja az Epson ePOS-Print segédprogramot az eszköz hálózati protokollok használatára történő beállításához.

A hálózati perifériák beállításával kapcsolatos további tudnivalókat lásd: [Hálózati perifériák támogatása – áttekintés](./dev-itpro/network-peripherals.md).

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>Dedikált fizetési terminál beállítása és felkérés a nyomtató és a pénztárgépfiók kiválasztására

### <a name="set-up-hardware-profiles"></a>Hardverprofilok beállítása

Kétféle hardverprofillal kell rendelkeznie. Az első a pénztárgéphez van rendelve. A második az üzlet szintjén van hozzárendelve egy hardvereszközhöz, és a hálózati nyugtanyomtatók és pénztárgépfiókok logikai csoportosítására szolgál.

#### <a name="set-up-a-hardware-profile-for-the-register"></a>Állítson be egy hardverprofilt a pénztárgép számára

A pénztárgéphez társított hardverprofil beállításához hajtsa végre az alábbi lépéseket.

1. A Dynamics 365 Commerce alkalmazásban keresse meg a **Hardverprofil** elemet.
2. Válassza az **Új** lehetőséget.
3. Rendeljen hozzá egy hardverprofilt, majd adjon meg egy leírást. Ez a hardverprofil lesz hozzárendelve magához a pénztárgéphez. Ezért a **Dedikált, tartalékkal** leírás elegendő.
4. A különböző típusú eszközök gyorslapján a következő eszköztípusok állíthatók be.

    | Eszköz | Típus | Eszköznév | További részletek |
    |---|---|---|---|
    | Nyomtató | Hálózat | *Bármely* | Az eszköznév megkülönbözteti a kis- és nagybetűket. A **Nyugtaprofil azonosítója** elemnek azonosnak kell lennie a csatorna szintjén a hardverállomáshoz hozzárendelt hardverprofilban megadott hálózati nyomtató **Nyugtaprofil azonosítója** elemmel. |
    | Pénztárfiók | Hálózat | *Bármely* | Az eszköznév megkülönbözteti a kis- és nagybetűket. A **Megosztott műszak használata** lehetőséget állítsa **Igen** értékre. |
    | EFT szolgáltatás | Adyen | Nem alkalmazható | Az azonnal használható Adyen összekötő beállításával kapcsolatos további információkért lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](./dev-itpro/adyen-connector.md?tabs=8-1-3). Más fizetési összekötők is támogathatók a [Commerce szoftverfejlesztői készlet (SDK) fizetésekhez](./dev-itpro/end-to-end-payment-extension.md) használatával. |
    | PIN-billentyűzet | Hálózat | **MicrosoftAdyenDeviceV001** | Egyik sem. |

5. A Dynamics 365 Commerce alkalmazásban keresse meg a **Pénztárgépek** elemet.
6. Válasszon ki egy pénztárgépet a pénztárgép számának kiválasztásával, majd válassza a **Szerkesztés** parancsot.
7. Rendelje hozzá az imént létrehozott hardverprofilt a pénztárgéphez, amelynek dedikált fizetési terminált kell használnia. A pénztárgéphez rendelt eszköznek vagy a Modern POS for Windows alkalmazást vagy a Modern POS for Android alkalmazást kell használnia.
8. Válassza a **Mentés** lehetőséget.
9. A Művelet panel **Pénztárgépek** lapján válassza az **IP-címek konfigurálása** menüpontot.
10. A **PIN-billentyűzet** gyorslapon adja meg a fizetési terminál IP-címét. A fizetési terminál IP-címének Adyen összekötővel történő lekérésével kapcsolatos tudnivalókért lásd: [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](./dev-itpro/adyen-connector.md?tabs=8-1-3).
11. Válassza a **Mentés** lehetőséget.

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>A nyugtanyomtató és a pénztárgépfiók hardverprofiljának beállítása

A hálózati nyugtanyomtató és a pénztárgépfiók csoportosítására használt hardverprofilt a következőképpen állíthatja be.

1. A Dynamics 365 Commerce alkalmazásban keresse meg a **Hardverprofil** elemet.
2. Válassza az **Új** lehetőséget.
3. Rendeljen hozzá egy hardverprofilt, majd adjon meg egy leírást. Ezt a hardverprofilt a program a nyugtanyomtató és a pénztárgépfiókok csoportosítására használja. Ennek megfelelően egy olyan leírás is elegendő, mint a **Hálózati nyomtató és pénztárgépfiók**.
4. A különböző típusú eszközök gyorslapján a következő eszköztípusok állíthatók be.

    | Eszköz | Típus | Leírás | További részletek |
    |---|---|---|---|
    | Nyomtató | Hálózat | **Epson** vagy **Star** | Az eszköznév megkülönbözteti a kis- és nagybetűket. A **Nyugtaprofil azonosítója** elemnek azonosnak kell lennie a pénztárgéphez hozzárendelt hardverprofilban megadott nyomtató **Nyugtaprofil azonosítója** elemmel. |
    | Pénztárfiók | Tartalék | **Epson** vagy **Star** | Az eszköznév megkülönbözteti a kis- és nagybetűket. A **Megosztott műszak használata** lehetőséget állítsa **Igen** értékre. |

5. Válassza a **Mentés** lehetőséget.

### <a name="set-up-hardware-stations"></a>Hardverállomások beállítása

Két hardverállomásra van szükség. Az első a pénztrágépre lesz leképezve. A második a szükséges módon lesz kiválasztva, ha nyugtát kell nyomtatni vagy a pénztárgépfiókot ki kell nyitni.

#### <a name="register-a-hardware-station"></a>Hardverállomás rgisztrálása

1. A Dynamics 365 Commerce alkalmazásban keresse meg az **Összes üzlet** elemet.
2. Válasszon egy üzletet a **Kiskereskedelmi csatorna azonosító** értékének kiválasztásáva, majd válassza a **Szerkesztés** parancsot.
3. Válassza a **Hardverállomások** gyorslap **Hozzáadás** elemét.
4. A **Hardverállomás típusa** mezőt állítsa **Dedikált** értékre.
5. Írjon be egy leírást, de ne adjon meg más értéket ehhez a hardverállomáshoz. Ez a hardverállomás kerül minden esetben felhasználásra a pénztárgépekhez. 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>A nyugtanyomtató és a pénztárgépfiók hardverállomásának beállítása

1. A Dynamics 365 Commerce alkalmazásban keresse meg az **Összes üzlet** elemet.
2. Válasszon egy üzletet a **Kiskereskedelmi csatorna azonosító** értékének kiválasztásáva, majd válassza a **Szerkesztés** parancsot.
3. Válassza a **Hardverállomások** gyorslap **Hozzáadás** elemét.
4. A **Hardverállomás típusa** mezőt állítsa **Dedikált** értékre.
5. Adjon meg leírást. Ezt a hardverállomást a program a nyugtanyomtatóhoz és a pénztárgépfiókhoz használja.
6. A **Hardverprofil** mezőben válassza ki azt a hardverprofilt, amelyet korábban létrehozott a nyugtanyomtatóhoz és a pénztárgépfiókhoz.
7. Válassza a **Mentés** lehetőséget.
8. Miközben a nyugtanyomtató és a pénztárgépfiók hardverállomása továbbra is ki van választva, válassza az **IP-címek konfigurálása** lehetőséget.
9. Kérje le a nyomtató IP-címét, és adja meg a nyugtanyomtató és a pénztárgépfiók IP-címeként.
10. Válassza a **Mentés** lehetőséget
11. Keresse meg az **Elosztási ütemezések** elemet.
12. Válassza ki az **1090**-es elosztási ütemezést, majd válassza a **Futtatás most** parancsot.
13. Válassza ki az **1070**-es elosztási ütemezést, majd válassza a **Futtatás most** parancsot.

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>A rendszer beállítása a nyugtanyomtató és a pénztárgépfiók kiválasztásának megadására a szükséges módon

1. A támogatott POS-ügyfélben zárja be az aktuális műszakot, ha a műszak meg van nyitva.
2. Jelentkezzen be, majd válassza ki a **Nem fiókos fiókműveletek** lehetőséget.
3. A **Hardverállomások kezelése** művelettel kapcsolja be a hardverállomást.
4. Válassza ki a pénztrához létrehozott hardverállomást annak aktívvá tételéhez.
5. Jelentkezzen ki a pénztárból, majd ismét jelentkezzen be, és nyisson meg egy műszakot.

A hardverprofilhoz rendelt fizetési terminál most mindig aktív lesz, és a program rákérdez, hogy szükség van-e nyugtanyomtatóra vagy pénztárgépfiókra.

Számos kereskedő, aki ezt a funkciót kérte, érdekelt a hulladék csökkentésében az e-mailes nyugták és az elektronikus fizetések ösztönzésével. A pénztár konfigurációjától függően a rendszer csak akkor kéri a nyugtanyomtató vagy a pénztárgépfiók kiválasztását a munkatárstól, ha a vevő fizikai nyugtát kér, vagy készpénzes fizetést kíván eszközölni.

Az üzlet alkalmazottainak egy tranzakcióhoz csak egy alkalommal kell kiválasztaniuk egy hardvereszközt, hacsak nem kell kinyomtatni a nyugtát, és emellett készpénzt használni a fizetéshez, de az eredetileg kiválasztott hardverprofil nem tartalmazza mindkét eszközt. Ebben az esetben az üzlet munkatársát a program újra megkérdezi, hogy válasszon egy hardverállomást, amely a tranzakció befejezéséhez használható.

## <a name="related-articles"></a>Kapcsolódó cikkek

- [POS Hybrid alkalmazás beállítása Android és iOS rendszerre](./dev-itpro/hybridapp.md)
- [Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](./dev-itpro/adyen-connector.md?tabs=8-1-3)
- [Hálózati perifériák támogatása – áttekintés](./dev-itpro/network-peripherals.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
