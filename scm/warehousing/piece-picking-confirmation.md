---
title: "Darab kitárolásának megerősítése"
description: "Ez a témakör leírja, hogyan állíthatja be és alkalmazhatja a darabkitárolás megerősítését mobileszközről."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: c5340f4dacd743600ef955c8d5228d1e2d2d2fa9
ms.contentlocale: hu-hu
ms.lasthandoff: 06/20/2017

---

# <a name="piece-picking-confirmation"></a>Darab kitárolásának megerősítése

[!include[banner](../includes/banner.md)]

A darabkitárolás lehetővé teszi, hogy minden egyes készletet mobileszközön végzett kitárolási vagy leltározási munka segítségével hagyjon jóvá. A kitároláshoz megersítheti a feldolgozandó munka mennyiségét a kitárolni kívánt mennyiségére vonatkoztatva. Leltározási munka esetén beolvashatja a leltározandó készletet, és nyomon követheti a teljes mennyiséget.

Darabkitárolás engedélyezésekor a program automatikusan kijelöli a termék megerősítése lehetőséget. Munkatípusú kitárolás esetén maximális darabszám van meghatározva. Ez lehetővé teszi a munka során kötelezően megerősítendő darabok maximumának beállítását. A maximális mennyiség a feldolgozás alatt álló aktuális munkaegységen alapul. A leltározási munkatípus esetében nincs maximum.

A beolvasott vonalkódhoz társított mennyiséget és mértékegységet is használhatja. Ez működik a bejövő folyamatok esetén, beleértve a vegyes azonosítótáblák bevételezését, a beszerzési rendelési cikket, az átmozgatási rendelési cikket és a rakománycikket. Működik a darabkitárolás esetén is, ahol a vonalkód beolvasása hozzáadja a mennyiséget a megerősített darabok számához, a konvertálás pedig a vonalkódon levő mértékegység és a munkaegység között történik. Ha a vonalkódon levő mértékegység leltározása során megerősítést nyer, hogy a mennyiség engedélyezve van a szekvenciacsoport leltározásához, a mennyiséget a rendszer hozzáadja a teljes számhoz.

## <a name="where-it-applies"></a>Alkalmazási kör

A darabkitárolás minden leltározási munka esetén és bármilyen munkatípus kezdeti kitárolása esetén működik A darabkitárolás nem alkalmazható, hogy a cikket sorozatszámok vezérlik, vagy ha a cikk egy termelési vagy kanbankitárolás egy azonosítótáblával szabályozott helyről, és a cikk előkészítésre van beállítva.

## <a name="set-up-piece-picking"></a>Darabkitárolás beállítása

1.  A mobileszköz menüpontjában nyissa meg a munkamegerősítés beállítási képernyőjét: Raktárkezelés > **Raktárkezelés** > **Beállítás** > **Mobileszköz** > **Mobileszköz menüpontjai**. 
2. A mobileszköz menüpontjából nyissa meg a Munkamegerősítés beállítását.

A következő lehetőségek közül választhat, ha a munka típusa kitárolás vagy leltározás.

| Lehetőség        | Leírás   | 
| ------------- | ------------- |
| Darab kitárolásának megerősítése   | Elérhető kitárolási és leltározási munkatípusok esetében. A termék megerősítése automatikusan be van jelölve. Lehetővé teszi, hogy a mobileszközről erősítse meg a készlet minden elemét. | 
| Darabok maximális száma     | Elérhető kitárolási munkához, ha a darabkitárolás megerősítése engedélyezve van. Beállítja a megerősítendő darabszám maximális értékét. |  
