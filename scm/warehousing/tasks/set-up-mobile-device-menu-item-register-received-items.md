--- 
title: "Mobileszköz-menüelem beállítása a bevételezett elem regisztrálásához"
description: "Ez a feladat a mobileszköz menü egy elemének a beállítására összpontosít."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 642e2b05c9f9a59f6b47a22f3d92f2f6ae245039
ms.contentlocale: hu-hu
ms.lasthandoff: 07/28/2017

---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Mobileszköz-menüelem beállítása a bevételezett elem regisztrálásához

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat a mobileszköz menü egy elemének a beállítására összpontosít. Ez a menüpont a beszerzési rendeléssel rendelt cikkek bevételezésének regisztrálására használható. 

Ezt az útmutatót használhatja az USMF bemutatócégen. Ezt az eljárást a raktári vezető használja.


## <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása
1. Ugrás a Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menü elemekre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Menüelem neve mezőbe.
    * Ez az egyedi azonosító a mobileszköz menücikk számára. Ha például beírhatja a „Saját beszerzési rendelés regisztráció” kifejezést.  
4. Érték beírása a Címmezőbe.
    * Ez az a cím, amely a felhasználók mobileszközein a jelenik meg. Ha például beírhatja a „Beszerzési rendelés regisztráció” kifejezést.  
5. A Mód mezőben válassza ki a „Munka” lehetőséget.
    * A beszerzési rendelés sorhoz érkezett készleten lévő mennyiség regisztrálása egy munkát hoz létre a cikkek mozgatására, az átvételi helyről a készletbe. Csak a cikkek beregisztrálása után jön létre a munka.  Ezért hagyja a Meglévő munka beállítás értékét Nem-en.  
6. Bontsa ki vagy csukja össze az Általános szakaszt.
7. Munka létrehozási folyamat mezőben válassza ki a „Beszerzési rendelési cikk bevételezése” lehetőséget.
    * A beszerzési rendelési sort egyedi módon azonosítani kell, mielőtt az aktuális készletet a raktárban regisztrálni lehet. Ebben az esetben a mobileszköz regisztrál egy beszerzési rendelés számot és cikkszámot, ez lehetővé teszi a rendszernek a BR sor azonosítását. Betárolás munka jön létre, és egy másik dolgozó kitárolhatja.    A kiválasztott munka létrehozási módszer határozza meg, hogy mely mezők válnak elérhetővé az Általános gyorslapon.  
    * Ha az Alapértelmezett adatok használata beállítást választja, az Alapértelmezett gomb elérhető. Itt kiválaszthatja a dolgozó napi munkájához szükséges adatokat megjelenítő mezőket, így ezek az értékek megjelennek a mobileszközön.  
    * Az Azonosítótábla-csoportosítás paraméter az átvétel alatt álló cikkhez kapcsolt szekvenciacsoporttal kombinálva működik. Meghatározhatja, hogy az egy raklapnál kisebb vagy nagyobb mennyiségű beérkező tételeket a rendszer összecsoportosítsa egy azonosítótábla alá, vagy minden egységhez külön azonosítótáblát rendeljen.  
    * Ha az Azonosítótábla létrehozás lehetőséget választja, az létre hoz egy egyedi azonosítótábla számot, a számsorozat kiválasztás alapján.   
    * Kiválaszthatja a munka létrehozásakor használandó sablont. Például ha cikket regisztrál a beszerzési rendeléshez, a betárolási munka a munkasablon alapján jön létre. Ha nem választja ki a munkasablont itt, a rendszer hozzárendel egy sablont a sablonokhoz hozzárendelt lekérdezésfeltétel alapján.  
    * Ha az intézkedéskódok megjelennek a mobileszközön, a dolgozók értékelhetik az állapotot vagy a cikkek mennyiségét, és kiválaszthatják a megfelelő kódot. Az intézkedéskódok szabályai határozzák meg, hogy a cikkek más raktárkezelési folyamatok számára is elérhetők lesznek-e. A szabályok meghatározhatják, hogy melyik helyutasítás használt a létrehozott munkához.   
    * Ha a Köteg intézkedéskódjai beállítást választja, a dolgozók értékelhetik az állapotot vagy egy köteg mennyiségét, és kiválaszthatják a megfelelő intézkedés kódot.  A köteg intézkedéskódjaira beállított szabályok határozzák meg, hogy a köteg más raktárkezelési folyamatok számára is elérhető lesz-e.  
    * Ha a Címkék nyomtatása beállítást választja, egy azonosítótábla-címke nyomtatódik automatikusan, amikor a cikkek beérkeznek.  
8. Kattintson a Mentés gombra.
9. Zárja be a lapot.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>A menüelem hozzáadása a mobileszköz menühöz
1. Ugrás a Raktárkezelés > Beállítás Mobileszköz > Mobileszköz menüre.
2. A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Név mezőben a „Bejövő” érték szerepel.
3. Kattintson a Szerkesztés lehetőségre.
4. A fán válassza ki az „Az Elérhető menü és cikkek fán válassza ki a menüelemet, amelyet korábban hozott létre.” lehetőséget.
    * Válassza ki az előbb létrehozott menüpontot.  
5. Kattintson a jobbra mutató nyílra.
6. Kattintson a Mentés gombra.
7. Zárja be a lapot.


