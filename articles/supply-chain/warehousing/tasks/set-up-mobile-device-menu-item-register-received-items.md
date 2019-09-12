---
title: Mobileszköz-menüelem beállítása a bevételezett elemek regisztrálásához
description: Ez a témakör a mobileszköz menüpontja beállítását ismerteti.
author: ShylaThompson
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFMenu
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 599a533c90b0346637221fecc78ddd688410fb3c
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914745"
---
# <a name="set-up-a-mobile-device-menu-item-to-register-received-items"></a>Mobileszköz-menüelem beállítása a bevételezett elemek regisztrálásához

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a témakör a mobileszköz menüpontja beállítását ismerteti. Ez a menüpont a beszerzési rendeléssel rendelt cikkek bevételezésének regisztrálására használható. 

Ezt az útmutatót használhatja az USMF bemutatócégen. Ezt az eljárást a raktári vezető használja.


## <a name="create-a-mobile-device-menu-item"></a>Mobileszköz-menüpont létrehozása
1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menüpontjai elemre.**
2. Válassza az **Új** lehetőséget.
3. Írjon be egy értéket a **Menüelem neve** mezőbe. Ez az egyedi azonosító a mobileszköz menücikk számára. Például megadhatja a `My PO registration` kifejezést.  
4. Érték beírása a **Cím** mezőbe. Ez az a cím, amely a felhasználók mobileszközein a jelenik meg. Például megadhatja a `PO registration` kifejezést.  
5. A **Mód** mezőben válassza ki a **Munka** lehetőséget. A beszerzési rendelés sorhoz érkezett készleten lévő mennyiség regisztrálása egy munkát hoz létre a cikkek mozgatására, az átvételi helyről a készletbe. Csak a cikkek beregisztrálása után jön létre a munka. Ezért hagyja a **Meglévő munka használata** beállítás értékét **Nem**-en.
6. Az **Általános** szakasz **Munkalétrehozási folyamat** mezőjében válassza ki a **Beszerzési rendelési cikk bevételezése** lehetőséget.
    - A beszerzési rendelési sort egyedi módon azonosítani kell, mielőtt az aktuális készletet a raktárban regisztrálni lehet. Ebben az esetben a mobileszköz regisztrál egy beszerzési rendelés számot és cikkszámot, ez lehetővé teszi a rendszernek a BR sor azonosítását. Betárolás munka jön létre, és egy másik dolgozó kitárolhatja. A kiválasztott munka-létrehozási módszer határozza meg, hogy mely mezők válnak elérhetővé az **Általános** gyorslapon.  
    - Ha az **Alapértelmezett adatok** használata beállítást választja, az **Alapértelmezett** gomb aktív. Itt kiválaszthatja a dolgozó napi munkájához szükséges adatokat megjelenítő mezőket, így ezek az értékek megjelennek a mobileszközön.  
    - Az **Azonosítótábla-csoportosítás** paraméter az átvétel alatt álló cikkhez kapcsolt szekvenciacsoporttal kombinálva működik. Meghatározhatja, hogy az egy raklapnál kisebb vagy nagyobb mennyiségű beérkező tételeket a rendszer összecsoportosítsa egy azonosítótábla alá, vagy minden egységhez külön azonosítótáblát rendeljen.  
    - Ha az **Azonosítótábla létrehozása** lehetőséget választja, azzal a számsorozat kiválasztása alapján létrehoz egy egyedi azonosítótáblát.  
    - Kiválaszthatja a munka létrehozásakor használandó sablont. Például ha cikket regisztrál a beszerzési rendeléshez, a betárolási munka a munkasablon alapján jön létre. Ha nem választja ki a munkasablont itt, a rendszer hozzárendel egy sablont a sablonokhoz hozzárendelt lekérdezésfeltétel alapján.  
    - Ha az intézkedéskódok megjelennek a mobileszközön, a dolgozók értékelhetik az állapotot vagy a cikkek mennyiségét, és kiválaszthatják a megfelelő kódot. Az intézkedéskódok szabályai határozzák meg, hogy a cikkek más raktárkezelési folyamatok számára is elérhetők lesznek-e. A szabályok meghatározhatják, hogy melyik helyutasítás használt a létrehozott munkához.   
    - Ha a **Köteg intézkedéskódjai** beállítást választja, a dolgozók értékelhetik az állapotot vagy egy köteg mennyiségét, és kiválaszthatják a megfelelő intézkedéskódot. A köteg intézkedéskódjaira beállított szabályok határozzák meg, hogy a köteg más raktárkezelési folyamatok számára is elérhető lesz-e.  
    - Ha a **Címkék nyomtatása** beállítást választja, a rendszer automatikusan kinyomtat egy azonosítótábla-címkét, amikor a cikkek beérkeznek.  
7. Válassza a **Mentés** lehetőséget.
8. Zárja be a lapot.

## <a name="add-the-menu-item-to-a-mobile-device-menu"></a>A menüelem hozzáadása a mobileszköz menühöz
1. A navigációs ablaktáblán ugorjon a **Modulok > Raktárkezelés > Beállítás > Mobileszköz > Mobileszköz menüpontja elemre.**
2. A **Gyorsszűrő** használatával végezzen szűrést az `inbound` értékkel rendelkező **Név** mezőben.
3. Válassza ki a **Szerkesztés** opciót.
4. Válassza ki az az elérhető menük és cikkek fán azt a menüelemet, amelyet korábban hozott létre.
5. Kattintson a jobbra mutató nyílra.
6. Válassza a **Mentés** lehetőséget.
7. Zárja be a lapot.

