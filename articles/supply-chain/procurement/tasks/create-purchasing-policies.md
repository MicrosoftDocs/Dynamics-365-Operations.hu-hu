---
title: Beszerzési irányelvek létrehozása
description: Ez a cikk bemutatja, hogyan lehet beszerzési irányelveket létrehozni a beszerzéssel kapcsolatos üzleti folyamatoknak megfelelően.
author: GalynaFedorova
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicyParameters, SysPolicy, RequisitionPurposeRule
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a8d42eaf22730f572e2733dec4318e5e4603d74
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2022
ms.locfileid: "9732699"
---
# <a name="create-purchasing-policies"></a>Beszerzési irányelvek létrehozása

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogyan lehet beszerzési irányelveket létrehozni a beszerzéssel kapcsolatos üzleti folyamatoknak megfelelően. A beszerzési irányelvek létrehozása előtt, be kell állítania a beszerzési irányelvek paramétereit. Lehetőség van a beszerzési irányelvek létrehozására, módosítására és visszavonására, azonban nem törölheti a beszerzési irányelvet. Ezt a folyamatot általában egy beszerzési vezető végzi el. Ezt a folyamatot az USMF bemutatócéggel vagy saját adataival is használhatja.


## <a name="set-up-policy-parameters"></a>Irányelv-paraméterek beállítása
1. A navigációs ablaktáblán ugorjon a **Modulok > Beszerzés és forrás> Beállítás > Irányelvek > Beszerzési irányelvek**.
2. A Műveleti panelen válassza a **Paraméterek** elemet.
    - Az irányelvszabályok a szervezet különböző szintjeire vonatkoznak. A szervezeti egységek a szervezeti hierarchiától függően jelennek meg, és a hierarchia azon szintjein, amelyek hozzá vannak rendelve a beszerzés belső ellenőrzésének céljaihoz. Például előfordulhat, hogy a szervezet rendelkezik jogi személyekkel, költséghelyekkel, és részlegekkel, azonban lehet, hogy ezek közül csak néhány rendelkezik a beszerzés belső ellenőrzés hierarchiájának céljával. Alapértelmezés szerint a Vállalat típus szervezete érhető el.  
3. Kattintson az **Irányelvszabály-típus paraméterei** fülre.
4. Válassza ki a **Beszerzés irányelv > Beszerzési igénylés-ellenőrzési szabály** lehetőséget a fa struktúrában.
    - Az irányelvek feldolgozásának elsőbbségi sorrendje az irányelvek szintjén határozható meg. Egyes irányelvtípusok esetén azonban az egyes irányelvszabály-típusok elsőbbségi sorrendje felülbírálható. Például a következőképpen határozhatja meg a beszerzési szabályok elsőbbségi sorrend rendelését: költséghely, részleg, vállalat. A katalógus irányelvszabálya esetén a következő sorrendet kell használnia: részleg, költséghely, vállalat. A Katalógus irányelvszabálynál módosíthatja az elsőbbségi sorrendet. Amikor a dolgozó igénylést hoz létre, a megjelenített katalógust azon irányelvek határozzák meg, amelyeket a rendszer a dolgozó részlegéhez, majd a költséghelyhez, és a vállalathoz rendelt.  
    - Ha a rendszer egynél több szervezeti szintet listázott, akkor a felfelé vagy lefelé nyíl használatával beállíthatja a beszerzési igénylés ellenőrzési szabályának elsőbbségi sorrendjét.  
5. Zárja be a lapot.

## <a name="create-a-new-policy"></a>Új irányelv létrehozása
1. Válassza az **Új** lehetőséget.
2. Írjon be egy értéket a **Név** mezőbe.
3. Írjon egy értéket a **Leírás** mezőbe.
    - Egyetlen beszerzési irányelv csak vonatkozhat egy szervezeti hierarchiára. Például rendelkezhet egy „Földrajzi” és egy „Részleg” elnevezésű hierarchiával, illetve a két hierarchiára vonatkozó, különböző beszerzési irányelvvel.  
    - Válasszon ki egy olyan szervezetet, amelyre vonatkozóan alkalmazni kell az irányelvet.  
4. Kattintson a nyílra a kijelölt szervezet hozzáadásához.
    - Ezen folyamat megismétlésével több szervezetet is hozzáadhat.  

## <a name="add-a-policy-rule"></a>Irányelvszabály hozzáadása
1. Válassza ki az **Igénylésicél-szabály** lehetőséget az **Irányelvszabály típusa** listában.
    - Egy olyan szabályt is létrehozhat, amely az alapértelmezett igénylési célt Felhasználás típusra állítja be, de helyette lehetővé válik a Feltöltés típusa lehetőség kiválasztása.  
2. Válassza ki az **Irányelvszabály létrehozása** lehetőséget.
3. Válassza ki az **Igen** lehetőséget a **Kézi felülbírálás engedélyezése** mezőben.
4. Válassza **Bezárás** lehetőséget.
    - Most beállíthatja az egyéb irányelveket a beszerzési irányelvekhez. Jegyezze meg, hogy egy irányelvszabály-típus nem rendelkezhet olyan átfedő szabályokkal, amelyek egyaránt aktív állapotban vannak az egyetlen beszerzési webhelyen.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
