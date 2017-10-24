---
title: "Költségszabályok meghatározása"
description: "Be lehet állítani költségszabályokat, amelyeket a munkatársaknak követniük kell költségjelentések, valamint utazásigénylések megadása és benyújtása során a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerben."
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a>Költségszabályok

[!include[banner](../includes/banner.md)]

Fel lehet állítani a dolgozók által követendő irányelveket (szabályokat) a költségjelentések és utazásigénylések benyújtására vonatkozóan. A költségirányelvek bevezetése segítséget nyújthat a hatékony költségkezeléshez. 

Például felállíthat egy olyan irányelvet, hogy a New York-i szállodaköltség éjszakánként nem haladhatja meg a 250 dollárt. Ha egy dolgozó olyan költségjelentést vagy utazásigénylést nyújt be, amelyben a szobaár meghaladja ezt a szintet, a rendszer értesíti a dolgozót, hogy meghaladta az irányelvben meghatározott költségkeretet. Az irányelv definiálásakor beállíthatja az üzenetet, amelyet a dolgozó megkap. 

Háromféle irányelvet állíthat be: 

 - Figyelmeztetés – lehetővé teszi a dolgozónak, hogy a költségjelentést vagy utazási igénylést nyújtson be, de a program megjelöli a költséget a jóváhagyók számára és  
 későbbi jelentéstételre. 
 - Hiba – a dolgozó a költségjelentés vagy utazásigénylés benyújtása előtt köteles úgy módosítani a költséget, hogy megfeleljen az irányelvnek. 
 - Indoklás – a dolgozónak, illetve a vezetőnek a költségjelentés vagy utazásigénylés benyújtása előtt indoklást kell megadnia, hogy miért lépte át az irányelvben megadott összeget. 

Szintén felállítható egy időintervallum, amelyben a költségirányelvek érvényben vannak. Például a szabadságolások utazási csúcsszezonjában a Magyarország és New York közötti légi közlekedés költsége magasra szökik. Meg lehet adni olyan repülési-költség szabályt, amely 5000 dán koronára korlátozza a New York-i repülőutak költségét, és beállítható, hogy ez a szabály március 15-től szeptember 15-ig legyen érvényben. 

