---
title: Mikor kell alaphelyzetbe állítani az adatpiacot?
description: Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók és azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.
author: jinniew
ms.date: 05/06/2021
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
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2021
ms.locfileid: "5988992"
---
# <a name="when-to-reset-a-data-mart"></a>Mikor kell alaphelyzetbe állítani az adatpiacot?

Az adatpiac alaphelyzetbe állítása sok időt vehet igénybe. A körülményektől függően előfordulhat, hogy ez a művelet nem a szükséges megoldás. Ez a témakör azokat a körülményeket sorolja fel, amelyek egy adatpiac visszaállításával tovább javíthatók, valamint azokat, amelyeknél nem valószínű, hogy segít az adatpiac alaphelyzetbe állítása.  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a>Mikor kell alaphelyzetbe állítanom az adatpiacot?
Az adatpiac alaphelyzetbe állítása előtt vegye figyelembe a következő kérdéseket. Ha egy vagy több kérdésre igen a válasz, azt jelezheti, hogy a szervezet számára előnyös lehet az adatpiac alaphelyzetbe állítása.

- Az alkalmazás-adatbázis vissza lett állítva?
- Ha egy támogatási eseményt nyitott meg, és egy ügyfélszolgálati szakértő arra utasítja, hogy állítsa vissza az adatpiacot egy hibaelhárítási lépés részeként?
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a>Mikor nem célszerű alaphelyzetbe állítani az adatpiacot?
Bizonyos körülmények között nem ajánljuk az adatpiac alaphelyzetbe állítását. Ezek közé tartoznak a következők. 

- Adatszinkronizáláshoz kapcsolódó teljesítményproblémákat tapasztal. 
- Ha a következő okok valamelyike miatt ismétlődik az alaphelyzetbe állítás: 
  - **Hiányzó adatok** 
  - **Elakadt integrációs állapot** 
  - **Elavult rekordok** – Az elavult rekordok önmagukban nem feltétlenül igazolják az adatpiac alaphelyzetbe állítását. Ha nagy adathalmaz van beállítva, az alaphelyzetbe állítási folyamat futása időt fog igénybe venni, de nem valószínű, hogy ez javulást eredményez.
 
## <a name="what-is-a-data-mart-reset"></a>Mit jelent az adatpiac alaphelyzetbe állítása?
- A visszaállítás csak akkor indul el, ha a meglévő feladatok befejeződnek. Így garantálható, hogy a régi adatok nem lesznek beillesztve. Ezen a ponton olyan üzenetet láthat, mint például: "Az adatpiac visszaállítását egy aktív feladat miatt nem sikerült feldolgozni. Próbálkozzon újra később."
- A visszaállítás letiltja az integrációs feladatokat, és törli az adatpiac összes adatát. Az integráció újra engedélyezve van.

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a>Ha alaphelyzetbe állítom az adatpiacot, elvesznek a már megtervezett jelentések? 
Nem, a jelentések SQL-táblákban vannak tárolva, és az adatpiac alaphelyzetbe állítása nem befolyásolja őket. Ha aggódik a megtervezett jelentések elvesztése miatt, készíthet biztonsági jelentést a megőrizni kívánt tervekről. A biztonsági mentéshez nyissa meg a Jelentéstervezőt, és nyissa meg a **Vállalat > Vállalatok > Építőelemek > Exportálás** menüpontot.
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a>Szükséges, hogy minden felhasználó kilépjen a rendszerből az adatpiac alaphelyzetbe állításához?
Nem, a felhasználók továbbra is dolgoznak a rendszerben az adatpiac alaphelyzetbe állítása során. Nem férhetnek azonban hozzá a Pénzügyi jelentés alkalmazással létrehozott jelentésekhez, amíg be nem fejeződik az alaphelyzetbe állítás. 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
