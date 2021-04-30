---
title: Áfaszámítás (előzetes verzió)
description: Ez a témakör az adószámítási funkció általános hatókörét és jellemzőit ismerteti.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892349"
---
# <a name="tax-calculation-preview"></a>Áfaszámítás (előzetes verzió)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Az adószámítás egy hiperskálázható több-bérlős szolgáltatás, amely lehetővé teszi a Global Tax Engine számára, hogy automatizálja és egyszerűsítse az adómeghatározási és számítási folyamatot. Az adómotor teljesen konfigurálható. A konfigurálható elemek közé tartozik többek között az adóköteles adatmodell, az adókód, az adóalkalmazási mátrix és az adószámítási képlet. Az adómotor a Microsoft Azure alapszolgáltatási platformon fut, és modern technológiát és exponenciális méretezhetőséget kínál.

Az adószámítás integrálva van a Dynamics 365 Finance és a Dynamics 365 Supply Chain Management szolgáltatásokkal. Végül integrálva lesz a Dynamics 365 Project Operations, Dynamics 365 Commerce és más saját és harmadik féltől származó alkalmazásokkal is.

Az adószámítás egy mikroszolgáltatás-alapú adómotor, amely exponenciális méretezhetőséget kínál. A következő feladatok elvégzésében segíthet Önnek:

- Konfigurálhatja az adószámítást a Regulatory Configuration Service (RCS) szolgáltatáson keresztül. Az RCS az elektronikus jelentéskészítési (ER) tervező továbbfejlesztett változata, és önálló szolgáltatásként érhető el.
- Konfigurálhatja az adómátrixot az adókódok és adómértékek automatikus meghatározásához.
- Konfigurálhatja az adószám automatikus meghatározásához.
- Konfigurálhatja az adószámítás tervezőjét képletek és feltételek meghatározására.
- Megoszthatja az adómeghatározási és számítási megoldást jogi személyek között.

Az adószámítási szolgáltatás használatához telepítse a projektből származó adószámítási szolgáltatásbővítményt az Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásban. Ezután fejezze be a beállítást az RCS-ben, és engedélyezze az adószámítási szolgáltatást a Finance és a Supply Chain Management alkalmazásokban. További tájékoztatás: [Első lépések az adószolgáltatással](./global-get-started-with-tax-calculation-service.md).

## <a name="availability"></a>Elérhetőség

Az adószámítás csak tesztkörnyezetben és kiválasztott ügyfelek számára érhető el egy nyilvános előzetes programon keresztül. Végül általánosan elérhetővé válik minden ügyfél számára és éles környezetekben is.

Folyamatosan érkeznek az új funkciót, ezért győződjön meg róla, hogy gyakran ellenőrizze a legfrissebb dokumentációt, hogy megismerje a támogatott szolgáltatások kiterjedését és hatókörét.

Az adószámítás a következő Azure-földrajzi területeken van telepítve. Más Azure földrajzi területeken is be lesz vezetve az ügyfelek igényeinek megfelelően:

- Amerikai Egyesült Államok
- Európa

> [!NOTE]
> Az adószámítás nem támogatja a Dynamics 365 helyszíni telepítését. Nem támogatja a korábbi verziókat sem, például a Dynamics AX 2012-t.

## <a name="feature-highlights"></a>A funkció újdonságai

- Konfigurálható adómátrix az adókódok és adó automatikus meghatározásához és számításához
- Több adónyilvántartási szám támogatása
- Átmozgatási rendelés támogatása az adó meghatározásához és kiszámításához
- Átmozgatási rendelés támogatása több adóregisztrációs szám meghatározásához

## <a name="supported-transactions"></a>Támogatott tranzakciók

Az adószámítást jogi személy és tranzakció engedélyezheti. A varázsló a következő tranzakciókat támogatja:

- Értékesítési folyamat

    - Értékesítési ajánlat
    - Értékesítési rendelés
    - Visszaigazolás
    - Kitárolási lista
    - Szállítólevél
    - Értékesítési számla
    - Jóváírás
    - Visszárurendelés
    - Fejléc vegyes költségek
    - Sor vegyes költsége

- Beszerzési folyamat

    - Beszerzési rendelés
    - Visszaigazolás
    - Bevételezések listája
    - Termékbevételezés
    - Beszerzési számla
    - Fejléc vegyes költségek
    - Sor vegyes költsége
    - Jóváírás
    - Visszárurendelés
    - Beszerzési igénylés
    - A beszerzési igénylési sor vegyes díja
    - Ajánlatkérés
    - Ajánlatkérés fejlécének vegyes díja
    - Ajánlatkérés sorának vegyes díja

- Készletfolyamat

    - Átmozgatási rendelések – szállítás
    - Átmozgatási rendelés – bevételezés

## <a name="related-resources"></a>Kapcsolódó erőforrások

[Az adószolgáltatás első lépései](./global-get-started-with-tax-calculation-service.md)

[Több adószám](./emea-multiple-vat-registration-numbers.md)

[Adófunkció támogatása átmozgatási rendeléshez](./tasks/tax-feature-support-for-transfer-order.md)

[Hogyan építsünk bővítményt az adószolgáltatásban?](./tax-service-add-data-fields-tax-integration-by-extension.md)