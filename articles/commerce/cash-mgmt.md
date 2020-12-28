---
title: Készpénzkezelés fejlesztései
description: Ez a témakör a Dynamics 365 Commerce készpénzkezeléssel kapcsolatos pénztári fejlesztéseit mutatja be.
author: anpurush
manager: AnnBe
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0c561c39dfcbfa739c5a22394c05191e7f9bc107
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412827"
---
# <a name="cash-management-improvements"></a>Készpénzkezelés fejlesztései

[!include [banner](includes/banner.md)]


A készpénzkezelés egy kulcsfontosságú funkció a kiskereskedők számára a fizikai üzletekben. A kiskereskedők azt szeretnék, hogy az üzletekben olyan rendszerek legyenek, amelyek segítik a készpénz teljes nyomon követhetőségét és elszámoltathatóságát, valamint a különböző pénztárgépek és pénztárosok közötti mozgást egy üzletben. Képesnek kell lenniük az esetleges különbségek egyeztetésére és a elszámoltathatóság megállapítására.


A Microsoft Dynamics 365 Commerce rendelkezik készpénzgazdálkodási lehetőségekkel a Pénztár (POS) alkalmazásban. A 10.0.3 verziónál korábbi Retail-verziókban azonban a készpénzkezelési funkciók nem elég megbízhatóak ahhoz, hogy az üzletekben a készpénzmozgások teljes nyomon követhetőségét biztosítsák. Bár a kiskereskedők képesek a készpénz egyeztetésére egy üzletben, nem tudják pontosan meghatározni az elszámoltathatóságot készpénzeltérés esetén.


A Retail 10.0.3 és újabb verzióiban a kiskereskedők számára elérhetővé válik a készpénzkezelés nyomon követhetősége. A nyomon követhetőség részeként a kiskereskedők megadhatnak a széfeket, a kétoldalas készpénz-tranzakciókat végezhetnek, valamint egyeztethetik a készpénzforgalmi tranzakciókat.

## <a name="set-up-traceability-and-define-safes"></a>A nyomon követhetőség beállítása és a széfek megadása

Az új készpénzgazdálkodás funkció beállításához hajtsa végre az alábbi lépéseket az üzletek működési profiljának konfigurálásához.

1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Pénztár beállítása \> Pénztárprofilok \> Funkcióprofilok** menüpontra, és válasszon ki egy olyan működési profilt, amely azokhoz az üzletekhez van kapcsolva, amelyekre vonatkozóan elérhetővé szeretné tenni a készpénzgazdálkodás fejlesztéseit.
2. A működési profil **Funkciók** gyorslapján, a **Speciális készpénzgazdálkodás** pontban állítsa a **Készpénz nyomon követhetőségének engedélyezése** beállítást **Igen** értékre.
3. A széfek beállításához nyissa meg **Kiskereskedelem és kiskereskedelem \> Csatornák \> Áruházak \> Összes áruház** pontot, és válasszon az üzletek közül.
4. Az **Üzletek** oldal műveleti ablaktábláján, a **Beállítás** lapon, a **Beállítás** csoportban válassza ki a **Széfek** lehetőséget. Ezzel a lehetőséggel több széfet is megadhat és karbantarthat egy üzlethez.
4. A funkció használata előtt futtatnia kell a **1070 csatorna konfiguráció** elosztási ütemezési feladatot, hogy ezeket a konfigurációkat szinkronizálja a csatorna-adatbázissal.

## <a name="additional-cash-management-changes"></a>További változások a készpénzkezelésben

A Retail 10.0.3-as és újabb verzióiban a készpénzforgalmi tranzakciókkal kapcsolatos következő lehetőségek is elérhetők:

- Az a felhasználó, akinek a „Nyitó összeg elszámolása” üzenet jelenik meg, meg kell adnia a készpénz forrását. A felhasználó megkeresheti az üzletben meghatározott elérhető széfeket, és kiválaszthatja azt a széfet, amelyből a készpénzt kiveszik, és a pénztárgépbe teszik.
- Az a felhasználó, aki a „fizetőeszköz eltávolítása” műveletre kattint, ki kell választania a nyitott „váltópénzbetét” tranzakciók listájából egy tranzakciót, amellyel szemben a műveletet végzi. Ha a megfelelőváltópénzbetét nem létezik a rendszerben, akkor a felhasználó létrehozhat egy nem csatolt fizetőeszköz-eltávolítási tranzakciót.
- A „váltópénzbetét” művelet felkéri a felhasználót, hogy válasszon a nyitott „fizetőeszköz-eltávolítás” tranzakciók listájából egy olyan tranzakciót, amellyel szemben a váltópénzbetét műveletet végrehajtják. Ha a megfelelő fizetőeszköz-eltávolítás nem létezik a rendszerben, akkor a felhasználó létrehozhat egy nem csatolt váltópénzbetét tranzakciót.
- A „széfes befizetést” végző felhasználónak ki kell választania a széfet, amelybe a készpénzt beteszi.
- Egy üzletben meghatározott széfek esetében a felhasználók kezelhetik a nyitó összeg elszámolását, a váltópénzbetét végrehajtását, a fizetőeszköz-eltávolítást, valamint a banki befizetést.
- Azoknak a felhasználóknak, akik rendelkeznek a megfelelő felhasználói jogosultságokkal, a "műszakok kezelése" műveletekkel az aktív, felfüggesztett és lezárt műszakok készpénzegyenlegét jelenítik meg.
- A műszakon belüli vagy műszakok közötti készpénztranzakciók egyeztetéséhez jelölje be az egyeztetésre váró műszakot, majd válassza az **Egyeztetés** elemet. A megnyitott nézet külön lapokon megjeleníti az egyeztetett és a nem egyeztetett tranzakciók listáját. Ebből a nézetből a felhasználó kiválaszthatja a nem egyeztetett tranzakciókat, és egyeztetheti őket, illetve kiválaszthatja a korábban egyeztetett tranzakciókat, és visszavonhatja egyeztetésüket.
- Ha egyeztetés közben a kiválasztott tranzakció nem kerül egyensúlyba, a felhasználónak meg kell adnia a kiegyenlítetlen egyeztetés okának a leírását. A felhasználók kiválaszthatnak egy tranzakciót, és szükség szerint egyeztetik a releváns ok leírásával.
- A felhasználók a műszak lezárása előtt folytathatják a tranzakciók egyeztetését és egyeztetések visszavonását. A műszak lezárása után nem lehet a tranzakciók egyeztetését visszavonni.
- Amikor egy felhasználó egy műszak zárását választja, a Commerce ellenőrzi, hogy nincsenek-e nem egyeztetett készpénzgazdálkodási tranzakciók a műszakban. A felhasználó nem zárhatja le a műszakot, amíg nem egyeztetett tranzakciók vannak.
