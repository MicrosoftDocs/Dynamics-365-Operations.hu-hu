---
title: Az adatpiac alaphelyzetbe állítása – GYIK
description: Ez a témakör az adatpiac alaphelyzetbe állításával kapcsolatos néhány gyakran ismételt kérdésre ad választ.
author: jinniew
ms.date: 02/14/2022
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
ms.openlocfilehash: 53f45f469c39f9e389763aa0daed658e5a62d377
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119512"
---
# <a name="data-mart-resets-faq"></a>Az adatpiac alaphelyzetbe állítása – GYIK

Ez a témakör az adatpiac alaphelyzetbe állításával kapcsolatos néhány gyakran ismételt kérdésre ad választ. Az adatpiac alaphelyzetbe állítása időigényes folyamat lehet, és a körülményektől függően előfordulhat, hogy nem ez a megoldás szükséges. Ennek megfelelően ez a témakör tájékoztatást nyújt az olyan körülményekről, amikor az adatpiac alaphelyzetbe állítása segíthet, illetve az olyan körülményekről, amikor valószínűleg nem segít.

## <a name="what-is-a-data-mart-reset"></a>Mit jelent az adatpiac alaphelyzetbe állítása?

Az adatpiac alaphelyzetbe állítása letiltja az integrációs feladatokat, törli az adatpiac összes adatát, majd újra engedélyezi az integrációt.

Annak érdekében, hogy a rendszer ne szúrjon be régi adatokat, az adatpiac visszaállítása csak a meglévő feladatok befejeződése után kezdődik el. Ha az összes feladat befejezése előtt próbálja alaphelyzetbe állítani az adatpiacot, a következőhöz hasonló üzenet jelenik meg: „Az adatpiac visszaállítását egy aktív feladat miatt nem sikerült feldolgozni. Próbálkozzon újra később.”

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a>Mikor kell alaphelyzetbe állítanom az adatpiacot?

Ha a következők közül egy vagy több érvényes, akkor a szervezete számára hasznos lehet az adatpiac alaphelyzetbe állítása:

- **Az alkalmazás-adatbázis vissza lett ásva.**
- **Egy támogatási jegy megnyitása** - egy támogatási szakember arra utasított, hogy állítsa vissza az adatpiacot egy hibaelhárítási lépés részeként.
- **Elavult rekordok nagy** százaléka – az elavult rekordok önmagukban nem feltétlenül igazolják az adatpiac alaphelyzetbe állítását. Az elavult adatok nagy százalékával csökkenhet a jelentés generálása és integrációja, és további helyfelhasználást eredményez az adatbázis számára. Javasoljuk, hogy egy datamart alaphelyzetbe állítása távolítsa el az elavult adatokat, ha az adatpiacon 80%-nál több elavult adat van.
 
> [!NOTE]
> Az adatpiac alaphelyzetbe állításának folyamatát befolyásolja az adatbázis főkönyvi és költségvetési tranzakcióinak száma. Attól függően, hogy hány tranzakció van a rendszerben, az adatpiac alaphelyzetbe állítása akár 15 perc alatt is befejeződhet, illetve akár négy óráig is eltarthat. Ha azonban az alaphelyzetbe állítás négy óránál tovább tart, akkor javasoljuk, hogy forduljon a támogatáshoz.
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a>Mikor nem megfelelő lépés az adatpiac alaphelyzetbe állítása?

Az alábbi körülmények között nem ajánljuk az adatpiac alaphelyzetbe állítását:

- Adatintegrációs teljesítményproblémák vannak.
- A következő okok valamelyike miatt ismétlődik az alaphelyzetbe állítás:

    - **Hiányzó vagy nem várt adatok** a jelentésben – ha az adatok hiányát észleli, nyisson meg egy támogatási jegyet a Microsofttal, hogy áttekintse a jelentés formátumát és az esetleges adatszinkronizálási problémákat.
    - **Elakadt integrációs állapot**
   
## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Ha alaphelyzetbe állítom az adatpiacot, elvesznek a már megtervezett jelentések?

Nem. A jelentések olyan SQL-táblákban vannak tárolva, amelyekre nincs hatással az adatpiac alaphelyzetbe állítása. Ha aggódik a megtervezett jelentések elvesztése miatt, biztonsági másolatot készíthet a megőrizni kívánt tervekről. A tervek biztonsági mentéséhez nyissa meg a Report Designert, és lépjen a **Vállalat \> Vállalatok \> Építőelemek \> Exportálás** részre.
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a>Minden felhasználónak ki kell lépnie a rendszerből az adatpiac alaphelyzetbe állításához?

Nem. A felhasználók dolgozhatnak a rendszerben az adatpiac alaphelyzetbe állítása során. Az alaphelyzetbe állítás befejeződéséig azonban nem férhetnek hozzá a Financial Reporter használatával létrehozott jelentésekhez.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
