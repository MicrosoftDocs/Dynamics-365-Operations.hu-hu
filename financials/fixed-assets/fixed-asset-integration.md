---
title: "Tárgyieszköz-integráció"
description: "A tárgyi eszközök integrálhatók a főkönyvvel, a készletkezeléssel, a kinnlevőségekkel és a követelésekkel. A tárgyi eszközök emellett a beszerzési rendelésekkel integrálva is beállíthatók."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 06559cba9e0a19e2530e8cf8559d8b7b272bbf16
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="fixed-assets-integration"></a>Tárgyieszköz-integráció

[!include[banner](../includes/banner.md)]


A tárgyi eszközök integrálhatók a főkönyvvel, a készletkezeléssel, a kinnlevőségekkel és a követelésekkel. A tárgyi eszközök emellett a beszerzési rendelésekkel integrálva is beállíthatók.

<a name="general-ledger"></a>Főkönyv
--------------

A Főkönyvön belül a tárgyi eszközök értékének összegzése általában több, a pénzügyi jelentések készítéséhez szükséges fő számlán történik. Azonban a **Tárgyi eszközök** lapon számos tárgyieszköz-rekordot létrehozhat. Ezek a rekordok tartalmazhatják például árat, az értékcsökkenést és az értékelést. Tárgyieszköz-tranzakció feladása esetén mindig a megfelelő fő számlát frissíti. A tárgyi eszközök fő számláin mindig a tárgyi eszközök frissített értékei láthatók.

A **Tárgyi eszköz feladási profilja** lapon határozhatja meg azokat a fő számlákat, amelyekre a tárgyi eszközök tranzakciói feladhatók. Kiválaszthatja a tárgyieszköz-tranzakciók azon típusait, amelyek az egyes fő számlára kerülnek feladásra. Attól függően, hogy milyen részletességgel szeretné szerepeltetni a tárgyi eszközöket a főkönyvben, a tárgyi eszközök fő számláinak számos kombinációját hozhatja létre a tárgyi eszközökhöz. A fő számlák tranzakciótípusokon, könyveken és más fő számlákon alapulhatnak.

## <a name="inventory-management"></a>Készletgazdálkodás
A tárgyi eszközök készletnaplóiban rögzítheti a beszerzett tárgyi eszközöket, amelyeket a jogi személy saját létre állított elő vagy épített meg. Egy beszerzésként vagy egy beszerzés részeként készletcikkeket mozgathat át tárgyi eszközökre. 

Az eszközök beszerzési rendelések útján is beszerezhetők. Amikor a beszerzési rendelések tárgyi eszközként megjelölt készletcikkeket tartalmaznak, a **Tárgyi eszközök paraméterei** lapon a **Beszerzés modulból való tárgyieszköz-beszerzés engedélyezése** opció határozza meg, hogy a számla feladásakor történik-e beszerzés feladása a tárgyi eszközre vonatkozóan. A tárgyi eszközök beszerzésének készletre kifejtett hatása a jogi személy beállításától függ. 

Ha egy készletcikk tárgyieszköz-beszerzéssé válik (a készletnaplón, beszerzési rendelésen vagy beszerzési javaslaton keresztül), akkor a tárgyi eszköz könyvének létrejön egy beszerzési tranzakciója. Ha a könyv beszerzése tartalmaz származtatott könyvet, akkor a származtatott könyvnek is létrejön egy beszerzési tranzakciója. 

A beszerzés feladásakor történő készletcsökkenést a Készletkezelés modulban a **Feladás** lapon megadott feladási szabályok irányítják. Azonban a tárgyi eszközökhöz kapcsolódó számlák feladása nem mindig csökkenti a készletet. Bizonyos esetekben a tárgyi eszközök megvásárlása belső használatra történik. Ilyen például az értékesítési osztály számára megvásárolt hordozható számítógép beszerzése. Ha beszerzési rendelésekkel dolgozik, akkor olyan cikkeket is megadhat, amelyek újraértékesítésre vagy belső használatra is használhatók. 

Ha a cikkcsoportokhoz tartozó tárgyi eszközökhöz megadott kibocsátási és bevételezési számlákat alkalmaz, ugyanazt a készletcikket egyaránt használhatja belső beszerzéshez és továbbértékesítési célú készlethez. 

A belső használatra szánt tárgyi eszközöket a **Tárgyi eszköz bevételezése** számlatípussal kell beállítani. Ez a számlatípust szolgál a tárgyi eszköz bevételezésének nyomon követésére. Szállítói számla feladásakor a tárgyieszköz-bevételezési számlát használja a következő feltételek valamelyikének teljesülése esetén:

-   A számlasor már létező, belső célokra szolgáló tárgyi eszközt tartalmaz.
-   Az **Új tárgyi eszköz?** jelölőnégyzetet a feladott a termékbevételezési sornál kell bejelölni.
-   Az **Új tárgyi eszköz létrehozása** jelölőnégyzetet a szállítói számlasorhoz kell bejelölni.

Az ilyen számla rendszerint költségszámla. A **Tárgyi eszköz bevételezése** számlatípus beállítható cikkcsoporthoz vagy önálló cikkhez is a **Beszerzési rendelés** lap használatával a **Cikkcsoport** vagy a **Feladás** lapokon.

A belső használatra szánt tárgyi eszközöket ehhez hasonlóan a **Tárgyi eszköz kiadása** számlatípussal kell beállítani. Ez a számlatípust szolgál a tárgyi eszköz jogosult számára való kiadásának nyomon követésére. Amikor az eszköz beszerzése beszerzési rendelés használatával történik, a tárgyieszköz-kiadási számla szolgál a tárgyieszköz-terhelési számla ellentételezéseként. Az eszköz beszerzését akkor lehet feladni, amikor megtörténik a szállítói számla feladása, vagy a tárgyieszköz-beszerzés feladása a Tárgyi eszközök naplóban, lehetőleg egy beszerzési javaslat használatával. A **Tárgyi eszköz kiadása** számlatípus beállítható cikkcsoporthoz vagy önálló cikkhez is a **Készlet** lap használatával a **Cikkcsoport** vagy a **Cikkfeladás** lapokon. 

Végső soron a feladáshoz használt fő számlákat, az adott cikkmodellcsoporthoz meghatározott főkönyvi integrációs beállítások határozzák meg. Emellett a használt fő számlák attól is függenek, hogy az eszköz hozzá van-e rendelve a beszerzési rendelési sorához. A számlák az egyes cikkcsoportok feladási profiljaiból vannak származtatva. 
**Megjegyzés:** Ha van készletfoglalás a termékbevételezés feladásakor, nem lehet tárgyi eszközt hozzárendelni, illetve a sorból tárgyi eszközt létrehozni. 

Azt, hogy egy tárgyieszköz-tranzakció feladása melyik számlára történik, két tényezőtől függ: attól, hogy az eszköz beszerzés vagy a jogi személy által előállított eszköz, illetve attól is, hogy milyen tranzakciótípusról van szó. 

A tranzakciótípus kapcsolja a készlettranzakciót a Tárgyi eszközök modulban megadott feladási profilhoz. Mivel a tárgyi eszközök feladási profilja határozza meg, mely számlák legyenek frissítve, ezért a tárgyi eszközhöz kiválasztott tranzakciótípus közvetetten azt is befolyásolja, hogy melyik fő számlára legyen feladva a tranzakció. Általában az előállított és a beszerzett tárgyi eszközök esetén is **Beszerzés** vagy **Beszerzés helyesbítése** lesz a tranzakciótípus.

## <a name="accounts-receivable"></a>Kinnlevőségek
A tárgyi eszközöknek a Kinnlevőségekkel való integrációjához feladási profilok szükségesek, amelyeket a Tárgyi eszközök modulban állíthat be. Ezek a feladási profilok akkor aktiválódnak, amikor egy vevői számlához kiválaszt egy tárgyi eszközt, egy könyvet és egy tárgyieszköz-tranzakciótípust a vevői számla feladása előtt. Mivel a tárgyi eszközök nem részei a Készletkezelésnek, tárgyi eszközök értékesítésekor a **Szabadszöveges számla** képernyőt kell használni. 

Ha a könyv tartalmaz származtatott könyvet, akkor egy származtatott könyvtranzakció is létrejön a vevői számla feladása során.

## <a name="accounts-payable"></a>Kötelezettségek
A tárgyi eszközök beszerzése általában külső szállítóktól történik. A **Tárgyi eszközök paraméterei** lap használatával adható meg, hogy az eszközbeszerzések mindig fel legyenek-e adva a szállítói számlák feladásakor, vagy hogy eszközbeszerzést csak a Tárgyi eszközök modulból lehessen feladni. Ha engedélyezi az eszközbeszerzések feladását a Kötelezettségek modulban, a tárgyieszköz-számlák mindig frissülnek a tárgyieszköz-beszerzés szállítói számlájának feladásakor. 

Ha be van állítva, hogy számla feladásakor beszerzési tranzakciót adjon fel a rendszer, a tranzakció feladása a különböző tárgyieszköz-tranzakciótípusok esetén a tárgyi eszköz feladási profiljában megadott beállítások szerint történik. A feladás módját a szállítói számla feladása előtt a **Beszerzési rendelés** lapon beállított tárgyi eszköz, könyv és a tárgyi eszköz tranzakciótípusa határozza meg. 

Ha a könyv tartalmaz származtatott könyvet, akkor egy származtatott könyvtranzakció is létrejön a szállítói számla feladása során.

Az egyes rendelési sorok integrációja a **Tárgyi eszközök** lapon történik, amely a **Soradatok** gyorslapon, a **Beszerzési rendelés** lapon található. A szállítónak tárgyi eszközre vonatkozó beszerzési rendeléseket küldhet. Azonban a tárgyi eszközök és a fő számlák csak akkor frissülnek, amikor a tárgyi eszköz megérkezése után feladja a szállítói számlát. Mivel a beszerzési rendelések csak készletcikkeket tartalmazhatnak, a tárgyi eszközök beszerzése a jogi személy beállításainak megfelelően befolyásolja a készletet.

## <a name="project-management-and-accounting"></a>Projektvezetés és könyvelés
A projekteket társítani lehet a projektben érintett eszközhöz. Ezenkívül minden egyes fázist, feladatot vagy alprojektek külön eszközhöz lehet társítani. Minden projektrekordhoz egy-egy tárgyi eszköz társítható. Társítás létrehozásához a tárgyi eszköz számát a **Projektek** lap **Tárgyi eszköz** száma mezőjében kell megadni. A projekt típusa lehet **Belső** vagy **Költségprojekt**. 

A **Projektek** lap használatával lehet a projektekhez társított eszközök részletes adatait is megtekinteni. A tárgyieszköz-rekord megjelenítéséhez kattintson a **Beállítás** gyorslapon található eszközhivatkozásra, ami után megnyílik a **Tárgyi eszközök** lap. Ezután kattintson a **Projektek** &gt; **Minden projekt** elemre, és így megtekintheti a tárgyi eszközhöz társított projekteket. 

A tárgyi eszközöket rendszerint akkor társítják projektekhez, amikor a projektek az eszközön végzett munkához, karbantartáshoz vagy javításhoz kapcsolódik. Amikor a projekt elkészült, nem jön létre automatikusan felértékelés az eszközhöz. Ezért a felértékelést manuálisan kell létrehoznia, ha szükség van rá. 

Projekt és eszköz közötti társítás törléséhez törölje a **Tárgyi eszköz száma** mezőt a **Projektek** lapon. 

Megjelölheti a tárgyi eszköznél, ha azt egy becsült projekt részeként állította elő vagy hozta létre. A becsült projekt végén automatikusan feladhatja az eszközbeszerzési tranzakciót.

További tudnivalókért lásd: [Eszközök vételezése beszerzésen keresztül](acquire-assets-procurement.md).




