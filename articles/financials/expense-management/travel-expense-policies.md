---
title: "Költségszabályok meghatározása"
description: "Be lehet állítani költségszabályokat, amelyeket a munkatársaknak követniük kell költségjelentések, valamint utazásigénylések megadása és benyújtása során a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszerben."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: b52fe81015a324bde07f387b42b834b79dc7c2da
ms.contentlocale: hu-hu
ms.lasthandoff: 03/13/2018

---

# <a name="expense-policies"></a>Költségszabályok

[!include[banner](../includes/banner.md)]

Fel lehet állítani a dolgozók által követendő irányelveket (szabályokat) a költségjelentések és utazásigénylések benyújtására vonatkozóan.         
A költségirányelvek bevezetése segítséget nyújthat a hatékony költségkezeléshez.         

Például felállíthat egy olyan irányelvet, hogy a New York-i szállodaköltség éjszakánként nem haladhatja meg a 250 dollárt.       
Ha a dolgozó benyújt egy költségjelentést vagy egy utazási igénylést, amelyben a szobaár meghaladja ezt az összeget, a rendszer értesíti a        
dolgozót, hogy a házirend szerinti költségösszeg túl lett lépve. Az irányelv definiálásakor beállíthatja az üzenetet, amelyet a dolgozó megkap        
.      
        
Háromféle irányelvet állíthat be:         
        
- Figyelmeztetés – lehetővé teszi a dolgozónak, hogy a költségjelentést vagy utazási igénylést nyújtson be, de a program megjelöli a költséget a jóváhagyók számára és        
későbbi jelentéstételre.        

- Hiba – a dolgozó a költségjelentés vagy utazásigénylés benyújtása előtt köteles úgy módosítani a költséget, hogy megfeleljen az irányelvnek.       
 
 - Indoklás – a dolgozónak, illetve a vezetőnek a költségjelentés vagy utazásigénylés benyújtása előtt indoklást kell megadnia, hogy miért lépte át az irányelvben megadott összeget.        
 
 Szintén felállítható egy időintervallum, amelyben a költségirányelvek érvényben vannak. Például a repülőjegyek Dánia      
 és New York között magasra szökhetnek a szabadságolások csúcs utazási időszaka alatt. Definiálni lehet egy repülési költségszabályt, amely      
 5000 DKK-ra korlátozza a New York-i repülőutak költségét, és megadhatja, hogy ez a szabály március 15. és      
 szeptember 15. között legyen érvényben.

