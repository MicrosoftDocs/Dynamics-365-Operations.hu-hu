---
title: Dynamics 365 Payment Connector az Adyen szolgáltatáshoz - áttekintés
description: Ez a cikk áttekintést nyújt a Microsoft Dynamics 365 Payment Connector for Adyen alkalmazásról.
author: rassadi
ms.date: 10/27/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 931fc69cda8daa2e06b6f1155fbf0369fd2bca55
ms.sourcegitcommit: 435e69160dbd7f9c61b37ac4440285a5df144622
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728294"
---
# <a name="dynamics-365-payment-connector-for-adyen-overview"></a>Dynamics 365 Payment Connector az Adyen szolgáltatáshoz - áttekintés

[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt Microsoft Dynamics a 365 Payment Connector for Adyen eszközről, és átfogó listát tartalmaz a támogatott funkciókról és funkciókról. A kapcsolódó cikkek között található az Adyen-regisztráció, a csatlakoztató konfigurációja, a gyakori kérdések, valamint egyes gyakori problémák hibaelhárítási útmutatása.

## <a name="key-terms"></a>Kulcsfogalmak

| Időszak | Leírás |
|---|---|
| Fizetési csatlakoztató | Kiterjesztés, amely megkönnyíti a kommunikációt Microsoft Dynamics 365 Commerce a (és a hozzá kapcsolódó összetevők) és a fizetési szolgáltatás között. Az ebben a cikkben ismertetett csatlakoztató a szabványos fizetési szoftverfejlesztői csomag (SDK) használatával lett megvalósítva. |
| Kártya jelen van | Olyan fizetési tranzakciókra vonatkozik, amelyekben fizikai kártya található és használható a Dynamics 365 point of Sale terminál csatlakoztatóján. |
| Nincs jelen kártya | Olyan fizetési tranzakciókra vonatkozik, ahol nincs fizikai kártya, például e-Commerce vagy Hívásközpont eset. Ilyen helyzetekben a fizetéssel kapcsolatos adatokat manuálisan kell megadni egy e-Commerce webhelyen, egy hívásközponti folyamaton, illetve a terminálon vagy a terminálon. |

## <a name="supported-features-functionality-versions-and-terminals"></a>Támogatott funkciók, funkciók, verziók és terminálok

A készletenen található Dynamics 365 Payment Connector for Adyen a szabványos fizetési SDK készletet használja. Ennek megfelelően nincs olyan különleges képessége, amely más fizetési csatlakoztatónál nem áll rendelkezésre.

### <a name="supported-versions"></a>Támogatott verziók

#### <a name="microsoft-dynamics-365-supported-versions"></a>Microsoft Dynamics 365 támogatott verzió
Az első fél verziójú Dynamics 365 Payment Connector for Adyen Microsoft Dynamics a 365 Finance 8.1.3-as verziójában (2019. január) vagy újabb verzióban, Microsoft Dynamics 365 Retail valamint a 8.1.3-as vagy újabb verzióban is támogatott. Harmadik felek azonban továbbra is kialakíthat más fizetési csatlakoztatókat az Adyen számára Microsoft Dynamics a 365 korábbi verzióihoz.

#### <a name="supported-adyen-firmware-versions"></a>Támogatott Adyen verziók

Az alábbi lista leírja, hogy milyen minimális és maximális Adyen verziók támogatottak a POS egyes verzióiban Microsoft Dynamics 365 Retail.

---

# <a name="10025"></a>[10.0.25](#tab/10-0-25)
### <a name="dynamics-365-retail-pos-version-10025"></a>Dynamics 365 Retail POS - 10.0.25-ös verzió
| Adyen verzió minimuma | Adyen maximális verziószáma |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_73p6 |

# <a name="10026"></a>[10.0.26](#tab/10-0-26)
### <a name="dynamics-365-retail-pos-version-10026"></a>Dynamics 365 Retail POS - 10.0.26-os verzió
| Adyen verzió minimuma | Adyen maximális verziószáma |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10027"></a>[10.0.27](#tab/10-0-27)
### <a name="dynamics-365-retail-pos-version-10027"></a>Dynamics 365 Retail POS - 10.0.27-es verzió
| Adyen verzió minimuma | Adyen maximális verziószáma |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10028"></a>[10.0.28](#tab/10-0-28)
### <a name="dynamics-365-retail-pos-version-10028"></a>Dynamics 365 Retail POS - 10.0.28-as verzió
| Adyen verzió minimuma | Adyen maximális verziószáma |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p22 |

# <a name="10029"></a>[10.0.29](#tab/10-0-29)
### <a name="dynamics-365-retail-pos-version-10029"></a>Dynamics 365 Retail POS - 10.0.29-es verzió
| Adyen verzió minimuma | Adyen maximális verziószáma |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

# <a name="10030"></a>[10.0.30](#tab/10-0-30)
### <a name="dynamics-365-retail-pos-version-10030"></a>Dynamics 365 Retail POS - 10.0.30-as verzió
| Adyen verzió minimuma | Adyen maximális verziószáma |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

---

> [!NOTE]
> Az Adyen a főverzió tesztelése után újabb alverzió-frissítéseket is kiadhat. Ha egy főverzió támogatott, akkor minden rendben van, ha az alverzió frissítései ugyanazon a főverzión belül vannak. Ezek a frissítések általában nagyon célzott javítások, és nem teljes körű újratesztelnek, ha korábban már tesztelték ugyanazt a főverziót. A frissítések nem haladják meg a dokumentációban felsorolt Adyen verzió maximális verzióját. 
>
> Az 53-as verziónál korábbi Adyen verzióról az 53-as verzióra való áttelepítéshez szükség van a POS KB **4577957** rendszernek a Commerce havi frissítéséhez (a 10.0.11-es verzióktól a 10.0.14-es verziókig). Ha e verziók valamelyike használatban van, és nem tartalmazza a gyorsjavítást, akkor a fizetési terminál utófrissítése csak AZ ÉS verzión keresztül engedélyezi a kifizetéseket. Ha a gyorsjavítást alkalmazza a POS-hoz, ezzel a probléma megoldásával megoldódik. Ha a POS verziója régebbi, mint a **10**.0.11-es verzió, akkor támogatási kérést kell kérni arról, hogy a szolgáltatáson kívülre került MPOS-fájloknál meg kell adni 4577957 a KB 4577957 javítást.
> 
> Az Adyen verzió 59p7-62p9 **verzióban** történő verzióinál az ajándékutalvány készpénzes fizetés művelete kétszer kéri a PIN-bevitelt olyan helyzetekben, amikor az ajándékutalványt manuálisan kell megadni. Ez a probléma nem kerül elő az ajándékutalvány lehúzáskor. Adyen vizsgálja. 

### <a name="supported-payment-terminals"></a>Támogatott fizetési terminálok
A Dynamics 365 Payment Connector for Adyen az eszköz-adyen [fizetési terminál API-t használja ki](https://www.adyen.com/blog/introducing-the-terminal-api). Az alkalmazásprogramozási felület (API) által támogatott összes fizetési terminált támogatja. A támogatott fizetési terminálok teljes listája az [Adyen POS terminálok oldalon található](https://www.adyen.com/pos-payments/terminals).

### <a name="supported-payment-instruments"></a>Támogatott fizetési eszközök

#### <a name="supported-debit-and-credit-cards"></a>Támogatott bankkártyák és hitelkártyák

| Márka | Változat | Kártya jelen van | e-Kereskedelem | Hívásközpont |
|---|---|:-:|:-:|:-:|
| MasterCard | Jóváírás | ✔ | ✔ | ✔ |
| MasterCard | Terhelés | ✔ | ✔ | ✔ |
| MasterCard | Alfanumerikus bank rendkívüli értékcsökkenése | ✔ | ✔ | ✔ |
| MasterCard | Kifizető | ✔ |  |  |
| MasterCard | Kifizető | ✔ |  |  |
| MasterCard | Maestro | ✔ | ✔ | ✔ |
| MasterCard | Maesala pay | ✔ |  |  |
| MasterCard | Maestro UK | ✔ | ✔ | ✔ |
| VÍZUM | Jóváírás | ✔ | ✔ | ✔ |
| VÍZUM | Terhelés | ✔ | ✔ | ✔ |
| VÍZUM | Alfanumerikus bank rendkívüli értékcsökkenése | ✔ | ✔ | ✔ |
| VÍZUM | Android Fizetni | ✔ |  |  |
| VÍZUM | Kifizető | ✔ |  |  |
| VÍZUM | Kifizető | ✔ |  |  |
| VÍZUM | VISA pénztár | ✔ | ✔ | ✔ |
| VÍZUM | VISA Dankort | ✔ | ✔ | ✔ |
| VÍZUM | VISA Új-Cario | ✔ | ✔ | ✔ |
| VÍZUM | VISA Aravia kártya | ✔ | ✔ | ✔ |
| AMEX | Jóváírás | ✔ | ✔ | ✔ |
| AMEX | Terhelés | ✔ | ✔ | ✔ |
| AMEX | Android Fizetni | ✔ |  |  |
| AMEX | Kifizető | ✔ |  |  |
| AMEX | Kifizető | ✔ |  |  |
| AMEX | AMEX kereskedelmi | ✔ | ✔ | ✔ |
| AMEX | AMEX-felhasználó | ✔ | ✔ | ✔ |
| AMEX | AMEX vállalat | ✔ | ✔ | ✔ |
| AMEX | AMEX kisvállalat | ✔ | ✔ | ✔ |
| Felfedezés | Normál | ✔ | ✔ | ✔ |
| Felfedezés | Android Fizetni | ✔ |  |  |
| Felfedezés | Kifizető | ✔ |  |  |
| Felfedezés | Kifizető | ✔ |  |  |
| Diners   | Normál | ✔ | ✔ | ✔ |
| Sási e-mail | Normál | ✔ | ✔ | ✔ |
| Jcb | Normál | ✔ | ✔ | ✔ |
| Szakszervezeti fizetés\* | Normál | ✔ |  |  |
| Interac Debit\* | Normál | ✔ |  |  |

\* Az Adyen nem biztosítja az interac és a Union Pay ismétlődő kártyatokeneket, ezért nem támogatottak olyan kártyával, amely nem jeleni tranzakciókat nem ad meg.

#### <a name="supported-gift-cards"></a>Támogatott ajándékutalványok
| Rendszer | Kártya jelen van | Nincs jelen kártya |
|---|:-:|---|
| Givex (givex) | ✔ | ✔ |
| Svs | ✔ | ✔ |

Ezeknek a külső ajándékutalvány-programoknak a Dynamics 365 Payment Connector for Adyen alkalmazáson keresztüli támogatásához további lépéseket kell végrehajtania. A további tudnivalókat lásd a Külső ajándékutalványok [támogatása oldalon](/dynamics365/unified-operations/retail/dev-itpro/gift-card).

#### <a name="supported-wallets"></a>Támogatott formátumok

| Rendszer | Kártya jelen van | Nincs jelen kártya |
|---|---|---|
| Alipay | A támogatás egy későbbi verzióban lesz hozzáadva. | Nem |
| WeCsat | A támogatás egy későbbi verzióban lesz hozzáadva. | Nem |

#### <a name="supported-card-present-input-methods"></a>Támogatott kártyás beviteli módok
| Beviteli mód | Támogatott | Jegyzetek |
|---|:-:|---|
| Dip | ✔ | |
| Lehúzás | ✔ | |
| Érintse meg | ✔ | |
| Manuális bevitel a POS felhasználói felületen. |  | Jelenleg nem támogatott |
| Manuális bevitel a fizetési terminálon keresztül. | ✔ | Támogatja a PIN-bejegyzéssel rendelkező hitelkártyák, terhelések és ajándékutalványok manuális bevitelét. | 


#### <a name="supported-card-present-countries"></a>Támogatott kártya jelenlegi országai

A következő országokban a Commerce összetevők rendelkezésre állnak, és a kártya támogatást nyújt az Adyen számára. A Commerce rendszer aktuális nemzetközi elérhetősége a [Nemzetközi elérhetőség oldalon található](/dynamics365/get-started/availability).

| Ország | Támogatott |
| --- | :-: |
| Ausztrália | ✔ |
| Ausztria | ✔ |
| Belgium | ✔ |
| Kanada | ✔ |
| Cseh Köztársaság | ✔ |
| Dánia | ✔ |
| Észtország | ✔ |
| Finnország | ✔ |
| Franciaország | ✔ |
| Németország | ✔ |
| Hongkong (KKT) | ✔ |
| Magyarország | ✔ |
| Izland | ✔ |
| Írország | ✔ |
| Olaszország | ✔ |
| Japán | Jövőbeli kiadás |
| Lettország | ✔ |
| Litvánia | ✔ |
| Malajzia | ✔ |
| Hollandia | ✔ |
| Új-Zéland | ✔ |
| Norvégia | ✔ |
| Lengyelország | ✔ |
| Szingapúr | ✔ |
| Svájc | ✔ |
| Spanyolország | ✔ |
| Svédország | ✔ |
| Svájc | ✔ |
| Egyesült Királyság | ✔ |
| Egyesült Államok | ✔ |
| Brazília | Jövőbeli kiadás |

#### <a name="supported-card-not-present-countries"></a>Támogatott kártya, amely nem jelen van országként

Az Adyen a következő országokban támogatja a nem jelenlítő tranzakciókat. [Egy adott ország támogatásának részleteiért forduljon az Adyenhez](https://www.adyen.com/contact/sales). A Commerce rendszer aktuális nemzetközi elérhetősége a [Nemzetközi elérhetőség oldalon található](/dynamics365/get-started/availability).

| Ország | 
| --- |
| Argentína |
| Örményország |
| Ausztrália |
| Ausztria |
| Bahrein |
| Belgium |
| Brazília |
| Bulgária |
| Kanada |
| Chile |
| Kína |
| Kolumbia |
| Horvátország |
| Ciprus |
| Cseh Köztársaság  |
| Dánia |
| Egyiptom |
| Észtország |
| Finnország |
| Franciaország |
| Grúzia |
| Németország |
| Gibraltár |
| Görögország |
| Guernsey |
| Hongkong (KKT) |
| Magyarország |
| Izland |
| India |
| Indonézia |
| Írország |
| Man-sziget |
| Izrael |
| Olaszország |
| Japán |
| Jersey |
| Korea |
| Kuvait |
| Lettország |
| Litvánia |
| Luxemburg |
| Malajzia |
| Málta |
| Mexikó |
| Marokkó |
| Hollandia |
| Új-Zéland |
| Norvégia |
| Peru |
| Lengyelország |
| Portugália |
| Katar |
| Románia |
| Szaúd-Arábia |
| Szerbia |
| Szingapúr |
| Szlovákia |
| Szlovénia |
| Dél-Afrika |
| Spanyolország |
| Svédország |
| Svájc |
| Tajvan |
| Tanzánia |
| Thaiföld |
| Törökország |
| Egyesült Arab Emírségek (UAE) |
| Egyesült Királyság |
| Amerikai Egyesült Államok, többek között Puerto Rico  |

#### <a name="supported-dynamics-365-payment-features"></a>Támogatott Dynamics 365 fizetési funkciók

Az alábbi táblázat bemutatja a Dynamics 365 Payment Connector for Adyen által támogatott funkciókat. Ezek a funkciók olyan fejlesztéseket tartalmaznak, amelyek 2018. decemberben a kifizetések SDK készletében és egyes összetevőiben találhatók. Nem kizárólagosak a Dynamics 365 Payment Connector for Adyen elemek. Ha további tájékoztatást tartalmaz arról, hogyan lehet ezeket a fejlesztéseket egy másik fizetési csatlakoztatónál használni, [akkor tekintse meg a Végpontok közötti fizetési integráció létrehozása" tájékoztatást](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension).

| Rendszer | Kártya jelen van | Nincs jelen kártya |
|---|:-:|:-:|
| [Ajándékutalvány egyenlege](/dynamics365/unified-operations/retail/dev-itpro/gift-card-cash-out) | ✔ | |
| [Ismétlődő kifizetés védelme](/dynamics365/unified-operations/retail/duplicate-payment-protection) | ✔ | |
| Csatorna jogkivonatosítása | ✔ | ✔ |
| Csatolt visszatérítések | ✔<br>(Kezdő kezdő 10.0.1) | ✔<br>(Kezdő kezdő 10.0.1) |
| [Online kifizetések mentése](../dev-itpro/adyen-connector-listPI.md) | | ✔<br>(Kezdő 10.0.2) | 
| [Külső ajándékutalványok hívásközponthoz és e-kereskedelemhez](./gift-card.md) | ✔<br>(Új 10.0.10) | 
| [SCA-kifizetés átirányítása](../adyen_redirect.md) | | ✔<br>(Kezdő 10.0.12) |
| [Dedikált fizetési terminálok és utasítások a nyomtatónak és a pénztárgépfióknak](../pos-multi-hws.md) | ✔<br>(Kezdő 10.0.12) | |
| [SDK-szintű billenőtámogatás az Adyen-csatlakoztatón keresztül](tipping.md) | ✔<br>(Kezdő kezdő 10.0.14) | |
| [A rendelésszámlázás növekményes rögzítése](incremental-capture.md) |  | ✔<br>(Kezdő kezdő 10.0.18) |
| [Előlegfizetések](../wallets.md) |  | ✔<br>(Kezdő 10.0.20) |
| [Fizetési adyen](google-pay-adyen.md) |  | ✔<br>(Új 10.0.27) |

## <a name="next-steps"></a>További lépések

A Dynamics 365 Payment Connector for Adyen [regisztrációjáról és konfigurálásról a Dynamics 365 Payment Connector for Adyen telepítője nyújt tájékoztatást](adyen-connector-setup.md).

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Payment Connector az Adyen szolgáltatáshoz beállítása](adyen-connector-setup.md)

[Dynamics 365 Payment Connector az Adyen - GYIK](adyen-connector-faq.md)

[Dynamics 365 Payment Connector az Adyen szolgáltatáshoz – hibaelhárítás](adyen-connector-troubleshoot.md)

[Kifizetésekkel kapcsolatos GYIK](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
