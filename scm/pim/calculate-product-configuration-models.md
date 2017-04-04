---
title: "Gyakran feltett kérdések a termékkonfigurációs modell számítások"
description: "A cikk konfigurációs modell számítások és ismerteti a megkötések és számításokat is használhatnak."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: 3a82fdb8532c79e33c167c43554a3de7d3061fcb
ms.lasthandoff: 03/31/2017


---

# <a name="calculations-for-product-configuration-models-faq"></a>Gyakran feltett kérdések a termékkonfigurációs modell számítások

A cikk konfigurációs modell számítások és ismerteti a megkötések és számításokat is használhatnak.

A számítások aritmetikai vagy logikai műveletekhez is használhatóak. A termékkonfigurációs modellek kifejezésmegszorításait egészítik ki. A számításokat a **Megszorításon alapuló termékkonfigurációs modell adatai** lapon definiálhatja, majd a kifejezésszerkesztőben építhet hozzájuk kifejezéseket. További információkért lásd: Számítások létrehozása.

## <a name="what-is-a-calculation"></a>Mi a számítás?
A számítás olyan elem, amelyet egy termékkonfigurációs modellben használhat. A számítások kiegészítik a megszorításokat a kívánt termék konfigurálásakor a tizedesértékek használatával az értékek számításához. Ezenkívül a számítások nagyobb elérhető operátorkészlettel rendelkeznek mint a megszorítások.  

A megszorításhoz hasonlóan egy számítás adott összetevővel társítható a termékkonfigurációs modellben, és másik összetevő nem használhatja fel újra, vagy egy másik összetevővel nem osztható meg. Egy fontos különbség azonban a megszorításokhoz képest, hogy a számítások imperatív (egyirányú) jellegűek, míg a megszorítások deklaratívak (kétirányúak). További tudnivalók a megszorításokról: [Kifejezés megszorítások és táblamegszorítások](expression-constraints-table-constraints-product-configuration-models.md).  

A számítás célattribútumból és számítási kifejezésből áll.

## <a name="what-is-a-target-attribute"></a>Mi a célattribútum?
A célattribútum olyan attribútum, amely a számítás eredményét kapja a kifejezésben.  

A következő kifejezésben a célattribútum asztalterítő mérték:  

**Kifejezés:** Ha\[decimalAttribute1 &lt;decimalAttribute2, = True, False\]  

**DecimalAttribute1** a tábla hossza és **decimalAttribute2** az asztalterítőn hossza. A kifejezés **Igaz** értéket ad ki célattribútumnak, ha a **decimalAttribute2** nagyobb vagy egyenlő a **decimalAttribute1** értékénél. Ellenkező esetben a kifejezés **Hamis** eredményt ad. Így a asztalterítő mérete elfogadható, ha a hossza egyenlő vagy meghaladja az asztal a hosszát.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>Milyen attribútum típusok állíthatók be a célattribútumokhoz?
A termékkonfiguráló által támogatott összes attribútumtípus megadható a célattribútumokhoz, kivéve rögzített lista nélküli szöveg.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>Korlátozhatja a célattribútum értéke a bemeneti attribútumok értékeit a számításban?
Nem, a célattribútum értéke nem tudja korlátozni a bemeneti attribútumok értékeit, mert a számítások egyirányúak. Így a célattribútum értéke a megadott bemeneti attribútumok értékét érintő változásokhoz képest meg van határozva, de a cél értékének változása nem befolyásolja a bemeneti attribútumok értékét. Ez a viselkedés eltér a megszorítások szokásos működésétől. A megszorítások mindkét irányban hatással vannak.

### <a name="example"></a>Példa

A következő kifejezés kiszámításának célja a tápkábel hossza, és a bemeneti érték szín:  

**Kifejezés:**\[Ha színes == "Zöld", 1.5, 1.0\]  

A cikk konfigurálása során a tápkábel hossza értékre van állítva **1,5** Ha **zöld** színes attribútum értékeként. Ha bármely más színt ad meg, a hossz **1,0** lesz. Azonban mivel a számítások egyirányúak, a számítás nem fogja átállítani a színattribútum értékét **zöldre** olyankor, ha **1,5** értékű hosszúságot ad meg.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>Mi történjen, ha a számítás egész szám típusú célattribútummal rendelkezik, de a számítás tizedes számot generál?
Ha egy célattribútum egész szám típusú, de a számítás tizedestörtet ad, akkor a számított eredménynek csak az egész részét adja vissza a rendszer. A tizedestört része törlődik, az eredmény kerekítése nélkül. Így például a 12,70 eredmény 12 értékként jelenik meg.

## <a name="when-do-calculations-occur"></a>Mikor történik számítás?
Számítások akkor fordulnak elő, ha minden beviteli attribútumhoz meg van adva érték.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>Felülírhatja az értéket, amely a célattribútumhoz van kiszámítva?
Felülírhatja az értéket, amely a célattribútumhoz van számítva, kivéve, ha a célattribútum, rejtettre vagy csak olvashatóra van beállítva.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-readonly"></a>A célattribútum rejtett vagy írásvédett beállítása
Rejtett vagy csak olvasható attribútum beállításához kövesse az alábbi lépéseket.

1.  Kattintson a **Termékinformációk kezelése**&gt;**közös**&gt;**termékkonfigurációs modellek**.
2.  Jelölje be az egyik termékkonfigurációs modellt, majd a műveleti ablakban kattintson a **Szerkesztés** gombra.
3.  A **Megszorításon alapuló termékkonfigurációs modell adatai** oldalon válassza ki a célattribútumként használandó attribútumot.
4.  Az **Attribútumok** gyorslapon jelölje be a **Rejtett** vagy az **Írásvédett** opciót.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>Egy számítás az általam beállított értékeket is felülírhatja?
Szám Termék konfigurálása beállított értékek a használt értékek. A számítás, amely a számításban a bemeneti értékek megváltozásakor előfordul nem tudja felülírni az értékeket, amelyeket egy adott attribútumhoz megad.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>Mi történik, ha a számításban eltávolítom a bemeneti értéket?
Ha eltávolít egy bemeneti értéket a számításban, a célattribútum értéke is törlődik.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>Miért jelenik meg hibaüzenet, amely szerint a modell ellentmondásos?
Ez az üzenet jelenik meg, ha a számításban hiba vagy ellentmondás szerepel egy vagy több megszorításban. További tudnivalók a megszorítások ellentmondásairól: [Kifejezés megszorítások és táblamegszorítások](expression-constraints-table-constraints-product-configuration-models.md). Az alábbiakban néhány olyan helyzetet mutatunk be, amelynél hibák léphetnek fel a számításokban:

-   Az érték nulla értékkel történő elosztásakor.
-   Ellentmondás áll fenn az alábbi két elem között:
    -   A lehetséges értékek az attribútumhoz, és ezeket egy megkötés korlátozza.
    -   A számítás által generált érték
-   A számítás által visszaküldött értékek az attribútum tartományán kívül esnek. Ennek egyik példája az egész \[1..10\] számított 0-ra.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>Miért jelenik meg hibaüzenet, annak ellenére, hogy a termékmodellt sikeresen érvényesítettem?
Az ellenőrzésben nem szerepelnek a számítások. Tesztelnie kell a termék konfigurációt, hogy megtalálja a hibákat a számításokban. A termékkonfigurációs modell teszteléséhez kövesse az alábbi lépéseket.

1.  Kattintson a **Termékinformációk kezelése**&gt;**közös**&gt;**termékkonfigurációs modellek**.
2.  Jelölje be az egyik termékkonfigurációs modellt, majd a műveleti ablakban kattintson a **Futtatás** csoport **Teszt** gombjára.



