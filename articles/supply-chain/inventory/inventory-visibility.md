---
title: Készletláthatóság bővítményének áttekintése
description: Ez a cikk bemutatja a készlet láthatóságát, és leírja annak funkcióit.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: dd790bcaada0c1a05e46b4edacaa31fc4e15be92
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762807"
---
# <a name="inventory-visibility-add-in-overview"></a>Készletláthatóság bővítményének áttekintése

[!include [banner](../includes/banner.md)]

A készlet láthatósági bővítménye (*más* néven a készlet láthatósági szolgáltatása) független és nagy mértékben skálázható mikroszolgáltatást biztosít, amely lehetővé teszi a tényleges készlet változásának feladását és a láthatósági követést az összes adatforrásra és csatornára. Ez a platform lehetővé teszi a globális készlet kezelését a következő (de nem csak) a következő listát tartalmazó funkciók használatával:

- Központilag nyomon követheti a legutóbbi készletállapotot (például az aktuális készletet, a rendelt, a beszerzett, az átszállítást, a visszahelyezést és a karanténba helyezett cikkeket) az összes adatforrás, raktár és hely között azáltal, hogy összekapcsolja az Ellátásilánc-kezelés és a külső logisztikai adatforrásokat (például rendeléskezelő rendszereket, külső vállalat erőforrás-tervezési \[ERP\] rendszereit, a \[pénztár POS\] rendszereit és a raktárkezelési rendszereket) a Készletáttekintő szolgáltatáshoz.
- Az aktuális készlet rendelkezésre állásának és hiányának lekérdezése, valamint azonnali válaszok lekérdezése a Készlet láthatósága szolgáltatás közvetlen hívásával.
- Kerülje a túlfedezést, különösen ha az igény különböző csatornákból érkezik, mivel a készlet-láthatósági szolgáltatásban kötetlen foglalásokat hoz létre.
- A ígért rendelések és a vevői várakozások jobb kezelése pontos, aktuális vagy következő elérhető dátumokkal, így az ígérethez rendelkezésre álló mennyiségekkel (ATP) szolgáltatás kiszámíthatja a várható rendelésteljesítési dátumokat.

## <a name="extensibility"></a>Bővíthetőség

A Készlet láthatósága szolgáltatás nagy mértékben extensible, mert az adatbevitel és -kimenet nem korlátozható a Microsoft-alkalmazásokra. Külső rendszerek a RESTful alkalmazásprogramozási felületeken (API-kon) keresztül is elérhetik a szolgáltatást. Az Ellátásilánc-kezelés adatforráshoz és dimenziókhoz megadott, a készlet-láthatósági funkciókat több külső fél rendszerével is integrálhatja úgy, hogy további adatforrásokat, készletállapot-intézkedéseket (*más* néven fizikai intézkedéseket a készlet láthatósági szolgáltatásában) és készletdimenziókat hoz létre a konfigurációs alkalmazáson keresztül. Ily módon egyszerre lekérdezheti és módosíthatja a több adatforrást és az előre definiált készletdimenziókat.

Ezenkívül, mivel a készlet láthatósága Microsoft Dataverse épül, az adatai felhasználhatók az adatok építésre és integrációra Power Apps is. Az üzleti követelményeknek Power BI megfelelő testreszabott irányítópultok létrehozására is használható.

## <a name="scalability"></a>Skálázhatóság

A Készlet láthatósága szolgáltatás az adattérfogattól függően skálázható felfelé vagy lefelé. A skálázhatósági tapasztalat elsősorban problémamentes, és a Microsoft platformcsapata által végzett, a tranzakciós adatok mennyiségének automatikus észlelése és értékelése alapján.

Az alábbi ábra a készlet láthatósági architektúráját mutatja be.

[<img src="media/inventory-visibility-architecture.png" alt="Inventory Visibility architecture." title=" A készlet láthatósági architektúrája" width="720" />](media/inventory-visibility-architecture.png)

## <a name="feature-highlights"></a>A funkció újdonságai

### <a name="get-a-global-view-of-real-time-inventory"></a>Valós idejű készlet globális nézetének bejezése

A készlet láthatósága gondoskodik arról, hogy mindig a legfrissebb készletmennyiségek elérést biztosítják az összes csatornában, helyen és raktárban. A használatának legnagyobb előnye a napi üzemeltetési tevékenység támogatása lesz, amikor készletrekordokat kell beszereznie. A tényleges aktuális készlet, az eladott mennyiségek és a beszerzett mennyiségek mind a dobozon ki vannak adva. Szükség szerint konfigurálhat más fizikai készletmékékeket is (például visszaküldött, karanténba helyezett és feladott adatokat), hogy valós időben meg tudja kapni ezeket az adatokat. A készlet láthatósága a több milliós készletváltozási álláshelyek hatékony feldolgozására képes. Attól függően, hogy milyen időközönként történt az adatok feladása, ezek összesítve is lehetnek, és a szolgáltatás utolsó készletmennyiségében is azonnal, másodpercenként vagy percenként is tükröződhet. A további tudnivalókat lásd [a Készlet láthatósága nyilvános API-kban](inventory-visibility-api.md).

### <a name="central-inventory-adjustment"></a>Központi készlet helyesbítése

A készlet láthatósága lehetővé teszi, hogy a külső rendszerek felhívják API-ját a készletváltozások feladása érdekében. A módosítások azonnal ki lesznek hatnak a készlet láthatóságában. Ebből levonja a program az aktuális készletet.

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Soft foglalás az összes rendelési csatorna túlcsatolásának elkerülése érdekében

Az *soft foglalások segítségével* meghatározott mennyiségeket lehet hozzárendelni vagy megjelölni a rendelés vagy az igény teljesítése érdekében. Az egyszerű foglalás nem befolyásolja a tényleges készletet, de levon a foglalásra elérhető készletmennyiségből, *és* frissített mennyiséget biztosít a jövőbeli rendelés teljesítéséhez. Ez a funkció akkor lesz hasznos, ha az értékesítési kérések vagy rendelések a vállalatnál egy vagy több olyan csatornából vagy adatforrásból jönnek létre, amelyek kívül vannak a rekordrendszerben található vállalati erőforrás-tervezési (ERP) rendszeren.

Ha nem használ kötetlen foglalásokat a Készletáttekintő szolgáltatásban, meg kell várnia, amíg az ERP rendszer szinkronizálja és feldolgozja a rendelést, hogy a tényleges készletmennyiség frissítését meg tudja kapni. Ennek a folyamatnak általában nagy késése van. Az értékesítési csatornákban azonban az értékesítési kérések és rendelések generálása esetén azonnal megszabadul a foglalás. Így megelőzhetők a túlárazásos helyzetek, mivel gondoskodnak arról, hogy az ERP rendszer elérése után ne ütközzanak egymással a rendelések. A köte foglalások azt is biztosítják, hogy az összes be ígért rendelést teljesíteni tudja. Ennek megfelelően segítenek teljesíteni a vevői várakozásokat, és karbantartani a vevők hűségét. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt.

### <a name="immediate-response-of-atp-quantity-and-dates"></a>Az rendelkezésre álló mennyiség és dátumok azonnali válasza

Fontos a közeli jövőben tervezett készlet (többek között a készletek, az igények és az tervezett aktuális készletadatok) láthatósága, mert a vállalata számára a következő célok elérését segíti:

- A készletszintek csökkentése a készletkezelési költségek csökkentése érdekében.
- A belső rendelésfeldolgozás megkönnyítése, hogy az értékesítők kiszámíthálják a szállítási és a szállítási dátumokat a megrendelt termékek rendelkezésre állása alapján.
- A következő rendelkezésre álló dátum megtételével gondoskodhat arról, hogy mikor várja meg a vevő a készleten nem elérhető cikk rendelkezésre állát.

Az ígérethez rendelkezésre álló szolgáltatás könnyen használható a napi rendelés teljesítésére. A legfontosabb az, hogy a többi készlet-láthatósági szolgáltatáshoz hasonló az "ATP *" funkció globális és valós idejű*. Ennek megfelelően több ATP számítási képletet is be lehet állítani, hogy a készlet rendelkezésre állására vonatkozó lekérdezések minden üzleti csatornát és adatforrást lefednek. A további tudnivalókat lásd [a Készlet láthatósága aktuális készlet változásának ütemezésében, és ígérethez rendelkezésre áll](inventory-visibility-available-to-promise.md).

### <a name="preallocate-your-stock-to-important-channels-or-customers-with-inventory-allocation"></a>A készlet előzetes lefoglalása a fontos csatornáknak vagy vevőknek a Készletfelosztás segítségével

A készlet láthatósági felosztási funkciója segítségével megvédheti és becsatlhatja értékes aktuális készletét a fontos csatornák, vevőcsoportok és helyek számára. A készlet felosztása után a készletfelhasználás csak a felosztott készletre korlátozódik, és a készletben maradó mennyiségeket a közeli valós időben levonják a program, hogy tükrözze a felhasználásra rendelkezésre álló mennyiséget. A további tudnivalókat lásd [a Készlet láthatósága készletfelosztásban](inventory-visibility-allocation.md).

### <a name="compatibility-with-wms-items"></a>Kompatibilitás a WMS-elemekkel

A Microsoft úgy tesz, hogy a raktárkezelési folyamatokkal (WMS) való integrációt lehetővé tesz, hogy a WMS-ügyfelek is kihasználják a készlet-láthatósági szolgáltatás előnyeit. A 2022-es Hullám 1. kiadásának (nyilvános betekintő ablak) szerint a készletszolgáltatás támogatja a WMS aktuális készletben található cikklekérdezéseit és az ATP-t. A WMS-vevők számára a következő hullámban az "soft reservation" és a "allocation" funkció lesz támogatott. További információ a WMS-cikkek [készlet láthatósági támogatásában található](inventory-visibility-whs-support.md).

A következő ábra a meglévő funkciók és az adatoknak az adatokba való elhelyezkedésének magas szintű összefoglalását mutatja be.

[<img src="media/inventory-visibility-feature-overview.png" alt="Inventory Visibility feature overview." title=" A Készlet láthatósága funkció áttekintése" width="720" />](media/inventory-visibility-feature-overview.png)

## <a name="licensing"></a>Licenckezelés

A Készlet láthatósága szolgáltatás a következő verziókban érhető el:

- **Készlet láthatósági bővítménye a Microsofthoz Dynamics 365 Supply Chain Management** – az ellátásilánc-kezelés érvényes licenccel rendelkező vállalatok esetén a készlet láthatósága külön költség nélkül érhető el. A készlet láthatóságának alapja Microsoft Power Platform a tárolási Microsoft Power Platform kapacitás és az API-korlátozások. Az ellátásilánc-kezelési licencnek alapértelmezett tárolási és API-kapacitást kell tartalmaznia. Ha több tárolási és API-kapacitásra van szüksége, szakmai licencet is megvásárolhat. Az alapértelmezett API-kiosztásról [és a szakmai licencről a Kéréskorlátok és -foglalások](/power-platform/admin/api-request-limits-allocations)[, valamint licencelés áttekintése nyújt részletes információkat Microsoft Power Platform](/power-platform/admin/pricing-billing-skus). Az alapértelmezett tárolási és API-felosztások segítségével elkezdheti elkezdeni a készlet láthatósági bővítményének használatát a mai napon. A telepítéssel kapcsolatos részletek a Készlet [láthatóságának telepítésével és beállításával kapcsolatban tartalmaznak részletes információkat](inventory-visibility-setup.md). Ha a becsült API- és tárhelyhasználat meghaladja a szokásos felosztást, forduljon az értékesítési képviselőhez, és kérje meg őket, hogy kivételért forduljon a platformcsapathoz.
- **A készlet láthatósági szolgáltatása az anyagjegyzék** egyik összetevője – ez a verzió vagy intelligens rendeléskezelési (IOM) ügyfelekhez, vagy olyan vállalatokhoz áll, amelyek nem használják ERP-rendszerükként az Ellátásilánc-kezelés összetevőt. A licenc része az intelligens rendeléskezelési csomagnak. A további tudnivalókat lásd [az Intelligens rendeléskezelés témakörben](/dynamics365/intelligent-order-management/overview).

## <a name="inventory-visibility-terminology"></a>A készlet láthatóságának fogalmai

A Készlet láthatósága bővítményben való munka közben fontos, hogy jobban megértse a következő fogalmakat és feltételeket:

- **Adatforrás** – az adatforrás jelenti azt a rendszert, amelyből az adatok származik.
- **Dimenziók** – a dimenziók azonosítják a termék jellemzőit. Ezek tárolási dimenziók (például hely vagy raktár) vagy termékdimenziók (például szín, méret vagy stílus) lehet.
- **Fizikai mértékek** – a fizikai mértékek olyan mennyiségek, amelyek különböző készletállapotokat mérnek, mint például az aktuális készlet, a beszerzett, a megrendelt vagy az eladott mennyiség.
- **Számított intézkedések** – a számított intézkedések fizikai intézkedések készlete alapján számolt mennyiségi mutatók. Például a teljes rendelkezésre álló számított *mérték* *·* + *számítása az Elérhető – Megrendelt* – *Eladva értékkel történik.* *·*
- **Partíció** – egy partíció hierarchiát határoz meg a készlet láthatóságának a fogadott adatok elosztására. Jelenleg az alapértelmezett partíció a hely és a hely.
- **Indexhierarchia** – az indexhierarchia részletesebben meghatározza, hogy hogyan szeretné lekérdezni a készletet, és hogy milyen eredményekre van szükség.

Ezekről a feltételekről és fogalmakról a Készlet láthatóságának [konfigurálása oldalon található további tájékoztatás](inventory-visibility-configuration.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
