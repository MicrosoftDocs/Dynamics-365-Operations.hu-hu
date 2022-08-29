---
title: Sorozatszámmal szabályozott termékek visszaküldése a pénztárban
description: Ez a témakör a Microsoft Dynamics 365 Commerce pénztári alkalmazás visszárufolyamatának részeként a szerializált cikkek érvényességének érvényességét ismerteti.
author: hhainesms
ms.date: 06/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9fa7e47b6d650370afe4b98d7eca01253bd1bc36
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268474"
---
# <a name="return-serial-numbercontrolled-products-in-pos"></a>Sorozatszámmal szabályozott termékek visszaküldése a pénztárban

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce pénztári alkalmazás visszárufolyamatának részeként a szerializált cikkek érvényességének érvényességét ismerteti.

> [!NOTE]
> A Commerce 10.0.20 és újabb kiadásaiban , a POS-terminálon elérhető egy új funkció, amelynek neve **Egyesített visszaküldés-feldolgozási élmény a pénztárban**. Ahhoz, hogy a visszárurendelések feldolgozása során a sorozatszám érvényesség ellenőrzése használható legyen a pénztárban, be kell kapcsolnia ezt a funkciót. A funkció bekapcsolása által biztosított egyéb funkciókkal kapcsolatos tudnivalókat lásd [Visszatérítések létrehozása a pénztárban](POS-returns.md).
>
> A funkciót a bekapcsolása után nem lehet kikapcsolni.

## <a name="options-for-validating-serialized-returns"></a>Szerializált visszaküldések érvényességének ellenőrzésével kapcsolatos beállítások

Ha az **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkció be van kapcsolva, a szervezetek a pénztáron keresztül ellenőrzést végezhetnek a sorozatszámmal szabályozott cikkek visszaküldéseiben. Ez a képesség képes figyelmeztetni a felhasználókat, ha a visszaadott sorozatszám eltér az eredeti eladott sorozatszámtól. A Commerce 10.0.20 vagy újabb verzióiban a felhasználók által kapott üzenet csak figyelmeztető üzenet. A felhasználók továbbra is feldolgozhatnak egy olyan sorozatszámot, amely eltér az eredetileg eladott sorozatszámtól.

A **Egyesített visszaküldés-feldolgozási élmény a pénztárban** funkció bekapcsolását követően a sorozatszámok ellenőrzésének bekapcsolásához egy szervezetben válassza a **Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Commerce paraméterek** lehetőséget a Commerce központban. A **Készlet** lapon az **Üzletkészlet műveletei** gyorslapon állítsa a **Sorozatszámok ellenőrzésének engedélyezése a pénztári visszatérítéseknél** lehetőséget **Igen** értékre.

## <a name="process-returns-for-serialized-items-in-pos"></a>Szerializált cikkek visszaküldésének feldolgozása a pénztárban

Ha a **Sorozatszámok ellenőrzésének engedélyezése a pénztári visszatérítéseknél** beállítás **Igen** beállításra lett állítva,amikor sorozatszámmal szabályozott cikk visszaadása történik a pénztáron keresztül, a felhasználó megadhatja a visszáru sorozatszámát a **Visszáru-termékek** lap részletek ablakában. Ha a megadott sorozatszám nem egyezik meg az értékesítési tranzakcióhoz tartozó eredeti sorozatszámmal, a felhasználó figyelmeztető üzenetet kap. Az alkalmazás azonban nem akadályozza meg, hogy a felhasználó továbbra is feladja a visszárut.

> [!NOTE]
> A pénztár jelenleg csak olyan visszárusorok sorozatszámának érvényesítését támogatja, amelyekben az eredeti rendelt mennyiség nem egynél több. Ha az eredeti értékesítésirendelés-sor nem a pénztár csatornában jött létre, és az adott értékesítési sorban szerializált cikkhez rendelt mennyiség egynél több, akkor a cikk nem küldhető vissza megfelelően a pénztári terminálon keresztül.

## <a name="additional-resources"></a>További erőforrások

[Visszatérítések létrehozása a pénztárban](POS-returns.md)
