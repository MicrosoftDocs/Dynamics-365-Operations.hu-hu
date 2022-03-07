---
title: Hogyan lehet beállítani a kiegyenlítő pénzügyi dimenziókat?
description: Ez a témakör a Pénzügyi dimenziók kiegyenlítése funkció beállításával és használatával kapcsolatos beállításokat ismerteti.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: 188c15c4cb0c295a9fcbb08273ddb391fbc29e24
ms.sourcegitcommit: b4c78655f2ab4b0e7ead96dfb9cf087a18014253
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2021
ms.locfileid: "7468940"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>Hogyan lehet beállítani a kiegyenlítő pénzügyi dimenziókat?

[!include [banner](../includes/banner.md)]

Ez a témakör a Pénzügyi dimenziók kiegyenlítése funkció beállításával és használatával kapcsolatos beállításokat ismerteti.

## <a name="symptom"></a>Tünet

A pénzügyi dimenziók kiegyenlítésének beállítása két lehetőséggel lehetséges. Az első lehetőség a **Pénzügyi dimenziók kiegyenlítése** mező használata a **Főkönyv** beállítási oldalon (**Főkönyv \> Főkönyv beállítása \> Főkönyv**). A második lehetőség a **Dimenziók kiegyenlítésének kötelezővé tétele** mezőt a **Pénzügyi dimenziók** oldalon (**Főkönyv > Számlatükör \> Dimenziók \> Pénzügyi dimenziók**). Ez a témakör bemutatja a két lehetőség közötti különbséget.

## <a name="resolution"></a>Megoldás

A szervezetek általában kiegyenlítődő dimenziókat használnak olyan mérleg létrehozásához, amely egyensúlyban van a pénzügyi dimenziók szintjén. Egyik funkció engedélyezése sem képes egyensúlyba hozni feladott, nem egyensúlyban levő dimenziókat. Mindkét funkció engedélyezése előtt manuálisan kell egyenslyba hoznia a mérleget korrekciós bejegyzések megadásával.

Ez a két lehetőség kölcsönösen kizárja egymást. A szervezet által használt beállításnak az üzleti követelményeken kell alapulni. Gyakran hallunk olyan ügyfelekről, akik mind a főkönyvi, mind a pénzügyi dimenzió beállításában meghatározzák a kiegyenlítő dimenziót, majd a szükséges további beállítások egy részét vagy egészét végrehajtják. A pénzügyi dimenziók szintjén létező egyensúlyhiány miatt azonban még mindig nem lehetséges az elszámolás.

Az alábbi szakaszok leírják a két lehetőséget, és bemutatják a beállításokat.

### <a name="ledger--balancing-financial-dimension"></a>Főkönyv – Kiegyenlítő pénzügyi dimenzió

A **Főkönyv** beállítási oldalán található kiegyenlítő dimenzióval lehet engedélyezni az egységközi könyvelést. Ha be szeretné kapcsolni a funkciót, hajtsa végre az alábbi lépéseket.

1. Határozza meg hogy melyik pénzügyi dimenzió lesz a kiegyenlítő dimenzió.

    - Ezzel a funkcióval csak egy pénzügyi dimenziót választhat ki kiegyenlítő dimenzióként.
    - Ne válassza ki még a dimenziót a **Főkönyv** beállítási oldalán.
    - Győződjön meg róla, hogy a mérleg már egyensúlyban van a kiválasztott pénzügyi dimenziónál.

2. Frissítse a kiegyenlítő pénzügyi dimenzió számlastruktúráját.

    - A kiegyenlítő pénzügyi dimenziónak szerepelnie kell az összes, a főkönyvhöz hozzárendelt számlastruktúrában.
    - A pénzügyi dimenzió nem engedélyezi az üres helyeket a számlastruktúrában. Ez a korlátozás gondoskodik arról, hogy a főkönyvbe feladott minden könyvelési bejegyzés tartalmazni fog egy pénzügyi dimenzióértéket. Az üres dimenzió nem érvényes kiegyenlítő dimenziók használata esetén.

3. Az **Automatikus tranzakciók számlái** oldalon (**Főkönyv \> Feladási beállítások \> Automatikus tranzakciók számlái**) adja meg az egységközi terhelési és jóváírási fő számlákat.
4. A **Főkönyv** beállítási oldalon (**Főkönyv \> Főkönyvi beállítás \> Főkönyv**) a **Kiegyenlítő pénzügyi dimenzió** mezőben válassza a kiegyenlítéshez használni kívánt pénzügyi dimenziót.

Ha a kiválasztott pénzügyi dimenzió nincs kiegyenlítve a tranzakciók bevitele és feladása közben, a rendszer automatikusan hozzáadja a könyvelési bejegyzés kiegyenlítéséhez szükséges tartozik vagy követel tételeket a feladás során. Az egységközi tranzakcióhoz tartozó terhelési és jóváírási főkönyvi számlák megjelennek a főkönyv feladott bizonylatán. Ezek nem jelennek meg azonban azokban a naplókban vagy forrásbizonylatokon, amelyekhez a könyvelési tételeket feladták.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>Pénzügyi dimenziók – Dimenziók kiegyenlítésének kötelezővé tétele

Bár a **Pénzügyi dimenziók** oldalon szereplő kiegyenlítő dimenziókat általában az állami szektor vállalatai használják, a funkció nem kapcsolódik egyetlen állami szektorra vonatkozó konfigurációs kulcshoz sem. Mivel a rendszer semmilyen korlátozást nem használ, ezt a funkciót akkor is használhatja, ha a szervezet nem állami szervezet.

Ezt a funkciót jellemzően az állami szektor ügyfélbázisa használja, mivel a feladásdefiníciókat alkalmazni kell az egyes tranzakciók automatikus kiegyenlítéséhez. Nem használja az **Automatikus tranzakciók számlái** oldalon meghatározott egységközi terhelési és jóváírási számlákat a könyvelési tételek automatikus kiegyenlítéséhez. Ha a feladásdefiníciók alkalmazása után egy könyvelési tétel nem kiegyensúlyozott a dimenzió szintjén, akkor a tranzakció nem lesz feladva még akkor sem, ha meg van adva az egységközi tartozik és követel számla.

Gyakran hallunk olyan ügyfelekről, akik mind a főkönyvi, mind a pénzügyi dimenzió beállításában meghatározzák a kiegyenlítő dimenziót. Ebben az esetben a rendszer a pénzügyi dimenziók funkciót használja. A pénzügyi dimenziók szintjén a kiegyenlítő dimenziók beállítása elsőbbséget élvez a feladás során. A feladás sikertelen lesz, ha a feladásdefiníció nem hoz létre kiegyensúlyozott könyvelési tételt a pénzügyi dimenzió szintjén.

A következő lépések szerint kapcsolhatja be a kiegyenlítő dimenziók használatát a pénzügyi dimenziók szintjén.

1. Határozza meg hogy melyik pénzügyi dimenziók lesznek a kiegyenlítő dimenziók.

    - Egynél több pénzügyi dimenziót is be lehet állítani kiegyenlítő dimenzióként.
    - Még ne állítsa be a pénzügyi dimenziókat, amelyek egy tranzakció kiegyenlítéséhez lesznek szükségesek a **Pénzügyi dimenziók** oldalon.

2. A szervezet által használt naplók vagy forrásdokumentumok minden típusára definiálja a feladásdefiníciókat. A feladásdefiníciók „egyeztetési feltételként” használják fel egy fel nem adott naplóból vagy forrásdokumentumból származó főkönyvi számlákat. A feladásdefiníció ezt követően visszaadja a „létrehozott bejegyzéseket”, amelyekből a könyvelési tételek válnak. Ha a feladásdefiníció helyesen van beállítva, a generált bejegyzés tartalmazza az egyeztetési feltételeknek megfelelő főkönyvi számlákat és további számlákat, amelyekkel a könyvelési tétel a dimenzió szintjén kiegyenlíthető. További információkért lásd: [A feladási típusok](posting-definitions.md). 
   
   A feladásdefiníciók nem támogatottak minden típusú tranzakciónál. Például a feladásdefiníciók nem definiálhatók az általános naplón vagy a tárgyieszköz-naplón keresztül bevitt tranzakciókhoz. Ha egy naplóhoz vagy forrásdokumentumhoz nem lehet feladásdefiníciót megadni, akkor a tranzakciót manuálisan kell kiegyenlítani a pénzügyi dimenzióértékkel. Ha például egy általánosnapló-bejegyzés készül, és a Részleg dimenzió a kiegyenlítő dimenzió, gondoskodnia kell arról, hogy minden részlegérték egyensúlyban legyen.  Ha a dimenzió nincs kiegyenlítve mindegyik részlegértéknél, a bizonylat addig nem adható fel, amíg az egyensúlyhiányt nem korrigálja manuálisan egy egységközi tartozik vagy követel érték bizonylathoz való hozzáadásával. 

    > [!IMPORTANT]
    > Ha túl sok tranzakciót kell manuálisan kiegyenlíteni, **ne** használja a kiegyenlítő dimenzió funkciót a **Pénzügyi dimenziók** oldalon. Ehelyett használja a kiegyenlítő dimenzió funkciót a **Főkönyv** beállítási lapján.

3. A feladásdefiníciók meghatározása után a pénzügyi dimenziókat meg lehet jelölni a kiegyenlítéshez szükségesként.

A tranzakciók megadása és feladása közben a feladásdefiníciókat a rendszer meghívja a könyvelési bejegyzések meghatározása érdekében. Ha a pénzügyi dimenziók nincsenek kiegyenlítve, akkor az ellenőrzés a könyvelési tételek meghatározása után történik. Ha a pénzügyi dimenziók nincsenek kiegyenlítve, a tranzakció nem lesz feladva, és egy üzenet jelenik meg, amely szerint a tartozik tételek nem egyenlők egy adott dimenzió jóváírásaival.
