---
title: "Juttatásra való jogosultsági irányelvek"
description: "Ez a cikk információt biztosít a juttatás alkalmassági irányelveit illetően, így segítve önt a különleges juttatásokra jogosult személyek meghatározásában."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 543e43df2ec70e6f6e884019bb1c65bf3661ff35
ms.openlocfilehash: 3f9ab358ecbe7a992341610184002dbd97a31a4d
ms.lasthandoff: 03/31/2017


---

# <a name="benefit-eligibility-policies"></a>Juttatásra való jogosultsági irányelvek

A témával kapcsolatban tartalmaz tájékoztatást juttatás való jogosultsági irányelvek, amely segítségével meghatározhatja adott ellátásra jogosult.

Juttatások létrehozásakor eldöntheti, mely juttatások mely alkalmazottak számára lesz elérhető. Az alábbi táblázat példákat mutat juttatásokra, amelyeket elérhetővé tehet bizonyos alkalmazottaknak.

| Juttatás          | Akiknek elérhető a juttatás |
|------------------|---------------------------------|
| Egészségbiztosítás | Minden alkalmazott                   |
| Mobiltelefon     | Értékesítési munkatársak, vezetők         |
| Parkolási engedélyek   | Ügyintézők                      |

Az alábbi összetevők jogosultsági házirendek létrehozásához használt:

-   Irányelvszabály típusai
-   Juttatásra való jogosultsági irányelvek

Az irányelvszabályok típusai definiálják az egyes irányelvszabályok kialakításakor használt lekérdezésparamétereket. Miután létrehozta az irányelvszabály-típusokat, juttatásra való jogosultsági irányelveket is létrehozhat. Az irányelvek lehetővé teszik szabálygyűjtemények létrehozását, amelyeket egy vagy több jogi személyre alkalmazhat. Minden irányelvben megnézheti a korábban létrehozott juttatásra való jogosultsági irányelvszabály-típusokat. 

A szabály hatáskörét az irányelven belül lehet megadni. Például ha **Vezető** nevű juttatásra való jogosultsági irányelvszabály-típust hoz létre, megadhatjami a szabály az irányelven belül. Ebben a példában minden olyan beosztásra vonatkozik a szabály, amelyben szerepel a „vezető” szó. Miután megadta az irányelvben foglalt szabály, vagy szabályok paramétereit, hozzárendelhet egy specifikus szabályt a juttatáshoz.

<a name="see-also"></a>Lásd még
--------

[Juttatási program meghatározása és kezelése](manage-benefit-program.md)


