---
title: Készlet zárása
description: A kiadási tranzakció bevételezési tranzakciókkal való kiegyenlítésének részeként lehetősége van frissíteni a főkönyvet, hogy az tükrözze a végrehajtott módosításokat.
author: AndersGirke
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61973
ms.assetid: c210c882-6849-4704-b78c-a777dd6cfdb6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 078969e12275c3abd2e4ea2f8c6c9579dce73e5f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574017"
---
# <a name="inventory-close"></a>Készlet zárása

[!include [banner](../includes/banner.md)]

A kiadási tranzakció bevételezési tranzakciókkal való kiegyenlítésének részeként lehetősége van frissíteni a főkönyvet, hogy az tükrözze a végrehajtott módosításokat.

A készletzárási folyamat a cikk cikkmodellcsoportjában kiválasztott készletértékelési módszer alapján a kiadási tranzakciókat a bevételezési tranzakciókkal szemben egyenlíti ki. A kiegyenlítési folyamat részeként megadhatja, hogy a főkönyv frissítése a történt módosításoknak megfelelően történjen. A program azonban a készletzárás vagy az újraszámítás futtatásáig a kiadási tranzakciókat a számított mozgóátlagon alapuló önköltségi áron adja fel. 

A készletzárás után a beállított készletzárási dátum előtti időszakokra nem lehet feladást végezni, kivéve befejezett készletzárási folyamat sztornírozása esetén. Ha például készletzárás fut le a január 31-ével véget érő időszakra vonatkozóan, január 31-nél korábbi dátummal rendelkező tranzakciókat nem lehet feladni. 

A készleten lévő cikkek kétféle készlettípushoz tartozhatnak: cikk vagy szolgáltatás. A készletzárás mindkét típusnál ugyanazokat a műveleteket hajtja végre. Azonban szolgáltatási cikkek esetében a készletzárás továbbra is kiegyenlíti a kiadásokat a bevételezésekkel szemben. 

A készletzárás gyakorisága vállalat szerint változik. Tranzakció volumene azonban segíti meghatározni eldönteni, hogy milyen gyakran futtasson készletzárást A legtöbb vállalat általában a készletzárást a hónap végi zárási és egyeztetési folyamatok részeként hajtja végre.

## <a name="inventory-recalculation-and-the-general-ledger"></a>A készlet újraszámítása és a főkönyv
Ha a készlethez és a főkönyvhez tartozó kiigazítás szükségesek a hónap vagy más készletidőszak során, futtathatja a készlet újraszámítását a készletzárás helyett. A készlet újraszámítása elvégzi a kiigazításokat, de készlettranzakciókhoz nem végzi el az elszámolást. 

Készlet-újraszámítás során módosul(nak) az aktuális készlet és a készlettranzakciók, a készlet-újraszámítások és a készletzárások pedig futtatódnak. A műveletek végrehajtása azokat a főkönyvi számlákat érinti, amelyek az eredeti készlettranzakcióhoz voltak kapcsolva. 

**Példa** 

Amikor egy értékesítési rendelésből beszerzési rendelést hoz létre, az eredeti értékelési rendelésben használt főkönyvi számlák frissülnek. Ha a cikkhez rendelt cikkcsoport főkönyvi számlái megváltoztak az értékesítési rendelés feladása óta, és a készlet újraszámítása helyesbítési összeget eredményezett a rendszer a helyesbítési összeget akkor is az eredeti főkönyvi számlákra adja fel. A helyesbített eredeti összeg nem a cikkhez rendelt új főkönyvi számlákra kerül feladásra. 

A frissítés befejeződése után ellenőrizheti a műveletek következtében létrejött és feladott főkönyvi bizonylatot.

1.  A **Zárás és kiigazítás** oldalon, az **Áttekintés** fülre kattintva, jelölje ki az ellenőrzendő frissítést.
2.  Kattintson a **Részletek** gombra, majd válassza ki **Bizonylat** lehetőséget.

## <a name="effects-of-the-inventory-close-process-on-the-general-ledger"></a>A készlet lezárási folyamat hatásai a főkönyvben.
Számos, a **Zárás és kiigazítás** oldalon elvégezhető művelet a főkönyv frissítését eredményezi. Például, a főkönyv frissül, az aktuális készlet kiigazítása, készlettranzakciók helyesbítése, a készlet újraszámításának és a készletzárás futtatása esetén. 

Ezen feladatok miatt frissített főkönyvek az eredeti készlettranzakcióhoz vannak csatolva. Ha például egy értékesítési rendelés az eredeti értékesítési rendeléshez alkalmazott beszerzési rendeléssel és az eredeti értékesítési rendeléssel van kiegyenlítve. Ez a viselkedés akkor is zajlik, ha a cikkhez rendelt cikkcsoportra vonatkozó főkönyv megváltozott az értékesítési rendelés feladása óta. Miután a készletzárás létrehoz egy kiegyenlítési összeget, a kiegyenlítési összeg akkor is az eredeti főkönyvi számlákra kerül bejegyzésre, és nem pedig a cikkhez rendelt új főkönyvi számlákra. A főkönyv akkor is frissíthető, ha sztorníroz egy készletzárást. 

> [!NOTE] 
> - A készlet zárása kötelező lépés az összes készletmodell esetében a hónap végi zárási eljárásban, kivéve a mozgó átlagköltséget.  Figyelmeztetés jelenik meg, ha úgy próbál pénzügyi időszakot lezárni, hogy nem az időszak záró dátumától kezdve végzi a készletzárást.
> - A zárási folyamat futtatása előtt megtekintheti azoknak az elemeknek a listáját, amelyeket nem lehet kiegyenlíteni a frissítés során.
> - A számítástechnikai erőforrások egyenletesebb terhelése érdekében ajánlott a készletzárás csúcsidőn kívüli végrehajtása.

## <a name="the-inventory-close-log"></a>A készletzárási napló
A készletzárási folyamat befejeződése után az üzenetközpontban egy üzenet tájékoztatást nyújt arról, hogy önköltségi egységár esetleg téves, mert egy tranzakciót nem sikerült teljesen kiegyenlíteni. 

Ezen üzenet megjelenítése előtt, a rendszer jelenti a cikkszámot és az érintett tranzakciót. Az üzenet arról ad tájékoztatást, hogy a tranzakcióhoz használt költségösszeg frissítése nem történt meg a készletzárás miatt. Ez az üzenet akkor jelenik meg, amikor a kiadás típusának tranzakcióját nem lehet kiegyenlíteni. 

A készletzárási folyamat során a rendszer mindegyik pénzügyi dimenziót ellenőriz, annak érdekében, hogy kiderüljön, hogy vajon több kiadás van-e, mint bevételezés a megadott zárási dátumig Az ilyen egyensúlyhiány olyankor léphet fel, amikor egy beszerzési rendelés készlettranzakciójának pénzügyi feladása nem történik meg teljes egészében, mert nem érkezett meg a szállító számlája, vagy mert egy magasabb szintű termelési anyagjegyzék-összetevőinek pénzügyi feladása nem történt meg. (A résztermelés nem költséggel számított.) Ilyen esetben az ezt követő zárás nem igazítja ki az összes kiadást a helyes önköltségi árhoz, mert nem áll rendelkezésre elégséges bevételezési információ. 

A rendszer minden zárási eljárás lefuttatásakor megadja, hogy a figyelmeztetéseket tartalmazó napló rögzített-e vagy megtekinthető-e. 

Ha sok figyelmeztetést kap az üzenetben, a következő műveleteket ajánlatos végrehajtani:

-   Bevételezések pénzügyi frissítése.
-   A zárási dátum későbbre állítása.
-   Az üzleti folyamatok felülvizsgálata.

Néhány körülmény között előfordulhat, hogy nem tud semmit sem tenni a figyelmeztetésekkel. Például, ha jelölést alkalmaz és a megjelölt beszerzési rendelés olyan pénzügyi dátummal rendelkezik, amely a zárási dátum utánra esik, a zárási dátum már nem módosítható.

## <a name="reversing-a-completed-inventory-close"></a>Befejezett készletzárás sztornírozása
Bizonyos esetekben szükség lehet egy befejezett készletzárás sztornírozására annak érdekében, hogy a kiegyenlítéseket a módosítások előtti állapotába állítsa vissza. Befejezett készletzárás sztornírozása esetén a készletet újra megnyitja a rendszer, hogy lehetővé tegye a készletzárás által lefedett időszakhoz kapcsolódó feladásokat. Kapcsolódó módosításokat a főkönyvben is végrehajthatja. Miután befejezte a szükséges módosításokat, ismét futtathatja a készletzárást az érintett periódusra. 

> [!NOTE] 
> Csak a legutóbb lezárt készletidőszakot lehet újra megnyitni. A korábbi készlet zárásának sztornírozása érdekében, először sztorníroznia kell minden egyes készletzárást a legutolsó zárással kezdődően.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]