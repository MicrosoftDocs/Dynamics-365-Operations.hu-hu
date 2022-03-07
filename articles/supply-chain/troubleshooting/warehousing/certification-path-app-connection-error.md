---
title: Hiba a tanúsítvány elérési útjának beállításakor az alkalmazáskapcsolatban
description: Ha a Warehouse Management alkalmazás a "Nem található a tanúsítvány elérési útjának megbízhatósági horgonyzása" hibát jeleníti meg, akkor ezen a lapon oldhatja meg, illetve kerülheti meg a problémát.
author: ivanv-microsoft
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: WMA
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ivanv
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e4a36874ac4982c9c92a7dcc17c13c7c7c02bf8c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476555"
---
# <a name="trust-anchor-for-certification-path-not-found-when-setting-up-app-connection"></a>Nem található a tanúsítvány elérési útjának megbízhatósági horgonyzása az alkalmazáskapcsolat beállításakor

## <a name="symptoms"></a>Tünetek

Amikor a Supply Chain Managementhez próbál kapcsolódni, a Warehouse Management alkalmazás a következő hibaüzenetet jelenítheti meg:

> java.security.cert.certPathValidatorException: A tanúsítvány elérési útjának megbízhatósági horgonyzás nem található.

Ez a probléma a következő tulajdonságokkal rendelkező eszközöket érintheti:

- **Operációs rendszer verziója**: Android 4.4.x (például: Zebra TC55). Ez nem probléma a közelmúltbeli Android verziókban.
- **Supply Chain Management helye**: felhő
- **Kapcsolat módja**: titkos ügyfélkód vagy tanúsítvány

## <a name="possible-cause"></a>Lehetséges ok

Lehet, hogy a Microsoft frissítette a Supply Chain Management által használt kiszolgálói SSL-tanúsítványokat. Emiatt előfordulhat, hogy a gyökértanúsítvány és/vagy valamelyik köztes tanúsítvány megváltozott, így az új tanúsítvány nem szerepel a mobileszköz megbízható rendszertanúsítványait felsoroló listán. Az Android újabb verziói automatikusan frissítik a megbízható tanúsítványok listáját, az Android 4.4.x azonban nem.

## <a name="resolution"></a>Megoldás

A probléma megoldásához tegye az alábbiak egyikét:

- A következő szakaszban leírt megoldással frissítse az összes szükséges eszközt.
- *Lehet*, hogy a megbízható tanúsító hatóságok (CA) listájáért fel kell vennie a kapcsolatot a Zebrával vagy a Google-lel. Ezt azonban nem erősítettük meg.
- Ha lehetséges, cserélje le a régebbi eszközöket olyan eszközökre, amelyek az Android újabb verzióját futtatják (ahol a megbízható CA-tanúsítványok automatikusan frissülnek).

### <a name="workaround"></a>Megkerülő megoldás

#### <a name="step-1-export-the-new-root-certificate-from-supply-chain-management"></a>1. lépés: Az új gyökértanúsítvány exportálása a Supply Chain Managementből

Manuálisan töltse le az új gyökértanúsítványt az internetböngészővel a következő lépéseket követve:

1. Jelentkezzen be a Dynamics Supply Chain Management alkalmazásba, és nyissa meg a kezdőlapot.

1. A böngésző címsorában válassza ki a zár ikont a **Hely biztonságos** párbeszédpanel megnyitásához.
1. A párbeszédpanelen válassza a **Tanúsítvány (érvényes)** lehetőséget a tanúsítvány **Tanúsítvány** ablakának megnyitásához.
1. Nyissa meg a **Tanúsítvány elérési útja** lapot a **Tanúsítvány** ablakban.
1. Válassza ki a hierarchiában látható felső tanúsítványt. (ez a gyökértanúsítvány).
1. Nyissa meg a **Részletek** lapot a **Tanúsítvány** ablakban.
1. Válassza ki a **Másolás fájlba** gombot a **Részletek** lap alján.
1. Megnyílik a **Tanúsítványexportáló varázsló**. A folytatáshoz kattintson a **Tovább** gombra.
1. Megnyílik az **Exportfájl-formátum** lap. Válassza a **DER kódolású bináris X.509 (. CER)** lehetőséget. Majd kattintson a **Tovább** gombra.
1. Megnyílik az **Exportálni kívánt fájlok** lap – adja meg a fájl nevét és helyét. Majd kattintson a **Tovább** gombra.
1. Megnyílik a **Tanúsítványexportáló varázsló kitöltése** lap, amely az exportálás eredményét mutatja. Válassza a **Befejezés** lehetőséget.

#### <a name="step-2-install-the-downloaded-certificate-onto-the-affected-devices"></a>2. lépés: A letöltött tanúsítvány telepítése az érintett eszközökre

A letöltött tanúsítványt a következő lépések alkalmazásával telepítheti:

1. Vigye át az előző lépésben letöltött tanúsítványt a frissíteni kívánt eszközre. SD-kártya vagy hálózati kapcsolat használatával például elérhetővé lehet tenni a fájlt az eszköz számára.
1. Nyissa meg az eszköz biztonsági beállításait, és válassza ki a menübeállítást a tanúsítvány fájlból való telepítéséhez. (Az ehhez szükséges pontos lépések az eszköz és az operációs rendszer verziójától függnek.)
1. Az új tanúsítványnak mostantól a megbízható tanúsítványok **Felhasználó** lapján kell megjelennie.
1. Ismételje meg az eljárást minden érintett termék esetén.
