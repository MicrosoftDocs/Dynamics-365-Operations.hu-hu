---
title: Dynamics 365 Commerce értékelési környezet GYIK
description: Ez a témakör válaszokat ad a Microsoft Dynamics 365 Commerce értékelési környezettel kapcsolatos gyakori kérdésekre.
author: v-chgri
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1e69aa3cb81dceb7af4cd15536164ac40d234e5fbc7f661612bc84dbb0983837
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712766"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a>Dynamics 365 Commerce értékelési környezet GYIK

[!include [banner](includes/banner.md)]

Ez a témakör válaszokat ad a Microsoft Dynamics 365 Commerce értékelési környezettel kapcsolatos gyakori kérdésekre.

**Használható a Commerce értékelési környezet e-kereskedelmi áruházként a jelenleg Retail alkalmazást megvalósító ügyfeleink esetében?**

Szám A Commerce értékelési környezet csak az értékelésre szolgál. Ha a Retail alkalmazást megvalósító ügyfél számára igényel környezetet, forduljon a Microsofthoz.

**Használható a Commerce értékelési környezet egy Retail alkalmazást megvalósító meglévő alkalmazáson/környezeten az e-kereskedelmi funkciók megvalósítására?**

Nem (többnyire). A Commerce értékelési összetevők csak olyan környezetekben érhetők el, amelyek megfelelnek az előfeltételekben és a létesítési útmutatóban megadott konfigurációknak. Ezenkívül a szükséges alapszintű demóadatok nem lesznek elérhetők olyan környezetekben, amelyeknek a kezdeti kiadása korábbi, mint a 10.0.8. 

**Milyen költségeket von maga után a Commerce értékelési környezet telepítése a Microsoft Azure alkalmazáson a Microsoft Dynamics Lifecycle Services (LCS) segítségével?**

Egy hagyományos Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce központ demókörnyezete (virtuális gép \[VM\]) fog megjelenni az Azure-előfizetésében. Az [Azure árkalkulátorral](https://azure.microsoft.com/pricing/calculator/) megbecsülheti ezt a költséget.

Más összetevők, például a Commerce Scale Unit, a Commerce webhelyépítő és az e-commerce webhely szoftverként, valamint a Microsoft által működtetett „szoftver szolgáltatásként” (SaaS) formájában elérhetővé válik.

**Jelenleg az Azure mely földrajzi régiói támogatottak a Commerce értékelési környezete esetében?**

A Commerce értékelési környezet csak Észak-Amerika területén telepíthető.

**Létezik letölthető virtuális merevlemez (VHD), amely rendelkezik a teljes OneBox virtuális számítógép (VM) opcióval?**

A Dynamics 365 Commerce és a Commerce Scale Unit teljes mértékben „szoftver szolgáltatásként” (SaaS) elven működnek, és a felhőben tároltak.

**Meddig használható a Commerce értékelési környezet?**

A Commerce értékelési környezet 30 napos határidőt tartalmaz attól a naptól számítva, amikor a SaaS-összetevők, például a Commerce Scale Unit, a Commerce webhelyépítő és az e-kereskedelmi webhely létesítése megtörtént.

**Meghosszabbítható a Commerce értékelési környezet időkorlátja?**

A határidő meghosszabbítása inkább kivétel a szabályra, és eseti alapon hoznak döntést róla. Segítségért forduljon a Microsoft-partnere kapcsolattartójához.

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 Commerce értékelési környezet áttekintése](cpe-overview.md)

[Dynamics 365 Commerce értékelési környezet kiépítése](provisioning-guide.md)

[Dynamics 365 Commerce értékelési környezet konfigurálása](cpe-post-provisioning.md)

[BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben](cpe-bopis.md)

[Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása](cpe-optional-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]