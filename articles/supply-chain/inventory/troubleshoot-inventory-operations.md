---
title: Készletműveletekkel kapcsolatos hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani a készletműveletek használata során felmerülő problémákat.
author: sherry-zheng
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 1198bc12830afa2ae2c5eb8e77413a9d8ef70c625823f676ab1965ff250c2443
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730393"
---
# <a name="troubleshoot-inventory-operations"></a>Készletműveletekkel kapcsolatos hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet javítani a készletműveletek használata során felmerülő problémákat.

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Nem található a "Munkafolyamat" legördülő párbeszédpanel a készletnaplókhoz.

### <a name="issue-description"></a>Probléma leírása

A naplóoldalon nem található a **Munkafolyamat** legördülő párbeszédpanel, vagy a kapcsolód munkafolyamat-műveletek nem érhetők el.

Ez a probléma három okból fordulhat elő, az alábbi alszakaszok szerint.

### <a name="issue-resolution-1"></a>Probléma 1. megoldása

Ha a probléma az összes felhasználóra vonatkozik, akkor előfordulhat, hogy a jóváhagyási munkafolyamat nincs hozzárendelve a naplónévhez. Egy hiba javításához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés &gt; Beállítás &gt; Naplónevek &gt; Készlet** pontra.
1. A beállítások megnyitásához válassza ki a napló nevét a lista paneljén.
1. Az **Általános** gyorslapon állítsa a **Jóváhagyási munkafolyamat** beállítást *Igen* értékre. Kattintson az **Igen** gombra, ha a rendszer a módosítás megerősítését kéri.
1. A **Munkafolyamat** mezőben válassza ki azt a munkafolyamatot, amelyet a kiválasztott naplónévhez használni szeretne.

### <a name="issue-resolution-2"></a>Probléma 2. megoldása

Ha a munkafolyamat egyedi kódot használ, problémák léphetnek fel a rendszer frissítése után. Például a napló munkafolyamatában a **Küldés** gomb szürke színnel jelenhet meg, így nem jelölheti ki a küldés jóváhagyásához.

Ha a **Küldés** gomb szürke színű, lehet, hogy testre szabták munkafolyamatot, ami azt jelenti, hogy a munkafolyamat módszere – a `canSubmitToWorkflow()` a `FormDataUtil` értékben – meg lett hosszabbítva. A probléma megoldásához módosítsa a `canSubmitToWorkflow()` módszer hosszabbításának módját, hogy a következő példában szereplő szerkezetet használja.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a>Probléma 3. megoldása

Ha a probléma csak néhány konkrét felhasználóra vonatkozik, akkor lehet, hogy ezeknek a felhasználóknak nincsenek meg a készletnaplókban a munkafolyamat-műveletek futtatásához szükséges biztonsági jogosultságai. Ellenőrizze, hogy minden érintett felhasználó rendelkezik-e a *Készletnapló munkafolyamatának karbantartása* biztonsági jogosultsággal. Alapértelmezés szerint ez a jogosultság ugyanolyan nevű feladathoz van hozzárendelve, és ez a feladat a *Raktári dolgozó* és *Raktárvezető* szerepkörre vonatkozik.

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a>A készletnapló rendszer által zárolt állapotú marad, és a munkafolyamat kötegelt feladata nem működik.

### <a name="issue-description"></a>Probléma leírása

Valamelyik készletnaplót valamilyen művelet zárolta, ezért nem lesz kiadva. Ha például a feladás során (amely rendszerzárolási művelet) ismeretlen hiba történik, a napló zárolt állapotú maradhat a rendszerben. Ebben az esetben a munkafolyamat munkatétel-kezelője hibát jelez, miközben zárolja az ellenőrzést.

### <a name="issue-resolution"></a>Probléma megoldása

Jelentkezzen be a Supply Chain Management SQL Server példányába, és ellenőrizze, hogy az **InventJournalTable.SystemBlocked** beállítása *1*-e. Ha igen, győződjön meg róla, hogy a napló nem lehet zárolt állapotú, majd állítsa vissza az **InventJournalTable.SystemBlocked** értékét *0*-ra.

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a>A készletnapló munkafolyamata soha nem befejezett, és a napló nem szerkeszthető és nem is feladható.

### <a name="issue-description"></a>Probléma leírása

A napló-jóváhagyási munkafolyamat elküldése után a munkafolyamat feldolgozása leáll, és a naplókat nem lehet szerkeszteni és feldolgozni.

### <a name="issue-resolution"></a>Probléma megoldása

Több oka is lehet annak, hogy miért nem fejeződött be a munkafolyamat feldolgozása. Ellenőrizze a következő problémákat:

- Ugorjon a **Készletkezelés &gt; Beállítás &gt; Készletkezelési munkafolyamatok** elemhez, és tekintse át az érintett munkafolyamat konfigurációját. A további tudnivalókat lásd: [Készletnapló-jóváhagyási munkafolyamatok](inventory-journal-workflow.md).
- Lehet, hogy a munkafolyamat kivételt vagy hibát észlelt. Tekintse át az érintett munkafolyamat munkatétel-előzményeit, és ellenőrizze, hogy tartalmaz-e olyan alkalmazáshibát, amely megszakítja a munkafolyamatot.
- A készletnapló csak jóváhagyás után frissíthető vagy szerkeszthető. Ha a visszahívás aktív, megpróbálhatja visszahívni a naplót. A munkafolyamat kötegelt feladatának végrehajtása több okból is felfüggeszthető. Ezeknek az okoknak egy részét a munkafolyamat-keretrendszer problémája okozhatja.

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a>A készletnapló munkafolyamat-feltételei csak a napló szintjén érvényesek, a sor szintjén nem

### <a name="issue-description"></a>Probléma leírása

Ezt a problémát például akkor tapasztalhatja, ha a költség összegére egy készletnapló-munkafolyamati feltételt próbál beállítani. Úgy állítsa be a feltételt, hogy az 1. lépés csak akkor fusson, ha a költség összege kisebb, mint 100. Ezután úgy állítson be egy másik feltételt, hogy az 2. lépés csak akkor fusson, ha a költség összege több, mint 100 vagy azzal egyenlő. Ezután a munkafolyamat futtatásakor a munkafolyamat előzményei csak egy sort mutatnak, és az első feltétel kiértékelése mindig *igaz*, függetlenül az elküldött értéktől.

### <a name="issue-workaround"></a>Probléma megoldása

A jelenlegi verzióban a készlet munkafolyamat-feltételei csak a napló szintjén érvényesek, a sor szintjén nem. Ez szándékosan van. Azt ajánljuk, hogy csak naplószintű attribútumokkal állítsa be a feltételi kritériumokat.

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a>Az Aktuális listaoldal szűrőablaka nem úgy szűri az eredményeket, ahogyan azt elvárom.

### <a name="issue-description"></a>Probléma leírása

Az **Aktuális lista** oldal szűrőablakának szűrői nem úgy szűrik az eredményeket, ahogyan azt ön elvárja.

### <a name="issue-resolution"></a>Probléma megoldása

Ez szándékosan van.

Az **Aktuális lista** lap egy részletes aktuális készlettáblából van összeállítva, amely az összes elérhető dimenziót tartalmazza. A lap listája azonban összesítés jellegű. Így előfordulhat, hogy a forrástábla sorait egyesíti a megjelenített dimenzióknak megfelelő értékek összesítésével.

A szűrők ablaktáblán beállított szűrők a forrástáblára vonatkoznak, nem az összesített listára. Ez a viselkedés időnként nem várt eredményt hoz, ahogy [ezek a példák](inventory-on-hand-list.md#examples) mutatják.

Azonban a  [rácsban megadott szűrők](inventory-on-hand-list.md#grid-filters) *nem* alkalmazandók az összesített listára. Ezek a szűrők egyaránt tartalmazzák a rács felső részén található GyorsSzűrő, valamint az egyes oszlopok fejlécének szűrőjét.

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>Az egység- és egységmennyiség nem megfelelően működik a készletnaplóban.

### <a name="issue-description"></a>Probléma leírása

Ha készletnapló egységekkel és mennyiségekkel dolgozik, a következő problémák valamelyike vagy mindkettő előfordulhat:

- Ha a kiadott termékhez be van állítva az átváltás egysége, akkor nem látja a készletnaplóban az egységeket és az egységmennyiségeket, és nem lehet benne módosítani az egységet.
- A készletnaplóban a **Mennyiség** és az **Egység** mezők láthatók, az **Egység mennyisége** mező azonban nem. Ha módosítja az egységet, adjon meg egy mennyiséget, majd adja fel a naplót – a naplóban továbbra is látható az adott mennyiség eredeti mértékegysége.

### <a name="issue-resolution"></a>Probléma megoldása

Ezen hiba javításához kövesse az alábbi lépéseket.

1. A **Szolgáltatáskezelés** munkaterületen győződjön meg arról, hogy be van kapcsolva a *Mértékegység és az egységmennyiség használata a készletnaplókban* funkció. Ez a funkció hozzáadja az **Egység** és az **Egységmennyiség** mezőket a naplóhoz.
1. A funkció bekapcsolás után használja a következő módon a **Mennyiség**, **Egységmennyiség** és **Egység** mezőket:

    - **Mennyiség** – Határozza meg a mennyiséget a kiadott termékre meghatározott alapértelmezett egység használatával. Ugyanakkor maga az alapértelmezett egység nem jelenik meg itt. Ha az alapértelmezett egység és az **Egység** mezőben kiválasztott egység között átváltás van beállítva, akkor a **Mennyiség** mező automatikusan frissül az **Egységmennyiség** és az **Egység** mezőben megadott beállításoknak megfelelően.
    - **Egységmennyiség** – Adja meg a mennyiséget az **Egység** mezőben kiválasztott egység használatával.
    - **Egység** – Válassza ki az **Egységmennyiség** mezőben szereplő értékre alkalmazandó egységet.

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>A következő hibaüzenet jelenik meg: "A termékraktározási egységben a tizedesjegyek maximális száma 0."

### <a name="issue-description"></a>Probléma leírása

Készlettranzakció vagy készletfoglalás feladása során a következő hibaüzenet jelenik meg: "A termékraktározási egységnél a tizedesjegyek maximális száma 0."

Ez a probléma akkor fordul elő, ha a készlettranzakció mennyisége olyan tizedesértékként van megadva, amely a mező által támogatott pontosság szintje alatti. Például egy készlettranzakcióhoz *0,5* mennyiséget adott meg, de csak egész számok támogatottak. Ezért az értéknek *1-nek* kell lennie *0,5* helyett.

### <a name="issue-resolution"></a>Probléma megoldása

1. Futtassa a következő parancsfájlt az SQL Server-példányon a készlettranzakciók mennyiségének kerekítéséhez. Ez a parancsfájl korrigálja az **inventTrans** táblában található értékeket.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Futtassa az adott anyagon az aktuális konzisztencia-ellenőrzést, ha a **hibajavítás** beállítás be van kapcsolva. Ez az ellenőrzés korrigálja az **inventSum** táblában található értékeket.

> [!IMPORTANT]
> Kifejezetten ajánljuk, hogy a környezetnek megfelelően körültekintően szerkessze a parancsfájlt, tesztelje tesztkörnyezetben, majd ellenőrizze az így kapott adatokat, mielőtt éles környezetben futtatja a parancsfájlt.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]