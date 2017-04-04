---
title: "A könyvvizsgálati irányelvmegsértések és esetek"
description: "Ez a cikk bemutatja, hogyan jönnek létre a naplózási ügyek a naplózási irányelvszabályok megsértése által. Információkat tartalmaz továbbá arról, hogyan alkalmazzák a naplózási irányelvek a dokumentumok határidő-intervallum szerinti kiválasztását."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: ecd32549b6067ed4c1211996e846e210f77f5013
ms.openlocfilehash: 77f72c9414f1fad720055e58e3f704b9c713072f
ms.lasthandoff: 03/31/2017


---

# <a name="audit-policy-violations-and-cases"></a>A könyvvizsgálati irányelvmegsértések és esetek

Ez a cikk bemutatja, hogyan jönnek létre a naplózási ügyek a naplózási irányelvszabályok megsértése által. Információkat tartalmaz továbbá arról, hogyan alkalmazzák a naplózási irányelvek a dokumentumok határidő-intervallum szerinti kiválasztását.

<a name="how-audit-cases-are-generated"></a>Könyvvizsgálati esetek létrehozásának módja
-----------------------------

Könyvelési irányelvek használatával azonosítani lehet a költségjelentéseket, a beszerzési rendeléseket és a szállítói számlákat, amelyek nem felelnek meg az irányelvszabályként meghatározott és konfigurált üzleti szabályoknak. 

A könyvvizsgálati irányelvek kötegelt módban futnak. A könyvvizsgálati irányelv futtatásakor, az irányelv összes irányelvszabálya egyszerre fut.

Minden egyes irányelvszabály értékel egy dokumentumbeállítást. Az irányelvszabály a dokumentumkiválasztási dátumtartományból választ dokumentumot, amely megfelel a megadott feltételnek. Például egy irányelvszabály kiválaszthat költség jelentéseker, amelyeknél az étkezések száma meghaladta az 50,00-t. Egy másik irányelvszabály kiválaszthatja a szállítói számlákat, amelyek fizethetőek egy adott szállítóra. Minden dokumentumhoz, amely a készletben ki van jelölve, megszegés generálódik. A megsértés egy rekordot, amelyben egy adott dokumentum, például számla 12345, az irányelvszabálynak nem felel meg. 

Több könyvelési megsértéssel rendelkező rekordok együtt csoportosítottak és könyvelési esetekhez rendeltek. Alapértelmezés szerint az egyes könyvvizsgálati irányelv esetek könyvvizsgálati irányelvszabály szerint vannak csoportosítva. Ha azt szeretné, be lehet állítani más csoportosítási feltételeket az **Esetcsoportosítási feltételek** lap használatával. Például csoportosíthatjuk költség fejlécek által projekt azonosítója és a szállítói számlák szállítói számlára. Ebben az esetben a megegyező Projektazonosítójú rendelkező összes költség fej megsértése csoportosulnak ugyanabban az ügyben, és ugyanabban az ügyben minden szállítói számlák, amelyek az azonos szállítói számlához csoportosulnak. 

> [!NOTE]
> Az ellenőrzési szabályok, amelyek alapján egy **ismétlődő** lekérdezéstípus, megsértése nem csoportosított házirendszabály használatával, vagy a megadott feltételek szerint a **esetben csoportosítási feltételt** lap. Ehelyett a könyvvizsgálati irányelvszabályban megadott feltétel alapján csoportosulnak. Például ha egy irányelvszabály értékeli a költségjelentéseket az azonos összeg, kereskedő azonosítója vagy dátum ismétlődő költségeihez, az összes költség, amelynek az értéke megegyezik, egy eset lesz. Különböző értékekkel rendelkező kiadások külön esetek lesznek.

A Könyvvizsgálati esetek elkészülte az esetkezelés tipikus folyamatának használatával kidásra kerülnek.

## <a name="document-selection-date-ranges"></a>Dokumentumkiválasztás dátumtartományok
A könyvvizsgálati irányelv futtatásakor minden irányelvszabály kijelöl adott típusú dokumentumokat, amelyek dátumai a dokumentumkiválasztási dátumtartományba esnek. A dokumentumkiválasztási dátumtartományt a **További lehetőségek** oldalon adhatja meg. Sok dokumentumhoz több dátum is tartozik. A dátum mező, amelyet könyvvizsgálati irányelvszabály, az **Irányelvszabály-típus** oldalon van megadva.

Íme néhány további mód, ahogy a költségvetési irányelv a dokumentumkiválasztási dátumtartományt használja:

-   Az irányelv az összes irányelvszabályt alkalmazza, amely érvényes a dokumentumkiválasztási dátumtartomány utolsó napján. Megtekintheti az egyes irányelvszabályok érvényességi dátumait a **Könyvviteli irányelvek** listaoldalán.
-   A irányelv használja a szervezeti csomópontokat, amelyek az irányelvhez társítottak a dokumentumkiválasztási dátumtartomány utolsó napján. Csak az irányelv jelenleg kapcsolódó szervezeti csomópontok jelennek meg a **Könyvviteli irányelvek** listaoldalán.
-   Az irányelvszabályok, amelyek **Keresés lista** lekérdezés típuson alapszanak, az irányelv értékeli a dokumentumokat a figyelt entitásokhoz, amelyek érvényesek a dokumentumkiválasztási dátumtartomány utolsó napján.


További tudnivalókért lásd: [házirend szabályok naplózása](audit-policy-rules.md)


