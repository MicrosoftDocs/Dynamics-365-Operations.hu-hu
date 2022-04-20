---
title: Készletláthatóság bővítményének áttekintése
description: Ez a téma elmagyarázza, hogy mi a Készletláthatóság, és ismerteti a funkcióit.
author: yufeihuang
ms.date: 03/18/2022
ms.topic: overview
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9eb8a135d2415c867c746a1c40a80cdb84819c0e
ms.sourcegitcommit: d475dea4cf13eae2f0ce517542c5173bb9d52c1c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/05/2022
ms.locfileid: "8547901"
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

## <a name="feature-highlights"></a>A funkció újdonságai

### <a name="get-a-global-view-of-real-time-inventory"></a>Valós idejű készlet globális nézetének bejezése

A készlet láthatósága gondoskodik arról, hogy mindig a legfrissebb készletmennyiségek elérést biztosítják az összes csatornában, helyen és raktárban. A használat legnagyobb előnye a napi üzemeltetési tevékenység támogatása lesz, amikor készletrekordokat kell beszereznie. A tényleges aktuális készlet, az eladott mennyiségek és a beszerzett mennyiségek mind a dobozon ki vannak adva. Szükség szerint konfigurálhat más fizikai készletmékékeket is (például visszaküldött, karanténba helyezett és feladott adatokat), hogy valós időben meg tudja kapni ezeket az adatokat. A készlet láthatósága a több milliós készletváltozási álláshelyek hatékony feldolgozására képes. Attól függően, hogy milyen időközönként történt az adatok feladása, ezek összesítve is lehetnek, és a szolgáltatás utolsó készletmennyiségében is azonnal, másodpercenként vagy percenként is tükröződhet. A további tudnivalókat lásd [a Készlet láthatósága nyilvános API-kban](inventory-visibility-api.md).

### <a name="soft-reservation-to-avoid-overselling-across-all-order-channels"></a>Soft foglalás az összes rendelési csatorna túlcsatolásának elkerülése érdekében

Az *soft foglalások segítségével* meghatározott mennyiségeket lehet hozzárendelni vagy megjelölni a rendelés vagy az igény teljesítése érdekében. Az egyszerű foglalás nem befolyásolja a tényleges készletet, de levon a foglalásra elérhető készletmennyiségből, *és* frissített mennyiséget biztosít a jövőbeli rendelés teljesítéséhez. Ez a funkció akkor lesz hasznos, ha az értékesítési kérések vagy rendelések a vállalatnál egy vagy több olyan csatornából vagy adatforrásból jönnek létre, amelyek kívül vannak a rekordrendszerben található vállalati erőforrás-tervezési (ERP) rendszeren.

Ha nem használ kötetlen foglalásokat a Készletáttekintő szolgáltatásban, akkor ki kell várnia, amíg az ERP rendszer szinkronizálja és feldolgozja a rendelést, hogy a tényleges készletmennyiség frissítését le tudja kapni. Ennek a folyamatnak általában nagy késése van. Az értékesítési csatornákban azonban az értékesítési kérések és rendelések generálása esetén azonnal megszabadul a foglalás. Így megelőzhetők a túlárazásos helyzetek, mivel gondoskodnak arról, hogy az ERP rendszer elérése után ne ütközzanak egymással a rendelések. A köte foglalások azt is biztosítják, hogy az összes be ígért rendelést teljesíteni tudja. Ennek megfelelően segítenek teljesíteni a vevői várakozásokat, és karbantartani a vevők hűségét. További információért lásd a [Készletláthatósági foglalások](inventory-visibility-reservations.md) című részt.

### <a name="immediate-response-of-atp-dates-confirmation"></a>Az "Tp" dátumok visszaigazolásának azonnali válasza

Fontos a közeli jövőben tervezett készlet (többek között a készletek, az igények és az tervezett aktuális készletadatok) láthatósága, mert a vállalata számára a következő célok elérését segíti:

- A készletszintek csökkentése a készletkezelési költségek csökkentése érdekében.
- A belső rendelésfeldolgozás megkönnyítése, hogy az értékesítők kiszámíthálják a szállítási és a szállítási dátumokat a megrendelt termékek rendelkezésre állása alapján.
- A következő rendelkezésre álló dátum megtételével gondoskodhat arról, hogy mikor várja meg a vevő a készleten nem elérhető cikk rendelkezésre állát.

Az ígérethez rendelkezésre álló szolgáltatás könnyen használható a napi rendelés teljesítésére. A legfontosabb az, hogy a többi készlet-láthatósági szolgáltatáshoz hasonló az "ATP *" funkció globális és valós idejű*. Ennek megfelelően több ATP számítási képletet is be lehet állítani, hogy a készlet rendelkezésre állására vonatkozó lekérdezések minden üzleti csatornát és adatforrást lefednek. A további tudnivalókat lásd [a Készlet láthatósága aktuális készlet változásának ütemezésében, és ígérethez rendelkezésre áll](inventory-visibility-available-to-promise.md).

### <a name="compatibility-with-advanced-warehouse-management-items"></a>Kompatibilitás a speciális raktárkezelési cikkekkel

A Microsoft gondoskodik a speciális raktárkezelés (WHS) ingyenes integrációjáról, így a raktárkezelési szolgáltatás vevői is élvezhedhetnek a készlet-láthatósági szolgáltatás előnyeiben. A 2022-es Hullám 1. kiadásának (nyilvános betekintő ablak) szerint a készletszolgáltatás támogatja az aktuális raktárkészlet -lekérdezéseket és az ATP-t. A következő hullámban a whs vevők számára támogatott lesz az "soft reservation" és a "allocation" funkció. A további tudnivalókat lásd [a raktárkészlet-készlet cikkekkel kapcsolatos láthatósági támogatásában](inventory-visibility-whs-support.md).

## <a name="licensing"></a>Licenckezelés

A Készlet láthatósága szolgáltatás a következő verziókban érhető el:

- **Készlet láthatósági bővítménye a Microsofthoz Dynamics 365 Supply Chain Management** – az ellátásilánc-kezelés érvényes licenccel rendelkező vállalatok esetén a készlet láthatósága külön licencköltség nélkül érhető el. A mai napon elkezdheti a próbálkozást. A telepítéssel kapcsolatos részletek a Készlet [láthatóságának telepítésével és beállításával kapcsolatban tartalmaznak részletes információkat](inventory-visibility-setup.md).
- **A készlet láthatósági szolgáltatása az anyagjegyzék** egyik összetevője – ez a verzió vagy intelligens rendeléskezelési (IOM) ügyfelekhez, vagy olyan vállalatokhoz áll, amelyek nem használják ERP-rendszerükként az Ellátásilánc-kezelés összetevőt. A licenc része az anyagjegyzékkötegnek. A további tudnivalókat lásd [az Intelligens rendeléskezelés témakörben](/dynamics365/intelligent-order-management/overview).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
