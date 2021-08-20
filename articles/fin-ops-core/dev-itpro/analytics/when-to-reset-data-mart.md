---
title: Az adatpiac alaphelyzetbe állítása – GYIK
description: Ez a témakör az adatpiac alaphelyzetbe állításával kapcsolatos néhány gyakran ismételt kérdésre ad választ.
author: jinniew
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e5a40342306eb9888b456a865ab2220dccfe65f8ccecc67bf8fc16f907e06977
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767755"
---
# <a name="data-mart-resets-faq"></a>Az adatpiac alaphelyzetbe állítása – GYIK

Ez a témakör az adatpiac alaphelyzetbe állításával kapcsolatos néhány gyakran ismételt kérdésre ad választ. Az adatpiac alaphelyzetbe állítása időigényes folyamat lehet, és a körülményektől függően előfordulhat, hogy nem ez a megoldás szükséges. Ennek megfelelően ez a témakör tájékoztatást nyújt az olyan körülményekről, amikor az adatpiac alaphelyzetbe állítása segíthet, illetve az olyan körülményekről, amikor valószínűleg nem segít.

## <a name="what-is-a-data-mart-reset"></a>Mit jelent az adatpiac alaphelyzetbe állítása?

Az adatpiac alaphelyzetbe állítása letiltja az integrációs feladatokat, törli az adatpiac összes adatát, majd újra engedélyezi az integrációt.

Annak érdekében, hogy a rendszer ne szúrjon be régi adatokat, az adatpiac visszaállítása csak a meglévő feladatok befejeződése után kezdődik el. Ha az összes feladat befejezése előtt próbálja alaphelyzetbe állítani az adatpiacot, a következőhöz hasonló üzenet jelenik meg: „Az adatpiac visszaállítását egy aktív feladat miatt nem sikerült feldolgozni. Próbálkozzon újra később.”

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Mikor kell alaphelyzetbe állítanom az adatpiacot?

Ha a következők közül egy vagy több érvényes, akkor a szervezete számára hasznos lehet az adatpiac alaphelyzetbe állítása:

- Az alkalmazás-adatbázis vissza lett állítva.
- Támogatási jegyet nyitott meg, és egy ügyfélszolgálati szakértő arra utasítja, hogy állítsa vissza az adatpiacot egy hibaelhárítási lépés részeként.
 
> [!NOTE]
> Az adatpiac alaphelyzetbe állításának folyamatát befolyásolja az adatbázis főkönyvi és költségvetési tranzakcióinak száma. Attól függően, hogy hány tranzakció van a rendszerben, az adatpiac alaphelyzetbe állítása akár 15 perc alatt is befejeződhet, illetve akár négy óráig is eltarthat. Ha azonban az alaphelyzetbe állítás négy óránál tovább tart, akkor javasoljuk, hogy forduljon a támogatáshoz.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Mikor nem megfelelő lépés az adatpiac alaphelyzetbe állítása?

Az alábbi körülmények között nem ajánljuk az adatpiac alaphelyzetbe állítását:

- Adatszinkronizálással kapcsolatos teljesítményproblémákat tapasztal.
- A következő okok valamelyike miatt ismétlődik az alaphelyzetbe állítás:

    - **Hiányzó adatok** – ha azt veszi észre, hogy adatok hiányoznak, nyisson támogatási jegyet a Microsofttal, hogy ellenőrizze a jelentés formátumát és az esetleges szinkronizálási problémákat.
    - **Elakadt integrációs állapot**
    - **Elavult rekordok** – Az elavult rekordok önmagukban nem feltétlenül igazolják az adatpiac alaphelyzetbe állítását. Ha nagy adatkészlet van beállítva, az alaphelyzetbe állítási folyamat futása időt vesz igénybe, de nem valószínű, hogy ez javulást eredményez.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Ha alaphelyzetbe állítom az adatpiacot, elvesznek a már megtervezett jelentések?

Nem. A jelentések olyan SQL-táblákban vannak tárolva, amelyekre nincs hatással az adatpiac alaphelyzetbe állítása. Ha aggódik a megtervezett jelentések elvesztése miatt, biztonsági másolatot készíthet a megőrizni kívánt tervekről. A tervek biztonsági mentéséhez nyissa meg a Report Designert, és lépjen a **Vállalat \> Vállalatok \> Építőelemek \> Exportálás** részre.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Minden felhasználónak ki kell lépnie a rendszerből az adatpiac alaphelyzetbe állításához?

Nem. A felhasználók dolgozhatnak a rendszerben az adatpiac alaphelyzetbe állítása során. Az alaphelyzetbe állítás befejeződéséig azonban nem férhetnek hozzá a Financial Reporter használatával létrehozott jelentésekhez.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
