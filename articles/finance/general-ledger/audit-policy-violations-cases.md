---
title: A könyvvizsgálati irányelvmegsértések és esetek
description: Ez a cikk bemutatja, hogyan jönnek létre a naplózási ügyek a naplózási irányelvszabályok megsértése által. Információkat tartalmaz továbbá arról, hogyan alkalmazzák a naplózási irányelvek a dokumentumok határidő-intervallum szerinti kiválasztását.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: kfend
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dbef92865c0a463b3922d7cc6c3f46759ffdc9ad
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711117"
---
# <a name="audit-policy-violations-and-cases"></a>A könyvvizsgálati irányelvmegsértések és esetek

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan jönnek létre a naplózási ügyek a naplózási irányelvszabályok megsértése által. Információkat tartalmaz továbbá arról, hogyan alkalmazzák a naplózási irányelvek a dokumentumok határidő-intervallum szerinti kiválasztását.

## <a name="how-audit-cases-are-generated"></a>Könyvvizsgálati esetek létrehozásának módja

Könyvelési irányelvek használatával azonosítani lehet a költségjelentéseket, a beszerzési rendeléseket és a szállítói számlákat, amelyek nem felelnek meg az irányelvszabályként meghatározott és konfigurált üzleti szabályoknak. 

A könyvvizsgálati irányelvek kötegelt módban futnak. A könyvvizsgálati irányelv futtatásakor, az irányelv összes irányelvszabálya egyszerre fut.

Minden egyes irányelvszabály értékel egy dokumentumbeállítást. Az irányelvszabály a dokumentumkiválasztási dátumtartományból választ dokumentumot, amely megfelel a megadott feltételnek. Például egy irányelvszabály kiválaszthat költség jelentéseker, amelyeknél az étkezések száma meghaladta az 50,00-t. Egy másik irányelvszabály kiválaszthatja a szállítói számlákat, amelyek fizethetőek egy adott szállítóra. Minden dokumentumhoz, amely a készletben ki van jelölve, megszegés generálódik. A megsértés egy rekordot, amelyben egy adott dokumentum, például számla 12345, az irányelvszabálynak nem felel meg. 

Több könyvelési megsértéssel rendelkező rekordok együtt csoportosítottak és könyvelési esetekhez rendeltek. Alapértelmezés szerint az egyes könyvvizsgálati irányelv esetek könyvvizsgálati irányelvszabály szerint vannak csoportosítva. Ha azt szeretné, be lehet állítani más csoportosítási feltételeket az **Esetcsoportosítási feltételek** lap használatával. Például csoportosíthatja a költségfejléceket projektazonosító alapján és a szállítói számlákat szállítókód alapján. Ebben az esetben az összes a megegyező projektazonosítójú költségfejléc-szabálysértés ugyanahhoz az esethez lesz csoportosítva, és az összes szállítói számla, amelynek azonos a szállítókódja, ugyanahhoz az esethez lesz csoportosítva. 

> [!NOTE]
> A **Másolat** lekérdezéstípuson alapuló könyvvizsgálati irányelvszabály miatt a megszegések nem csoportosulnak irányelvszabály vagy az **Esetcsoportosítási feltételek** lapon megadott feltételek szerint. Ehelyett a könyvvizsgálati irányelvszabályban megadott feltétel alapján csoportosulnak. Például ha egy irányelvszabály értékeli a költségjelentéseket az azonos összeg, kereskedő azonosítója vagy dátum ismétlődő költségeihez, az összes költség, amelynek az értéke megegyezik, egy eset lesz. Különböző értékekkel rendelkező kiadások külön esetek lesznek.

A Könyvvizsgálati esetek elkészülte az esetkezelés tipikus folyamatának használatával kidásra kerülnek.

## <a name="document-selection-date-ranges"></a>Dokumentumkiválasztás dátumtartományok
A könyvvizsgálati irányelv futtatásakor minden irányelvszabály kijelöl adott típusú dokumentumokat, amelyek dátumai a dokumentumkiválasztási dátumtartományba esnek. A dokumentumkiválasztási dátumtartományt a **További lehetőségek** oldalon adhatja meg. Sok dokumentumhoz több dátum is tartozik. A dátum mező, amelyet könyvvizsgálati irányelvszabály, az **Irányelvszabály-típus** oldalon van megadva.

Íme néhány további mód, ahogy a költségvetési irányelv a dokumentumkiválasztási dátumtartományt használja:

-   Az irányelv az összes irányelvszabályt alkalmazza, amely érvényes a dokumentumkiválasztási dátumtartomány utolsó napján. Megtekintheti az egyes irányelvszabályok érvényességi dátumait a **Könyvviteli irányelvek** listaoldalán.
-   A irányelv használja a szervezeti csomópontokat, amelyek az irányelvhez társítottak a dokumentumkiválasztási dátumtartomány utolsó napján. Csak az irányelv jelenleg kapcsolódó szervezeti csomópontok jelennek meg a **Könyvviteli irányelvek** listaoldalán.
-   Az irányelvszabályok, amelyek **Keresés lista** lekérdezés típuson alapszanak, az irányelv értékeli a dokumentumokat a figyelt entitásokhoz, amelyek érvényesek a dokumentumkiválasztási dátumtartomány utolsó napján.


További információ: [Könyvvizsgálati irányelvszabály](audit-policy-rules.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
