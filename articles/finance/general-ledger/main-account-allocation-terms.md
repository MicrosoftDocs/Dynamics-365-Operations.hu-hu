---
title: Felosztási feltételek
description: Ez a témakör a felosztási feltételek fő számlán történő használatáról nyújt tájékoztatást.
author: rachel-profitt
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 957baba1364fbbd4a51c6f51b0fad5bf8db46680fa97b9d3d0474dc015064609
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776528"
---
# <a name="allocation-terms"></a>Felosztási feltételek

[!include [banner](../includes/banner.md)]

Ez a témakör a felosztási feltételek fő számlán történő használatáról nyújt tájékoztatást. A felosztási feltételek segítségével összegeket oszthat fel több főkönyvi számla kombináció között. Ezek garantáljak azt, hogy a költségek vagy a bevételek a megfelelő objektumot terhelik a könyvelés során.

A fő számlán létrehozott felosztási feltételek határozzák meg, hogy egy bizonylat hány százalékát kell hozzárendelni egy egyforrású fő számlából, illetve a pénzügyi dimenziók kombinációját. Ezenkívül Ön meghatározhatja a cél fő számlát, és azokat a pénzügyi dimenziókat, ahol az összeget fel szeretné osztani. 

Amikor meghatározza a felosztáshoz a forrás pénzügyi dimenzióját, akkor kiválaszthatja, hogy az egyes dimenziók meghatározottak vagy meghatározatlanok-e. A meghatározott azt jelzi, hogy a forrástranzakció pénzügyi dimenziójának meg kell egyeznie a kiválasztott dimenzióval. Ha a meghatározatlan beállítást választja, az azt jelzi, hogy a pénzügyi dimenzió bármely értéke hozzájárulhat egy egyezéshez.

Amikor egy felosztási feltételhez meghatározza a cél főkönyvi számlát, meg kell adnia azt a fő számlát, amelyhez felosztja az összeget. Használhatja ugyanazt a fő számlát, ahová elküldte a forrástranzakciót, vagy akár egy másik fő számlát is. Ha ugyanazt a fő számlát használja, akkor a rekord mentésekor figyelmeztetés jelenik meg. A fő számla meghatározásán kívül meg kell adnia a cél dimenziókat is. Minden dimenziónál megadhatja, hogy meg kívánja-e őrizni a forrás pénzügyi dimenzió értékét vagy módosítja azt. Ha a nem lehetőséget választja, akkor új értéket kell kiválasztania a pénzügyi dimenzióhoz. Ha az igen lehetőséget választja, akkor nincs meghatározva semmilyen további információ, és a feladás során a rendszer az eredeti pénzügyi dimenziókat fogja megtartani.

Nincs korlátozva a fő számlához adható felosztási feltételek száma, azonban a felosztási feltételek felosztási százalékának összege nem haladhatja meg a 100 értéket. Ha az eredeti bizonylat összegének egy része a forrás pénzügyi dimenzióiban marad, akkor 100 százalék alatti felosztásokat is létre lehet hozni. Jogi személy felülbírálásakánt hozzáadhatók felosztási feltételek a fő számlához. Ha megosztott számlatükröt használ, akkor mindegyik jogi személyhez meg kell határozni a felosztási feltételeket. A **Felosztási feltételek** gomb eléréséhez előbb be kell jelölnie a **Felosztás** jelölőnégyzetet a Jogi személy felülbírálása lehetőségnél.

## <a name="allocation-term-example"></a>Példa a felosztási feltételre
Meghatározott egy költséghelyet a 000 számú, CORPORATE nevű szervezethez. Amikor a számlák feladásra kerülnek a közműkiadásokhoz, ehhez a CORPORATE költséghelyhez lesznek kódolva. A vállalat meghatározott egy szabályt, miszerint minden közműkiadást a különálló költséghelyek százalékos értékével kell felosztani. A részleg és az üzleti egység egyéb pénzügyi dimenziói változatlanok maradnak.

Ebben a példában egy új felosztási feltétel jön létre a közműkiadások fő számláján. Egy sor jön létre minden egyes költséghelyhez, amelyben a felosztandó százalék szerepel. Az egyes sorokhoz tartozó forrás pénzügyi dimenziók **Kiválasztási feltételei** **Költséghely**-**specifikusak**, és az érték 000: CORPORATE lehetőségre van állítva. A részleg és az üzleti egység esetében a **Kiválasztási feltételek** **Meghatározatlan** értékűek.

A **Cél főkönyvi számla** gyorslapon a fő számla ugyanarra a közműkiadás számlára lesz állítva, és a **Pénzügyi dimenziók megtartása** lehetőség **Igen** értékű lesz az **Üzleti részleg** és **Részleg** elemnél. A **Pénzügyi dimenziók megtartása** **Nem** értékre lesz állítva a **Költséghely** esetében, és a kiválasztott érték fog vonatkozni a felosztáshoz választott összes költséghelyre. Ha három költséghely van kiválasztva a felosztáshoz, akkor a program három felosztási feltétel rekordját hozza létre. A felosztási feltételek közötti egyetlen különbség a cél főkönyvi számlán megadott költséghely.

## <a name="create-an-allocation-term-on-a-main-account"></a>Felosztási feltétel létrehozása egy fő számlán

1. A **Navigációs ablaktábla** lehetőségben menjen a **Modulok > Főkönyv > Számlatükör > Számlák > Fő számlák** lehetőségre.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A **Jogi személy felülbírálása** gyorslapon válassza a **Hozzáadás** elemet.
4. Válassza a **Vállalat**, majd a **Hozzáadás** lehetőséget.
5. Válassza a **Felosztás** jelölőnégyzetet.
6. Válassza a **Felosztási feltételek** lehetőséget.
7. Válassza a **Szerkesztés** lehetőséget az alapértelmezett rekord módosításához vagy az **Új** elemet a rekord hozzáadásához.
8. A **Százalék** mezőbe írja be a felosztani kívánt bizonylat-tranzakciók százalékát.
9. A **Forrás pénzügyi dimenzió** gyorslap egyes pénzügyi dimenzióinak **Kiválasztási feltételei** közül válasszon ki egy lehetőséget.
    - Ha a **Meghatározott** lehetőséget választja, akkor a jobb oldali legördülő listából válassza ki a pénzügyi dimenzió értékét.
    - Ha **Meghatározatlan** lehetőséget választja , akkor a pénzügyi dimenzióhoz nem szükséges további információt megadni.
10. A **Cél főkönyvi** számla gyorslap **Számlához** mezőben válassza ki a fő számlát, amelybe fel szeretné osztani a bizonylattranzakció százalékát.
11. A pénzügyi dimenziók **Forrás pénzügyi dimenziók megtartása** elemben válasszon egy lehetőséget.
    - Ha a **Nem** lehetőséget választja, akkor válassza ki azona pénzügyi dimenzió értékét a legördülő listából, ahol a bizonylattranzakciót fel szeretné osztani.
    - Ha az **Igen** lehetőséget választja, akkor nincs szükség további információkra. A rendszer az eredeti bizonylaton szereplő értéket fogja megtartani a felosztás feladásakor.
12. Ismételje meg a 7–11. lépést minden további felosztásnál. A felosztások összege a **Teljes százalék** mezőben szerepel. Ez az összeg nem lehet nagyobb mint 100.
13. Zárja be az összes oldalt.

>[!NOTE] 
> A kiválasztott felosztás másolásához igény szerint használhatja a **Másolás** gombot is.

Amikor egy fő számlához felosztási feltétel jön létre, a rendszer automatikusan felad egy új bizonylatot, amikor egy olyan bizonylatot adnak fel, amely megfelel a felosztási feltételekben szereplő forrás pénzügyi dimenzióinak.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]