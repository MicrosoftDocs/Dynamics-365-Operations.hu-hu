---
title: Nemi alap enum extensibility
description: Ez a cikk áttekintést nyújt a nemi alap enumeráció (enumeráció) extenzitásának áttekintésére.
author: twheeloc
ms.date: 05/23/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61a80c16d24d8fda264340d79ed393db3f635908
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749300"
---
# <a name="gender-base-enum-extensibility"></a>Nemi alap enum extensibility

A **nemek** felsorolása (enumeráció) már ki nem egyenlíthető. Ez a témakör ismerteti azokat a módosításokat, amelyek a kódbázisban vannak elkönyvelve, ha **a nemek** közötti felsorolás kiterjesztését tervezi.

## <a name="gender-vs-hcmpersongender"></a>Nem és HcmPersonGender

A nemi értékeknek két felsorolása van:

- **Nem** (alkalmazás platformja)
- **HcmPersonGender** (PersonnelManagement)

A **Nemek** szerinti felsorolás az Microsoft Dynamics egész 365 Pénzügyben használatos, **míg a HcmPersonGender** a humánerőforrás-kezelési (HCM) funkciókra jellemző. Ha a HCM-funkciókat használja, **és** bármilyen módosítást végrehajtott a nemek felsorolásán, **érdemes megfontolni a HcmPersonGender ugyanazon módosításait**. Ha például a **Nemek számba veheti fel a Transgendert** **·**, **akkor a HcmPersonGender felsoroláshoz is hozzáadhatja a Transgendert.** **·**

## <a name="hcmpersongendertranformutil-class"></a>HcmPersonGenderTranformUtil (osztály)

Egy új **HcmPersonGenderTranformUtil osztály jött** létre, amely lehetővé teszi a két alap enumeráció közötti fordítást. Ebben az osztályban két módszer van: **convertGenderToHcmPersonGender** és **convertHcmPersonGenderToGender**. A **Parancslánc** **osztály** vagy eseménykezelők segítségével hozzon létre kiterjesztést, és mindkét módszert bővítse az alapvető felsoroláshoz hozzáadott új értékek leképezésére.

## <a name="payrollstatewagetaxprepdp-class"></a>PayrollStateWageTaxPrepDP (osztály)

**A PayrollStateWageTaxPrepDP** a **bérlista állami béradója Prep** SQL Server Reporting Services (SSRS) jelentés adatszolgáltató osztálya. Az Egyesült Államokban három érték érhető el: **Női**, **·** **Női és Meghatározatlan.** A populatePayrollStateWageTaxPrepTmp **metódusban van egy switch utasítás, amely a** HcmPersonGender **enum értékének három mező egyikére való leképezésére használatos:** IsMale **,** IsFemale **vagy** IsUnspecifiedGender **.** A switch utasítás alapértelmezett értéke **Az IsUnspecifiedGender**. **Ha másképp szeretne leképezni valamilyen értéket a HcmPersonGender** felsoroláshoz, létre kell hoznia egy kiterjesztést a parancslánc osztályon keresztül a populatePayrollStateWageTaxPrepTmp **metóduson keresztül,** **hogy** szükség szerint módosítsa az értéket.

## <a name="smmoutlooksync_contact-class"></a>smmOutlookSync_Contact (osztály)

Az **smmOutlookSync_Contact integráció osztálya az Outlook programba, illetve a kapcsolattartókhoz, illetve az** outlook **programba**, illetve onnan származó értékeket tartalmaz **.** **Az Outlook** három értéket támogat: **Női,** **Női** **és Meghatározatlan**. Az osztálynak két módja van, amelyek segítenek a **nemek** OutlookGendershez való **leképezésében**. Az alapértelmezett módszer a **Nem meghatározott/Meghatározatlan**. Ha a nemi felsoroláshoz további **értékeket** hoz létre, **akkor** a parancsláncosztály használatával mindkét módszerrel, illetve szükség szerint leképezve is létre kell hoznia egy kiterjesztést.
