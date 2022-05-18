---
title: Beszerzési rendelések létrehozása
description: A cikk ismerteti a beszerzési megrendelés kézi létrehozásának folyamatát és lehetőségeit.
author: GalynaFedorova
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 93053
ms.assetid: 25b1c9f1-20f8-4cf5-b87c-876e32f68846
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70050efb31040f2c7ebfc55681a7145e313d804d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674365"
---
# <a name="create-purchase-orders"></a>Beszerzési rendelések létrehozása

[!include [banner](../includes/banner.md)]

A cikk ismerteti a beszerzési megrendelés kézi létrehozásának folyamatát és lehetőségeit.

Beszerzési rendelés létrehozásakor a teljes rendelés általános információi beszerzési rendelés fejlécében vannak megadva, és ekkor egy vagy több beszerzésirendelés-sor hozzáadható. A cikk ismerteti a leggyakrabban használt beállításokat.  

Beszerzési rendelés más beszerzési rendelés vagy értékesítési rendelés sorainak bemásolásával is létrehozható. Ebben az esetben megfordíthatja a készleten szereplő jelzést, ahogyan a számlán is megfordítható a jelzés követelés jelzésére.  

Beszerzési rendelés ugyan manuálisan is létrehozható, de leggyakrabban egyéb folyamatokból kerül generálásra. Rendelések automatikusan létrehozhatók más dokumentumok, például igénylések alapján. Másik megoldásként az alaptervezés részeként is létrehozhatók tervezett beszerzési rendelésekkel. Ha beszerzési szerződéseket használ, a beszerzési rendelések a **Kiadási rendelés** művelettel hozhatók létre. Beszerzési megrendelés automatikus létrehozására további, fejlettebb módszerek is léteznek. Rendelések hozhatók létre például közvetlen kiszállítás vagy vállalatközi rendelés láncok használatával.

## <a name="creating-a-purchase-order-header"></a>Beszerzési rendelés fejléc létrehozása
Egy új beszerzési rendelés létrehozásakor megjelenik egy párbeszédpanel, amelyen meg lehet adni a leggyakrabban használt adatokat a beszerzési rendelés fejlécében. Amikor rákattint az **OK** gombra a párbeszédpanel bezárásához, a rendelés létrejön, és a fejlécben további információk határozhatók meg.  

Beszerzési rendelés létrehozásakor az első meghatározandó adat a rendelés típusa. A **Beszerzési rendelés** a leggyakrabban használt típus. Azonban ha követelési számlát kell használni, használhatja a **Visszaküldött rendelés** típust.  

A **Szállítói számla** mezőben meg kell adni, hogy ki a szállító. Ebben a mezőben kereshet számlára, vagy a szállító nevére. Ha a szállító több helyről szállít, de ehhez egy számlaszámot használ, a számlaszámot kiválaszthatja a **Számlaszám** mezőben, és különböző szállítói számlákhoz használhatja. Ha olyan termékekre kell beszerzési rendelést létrehoznia, melyeket csak egyszer fog megrendelni, használhatja az **Egyszeri szállító** opciót. Ez az opció automatikusan egy új, egyszeriként megjelölt szállítói számlát hoz létre, így megkönnyítve a későbbi, egyszeri alkalomra létrehozott számlák adattisztítási folyamatát a **Kötelezettségek** modulban. Szállítói számla kiválasztásakor a beszerzési megrendelés fejlécének sok mezője a szállítói számlából származtatott alapértéket kap. Például az alapértelmezett kézbesítési hely és raktár a szállító adataiból kerülnek kimásolásra. Azonban ezeket az alapértelmezett értékeket felül lehet bírálni, ha a tranzakció más helyen történik.  

Amennyiben a szállító a megrendeléshez biztosított referenciaszámot, az a **Szállítói referencia** mezőben rögzíthető. Visszaküldött rendelések esetén az értéket meg kell adnia az **RMA** mezőben, hogy az referenciaként szolgálhasson a szállító visszatérítésének engedélyezéséhez.  

Ha a rendeléshez vásárlási megállapodás is tartozik, ezt az információt a **Vásárlási megállapodás** mezőben meg kell adnia.  

A beszerzési rendelés fejléce továbbá információkat tartalmaz a teljes rendelésre vonatkozó díjakról, anélkül, hogy azokat külön sorokban részletezné. A költségeket automatikusan hozzá lehet adni a megrendeléshez, amennyiben a szállítóhoz vagy a szállító költségcsoportjához be van állítva az automatikus költségek opció. A költségeket manuálisan, a műveleti ablaktáblán található **Fenntartási költségek** gombra kattintva is hozzáadhatja a megrendelőlap fejlécéhez.

## <a name="adding-purchase-order-lines"></a>Beszerzésirendelés-sorok hozzáadása
A beszerzési megrendelések vonatkozhatnak fizikai termékekre, vagy szolgáltatásokra. A készletmodell-csoport egyik beállítása meghatározza, hogy egy adott termékszám vonatkozik-e az adott termékre vagy szolgáltatásra. Általában a megvásárolandó cikket a cikkszámmal azonosítják. Azonban, ha a rendelés olyan termékekre vagy szolgáltatásokra vonatkozik, melyek közvetlen felhasználásra kerülnek, a cikket a beszerzési kategóriával is azonosíthatja.  

A beszerzési megrendelés soraiban sok mező található, de ezek közül sok egy másik fejlécben található információk alapján alapértéket kap. Bizonyos termék vagy szolgáltatás kiválasztásakor további mezők jelenhetnek meg. A kézzel leggyakrabban beállított mezők tartalmazzák a cikkszám-, a mennyiség-, és a kért szállítási dátum mezőket. Az egységárakra és kedvezményekre vonatkozó információk is nagyon fontosak, de ezen mezők értékeit gyakran a kereskedelmi megállapodások vagy vásárlási megállapodások határozzák meg.  

Egy termék kiválasztásakor nem csak a cikkszámra, hanem a termék nevére vagy a termék nevének egy részére is kereshet. Ha egy terméknek több változata, pl. különböző méretei vannak, azokat a **Sorok hozzáadása** gombbal, vagy a **Variánsszám** mezőben található keresővel megjelenítheti.  

A beszerzési megrendelésben gyakran soronként meg kell adnia a kiválasztott cikk különböző dimenzióira vonatkozó adatokat. A meghatározandó dimenziók az alaptermékhez rendelt dimenziócsoportoktól függenek. Például gyakran meg kell adnia egy helyet és egy raktárat annak a helyszínnek a megjelöléséhez, ahová a terméket szállíttatni kívánja. Termékváltozatokat változatszámmal, vagy egy vagy több termékdimenzió, mint pl. szín, méret, konfiguráció, vagy stílus megadásával azonosíthat. A követési dimenziók, mint pl. kötegszám és sorszám segítségével egyedien azonosíthat minden készletadagot. Rendelés létrehozása után a rendelésen szereplő dimenzióértékeket a **Regisztráció** művelettel adhat meg. Például, egy adott cikkből öt darabot rendelt. Később rögzítheti, hogy három ilyen darab fekete, kettő pedig kék színű lesz. Ez a megközelítés alternatívát nyújt az érkezési regisztráció során történő dimenzióinformáció-megadásra.  

Ellenőrizheti a készlettranzakció állapotát a raktározott termékekre vonatkozóan. Például érdemes ellenőrizni az aktuális készlet mennyiségét, hogy eldöntse, mennyit rendeljen. Ezen kívül érdemes lehet ellenőrizni egy rendelt mennyiség készletállapotát, hogy megtudja, hogy megtörtént-e az érkezési regisztráció.  

Egy termék szállító részére történő visszaküldésekor az erre használt beszerzésirendelés-sornak negatív értéke lesz. Visszaküldésre kiválaszthat egy adott adagot a **Foglalás** művelettel.  

Egyes esetekben érdemes felosztani a rendelt mennyiséget úgy, hogy a különböző részek más-más napokon érkezzenek. Ezeket a szállításokat a **Szállítás ütemezése** művelettel hajthatja végre, ami a **Sorok** nézetben a **Beszerzésirendelés-sor** menüben található meg.  

A költségeket automatikusan hozzá lehet adni a beszerzésirendelés-sorokhoz, amennyiben a szállítóhoz vagy a szállító költségcsoportjához, és a cikkhez vagy a cikk költségcsoportjához be van állítva az automatikus költségek opció. Azonban gyakoribb, hogy a költségeket manuálisan, a rendeléssor szintjén adják meg. Költség hozzáadásához nyissa meg a **Költségek kezelése** lapot a **Költségek kezelése** művelettel a **Pénzügyek** menüpontban, **Sorok** nézetben. A költségek hozzáadása közvetlenül a rendelési sor szintjén azért előnyös, mert így a költségeket készletköltségként lehet elszámolni. Költségkódok beállításához a számlatermék-költségekhez használja a **Cikk** tartozás opciót. Az ilyen típusú költségeket a rendelés megerősítése előtt a beszerzési rendelés fejlécéből a sorokhoz kell rendelni. Érdemes lehet például a költségeket az egyes sorokban szereplő mennyiség alapján hozzárendelni. A költségkategória is befolyásolja, hogyan kerülnek elszámolásra a költségek. A rögzített költségek például egy fix összeget adnak meg, a százalékköltségek pedig a rendeléssor nettó összege alapján százalékként kerülnek kiszámolásra. A beszerzési rendelések terhelésekhez rendelhetők, és a terhelésekben szerepelhet a szállítási költségekre vonatkozó becslés. Ez a költség a terhelésekből a beszerzésirendelés-sorokhoz rendelhető.

## <a name="purchase-order-actions"></a>Beszerzési rendelés műveletei
A fejléc és a sorok beszerzési rendeléshez történő hozzáadása után gyakori, hogy további lépéseket kell végrehajtani a beszerzési rendelés megerősítése előtt. Mivel sok lehetőség áll rendelkezésre, érdemes lehet a [Műveletkeresés](../../fin-ops-core/fin-ops/get-started/action-search.md) opciót használni a megfelelő elem megtalálására a menüben.  

A rendelésen a termékek konfigurálhatók úgy, hogy kiegészítő cikkeket tartalmazzanak. A kiegészítő cikkek olyan termékek, vagy más termékekkel együtt lehet vagy kell megvásárolni. A kiegészítő termékek költségmentesen hozzáadhatók, mint kísérő termékek, vagy eldöntheti, hogy hozzáadja-e őket a rendeléshez vagy sem. A kiegészítő elemeket minden hozzáadott rendelési sor után ellenőrizheti. Azonban a kiegészítő termékek ellenőrzése és hozzáadása kényelmesebb lehet a Kiegészítő termékek oldal használatával a **Műveletek oldalon**, ahol az összes rendeléssort egyszerre kezelheti.  

A kedvezmények általában a sorok létrehozásakor kerülnek hozzáadásra. Azonban bizonyos engedmények a teljes rendelésre vonatkoznak:

-   Az **Összes kedvezmény** művelet a teljes rendelésre vonatkozó kedvezmények százalékát számolja ki. Ne tévessze össze ezt a kedvezményt a készpénzfizetési engedmény százalékával. A készpénzfizetési engedmények a számla kifizetésére vonatkoznak, és a kifizetés egy megadott dátumon történő kifizetésétől függenek.
-   Ha többsoros engedmény érvényes, akkor kell használni a **Többsoros engedmény** műveletet, ami kiszámolja és hozzárendeli az engedményt a rendeléshez. Többsoros engedmények akkor adhatók, ha a rendelésen szereplő termékegyveleg meghaladja az összesített küszöbértéket. Ezt a fajta kedvezményt csak néhány vállalat alkalmazza.

Azokat a költségeket, melyek **Cikk** terheléstípust használó költségkóddal rendelkeznek, a rendelés megerősítése előtt hozzá kell rendelni a sorszinthez. Kényelmesebb lehet ezeket a költségeket a megrendelés fejlécszintjén hozzárendelni, így megállapítva a költségek teljes összegét. Ebben az esetben azonban a költséget a rendelés megerősítése előtt minden egyes sorhoz hozzá kell rendelni. Használhatja a **Költségek hozzárendelése** műveletet az olyan költségek felosztására, melyeket a fejlécszintről a rendeléssorokhoz rendel hozzá. A költségeket az egyes sorok nettó összegeinek megfelelően a rendelt mennyiség alapján, vagy egyenlően is fel lehet osztani. A költségek sorokhoz rendelése után a költség törlődik a megrendelés fejlécéből.  

A beszerzési megrendelések konfigurálhatók úgy, hogy azok csak úgy legyenek feldolgozhatók, ha a költségvetési pénzalapok már a rendeléshez vannak rendelve. Ebben az esetben használhatja a **Költségvetés-ellenőrzés** műveletet a költségvetés hozzárendeléséhez.  

Előfordulhat, hogy egy adott beszerzési megrendelés végrehajtását késleltetni kell. Például előfordulhat, hogy egy termékre vagy szolgáltatásra vonatkozóan további információkra van szüksége, vagy engedélyeztetnie kell a kiadásokat. Egy rendelés számos módon visszatartható. Például várhat a rendelés megerősítésével. Ha a változáskezelés munkafolyamatot használja, akkor azt is megteheti, hogy nem adja le a rendelést engedélyezésre. Ha egy bizonyos szállító összes rendelését fel kell függesztenie, a szállítót **Felfüggesztve** jelöléssel láthatja el a szállítói alapadatoknál. Felmerülhetnek olyan körülmények, melyek megakadályozzák egy adott rendelés feldolgozását. A feldolgozást hátráltathatja például, ha a túllépte a hitelkeretet, vagy ha a szükséges költségvetési alapok nem állnak rendelkezésre.

## <a name="additional-resources"></a>További erőforrások

[Beszerzési rendelések áttekintése](purchase-order-overview.md)

[Beszerzési rendelések jóváhagyása és megerősítése](purchase-order-approval-confirmation.md)

[Termékbevételezés összevetése a beszerzési rendelésekkel](product-receipt-against-purchase-orders.md)

[Szállítói számlák áttekintése](../../finance/accounts-payable/vendor-invoices-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]