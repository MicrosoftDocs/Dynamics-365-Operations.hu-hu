---
title: Szervezeti adminisztráció kezdőlap
description: Ebből a témakörből olyan erőforrásokat érhet el, amelyek segítségével a szervezete hatékonyabban használatba vehető.
author: sericks007
ms.date: 08/18/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "20421"
- intro-internal
ms.assetid: 7aa24a03-d172-47e9-81f8-ebd39e80bc60
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04d188b0bf7d7fc7064467e1e05199d0eb90b4d0276a3c0c01ad8f9be78e76e8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6759896"
---
# <a name="organization-administration-home-page"></a>Szervezeti adminisztráció kezdőlap

[!include [banner](../includes/banner.md)]

A témakör segítséget nyújt a kiemelt felhasználók és az adminisztrátorok számára a rendszer folyamatos és hatékony működésének konfigurálásához a szervezet és a cég számára.

A itt felsorolt tartalom java része a **Szervezeti adminisztráció** modul szolgáltatásaira vonatkozik. Vannak azonban feladatok, például rekordsablon létrehozása és használata, amelyek a szervezet minél hatékonyabb segítésére bármely modulból elvégezhetők.

## <a name="number-sequences"></a>Számsorozatok

A számsorozatokat az azonosítókat igénylő alapadatrekordok és tranzakciórekordok olvasható, egyedi azonosítóinak létrehozására használja a rendszer. Az azonosítókat igénylő alapadatokrekordokat és tranzakciós bejegyzéseket *hivatkozásnak* nevezik. Egy hivatkozáshoz tartozó új rekordok létrehozása előtt be kell állítania egy számsorozatot, és a hivatkozáshoz társítani.

- [Számsorozatok áttekintése](number-sequence-overview.md)
- [Számsorozatok beállítása varázsló használatával](tasks/set-up-number-sequences-wizard.md) (Feladat-útmutató)
- [Számsorozatok beállítása egyedi alapon](tasks/set-up-number-sequences-individual-basis.md) (Feladat-útmutató)

## <a name="organizations"></a>Szervezetek

Egy szervezet olyan emberek csoportja, akik valamely üzleti folyamat végrehajtása vagy egy cél elérése érdekében együtt dologoznak Szervezeti hierarchiák a vállalkozását alkotó szervezetek közötti kapcsolatotat jelölik.

Szervezetek és szervezeti hierarchiák beállítása előtt, győződjön meg arról, hogy megtervezi, hogyan lehet modellezni vállalatát. A szervezeti modellnek jelentős hatása van a bevezetésre és az üzleti folyamatokra.

- [Szervezetek és szervezeti hierarchiák áttekintése](organizations-organizational-hierarchies.md)
- [Szervezeti hierarchia megtervezése](plan-organizational-hierarchy.md)
- [Szervezeti hierarchia létrehozása](tasks/create-organization-hierarchy.md) (Feladat-útmutató)
- [Jogi személy létrehozása](tasks/create-legal-entity.md) (Feladat-útmutató)
- [Üzemi egység létrehozása](tasks/create-operating-unit.md) (Feladat-útmutató)

## <a name="address-books"></a>Címjegyzékek

A globális címjegyzék központi tárház olyan alapadatok számára, amelyeket minden külső és belső személy és szervezet esetén tárolni kell, amelyekkel a vállalat kommunikál. Partnerrekordokhoz kapcsolódó adatok a fél neve, címe és a kapcsolattartási adatai.

Miután létrehozta a globális címjegyzéket, további címjegyzéket hozhat létre szükség szerint, például vállalatonként vagy az üzlet sorainként külön címjegyzéket hozhat létre a szervezetben.

- [Globális címjegyzék áttekintése](overview-global-address-book.md)
- [Terv a globális címjegyzékhez és egyéb címjegyzékekhez](plan-configuration-global-address-book-additional-address-books.md)
- [Globális címjegyzék konfigurálása](tasks/configure-global-address-book.md)
- [Címjegyzékek GYIK](qa-address-books.md)

## <a name="workflow"></a>Munkafolyamat

A munkafolyamat rendszer, amelynek segítségével létrehozhat egyes munkafolyamatokat vagy üzleti eljárásokat. Munkafolyamat létrehozásakor megadja, hogyan halad vagy mozog egy dokumentum a rendszeren keresztül annak jelzésével, hogy kinek a feladata a feladat végrehajtása, a döntéshozatal, illetve a dokumentum jóváhagyása.

- [A munkafolyamat-rendszer áttekintése](overview-workflow-system.md)
- [Munkafolyamat-elemek](workflow-elements.md)
- [Munkafolyamat-jóváhagyási folyamatok műveletei](workflow-actions.md)
- [Munkafolyamatok létrehozása – áttekintés](create-workflow.md)

## <a name="electronic-signatures"></a>Elektronikus aláírások

Az elektronikus aláírás igazolja annak a személynek a személyazonosságát, aki egy számítási folyamat elindítása vagy jóváhagyása előtt áll. Egyes ágazatokban az elektronikus aláírás ugyanúgy jogilag kötelező érvényű, mint a kézzel írott aláírás. Az elektronikus aláírás használatát törvény írja elő számos szabályozott iparágban, például a gyógyszeriparban, az élelmiszer- és italgyártás, a repülőgépgyártás és a honvédelem területén.

A kritikus üzleti folyamatoknál használhatja az elektronikus aláírásokat. Egyes folyamatokba be vannak építve az elektronikus aláírási funkciók. Ugyanezen a képernyőn egyéni elektronikus aláírási követelményeket is létrehozhat, tetszőleges adatbázis-táblára és mezőre vonatkozóan.

- [Az elektronikus aláírások áttekintése](electronic-signature-overview.md)
- [Az elektronikus aláírások beállítása](tasks/set-up-electronic-signatures.md) (Feladat-útmutató)

## <a name="case-management"></a>Esetkezelés

Az esetek tervezésével, nyomon követésével és elemzésével hatékony megoldásokat hozhat létre, amelyeket aztán használhat a hasonló problémákhoz. Például amikor az ügyfélszolgálati képviselők vagy az emberi erőforrások létrehozói eseteket hoznak létre, az adatokat a tudásbáziscikkekben találják meg arra vonatkozóan, hogyan tudnak egy eseten dolgozni, és azt hatékonyan megoldani.

- [Esetkezelés – áttekintés](cases.md)
- [Esetkategória-biztonság, esetfolyamatok és esetkategóriák tervezése](plan-case-management.md)

## <a name="record-templates"></a>Rekordsablonok

A rekordsablonok segítenek a rekordok gyorsabb létrehozásában. Rekordsablon létrehozásával a gyakran használt mezőértékeket nem kell minden új rekordhoz kifejezett módon megadni.

- [Rekordsablonok áttekintése](record-templates.md)
- [Adatbevitel megkönnyítése érdekében rekordsablon létrehozása](../../dev-itpro/data-entities/tasks/create-record-template-facilitate-data-entry.md) (Feladat-útmutató)
- [Rekordsablon használata egy új rekord létrehozásához](../../dev-itpro/data-entities/tasks/use-record-template-new-record.md) (Feladat-útmutató)

## <a name="general-organization-administration"></a>Általános szervezeti adminisztráció

- [A fejléc vagy embléma módosítása](../get-started/tasks/change-banner-or-logo.md) (Feladat-útmutató)
- [A dokumentumkezelés konfigurálása](configure-document-management.md)
- [E-mail konfigurálása és küldése](configure-email.md)
- [Dátum-/időadatok és időzónák](date-time-zones.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]