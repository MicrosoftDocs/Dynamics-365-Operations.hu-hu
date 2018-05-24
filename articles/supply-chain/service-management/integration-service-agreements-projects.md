---
title: "Szolgáltatási szerződések és projektek integrálása"
description: "A szolgáltatási szerződések és soraik műveletei során a Projektvezetés és könyvelés területein beállított adatokat hasznosíthatja."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9f2640eae299411d633c68795bc16883dbb5eeaf
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="integration-for-service-agreements-and-projects"></a>Szolgáltatási szerződések és projektek integrálása 

[!include [banner](../includes/banner.md)]


A szolgáltatási szerződések és soraik műveletei során a **Projektvezetés és könyvelés** következő területein beállított adatokat hasznosíthatja.

## <a name="project-prices"></a>Projektárak

A szolgáltatási szerződés tranzakciójának önköltségi és eladási árát a szerződéshez kapcsolódó projekt önköltségi árbeállításából lehet levezetni. Az önköltségi és eladási árak projektenként, alkalmazottanként és kategóriánként is beállíthatók. 

## <a name="project-validation"></a>Projektellenőrzés

A **Projektvezetés és könyvelés** ellenőrzési beállításaival korlátozni lehet, hogy mely projektek, alkalmazottak és kategóriák legyenek kiválaszthatók a szolgáltatási szerződés soraiban. Az ellenőrzés beállítás segítségével alkalmazottakat, projekteket és kategóriákat kombinálhat a hozzáférés vezérlése céljából. 

## <a name="project-line-properties"></a>Projekt sortulajdonságai

A sortulajdonság egy automatikusan rögzített beállítás minden szolgáltatásiszerződés-sorban.

A sortulajdonságok a **Sortulajdonság** képernyőn hozhatók létre a **Projektvezetés és könyvelés** modulban. A szolgáltatási szerződésen rögzített sortulajdonságot a rendszer csatolja a szolgáltatási szerződéshez kiválasztott projekthez, ebből következően ezt a szolgáltatásiszerződés-sor is örökli. 

## <a name="default-offset-accounts"></a>Alapértelmezett ellenszámlák

Kiadási tranzakció rögzítésekor a program automatikusan kiválasztja az alapértelmezett kiadási ellenszámlát a tranzakcióhoz. Az alapértelmezett költségszámla az aktuális szolgáltatási szerződéshez csatolt projektben állítható be.

## <a name="project-categories"></a>Projektkategóriák

A szolgáltatásiszerződés-sorokban elérhető kategóriák a **Projektkategóriák** képernyőn állíthatók be a **Projektvezetés és könyvelés** modulban. 

> [!NOTE]
> <P>Azok a kategóriák választhatók ki, amelyek <STRONG>Aktív a naplókban</STRONG> jelölőnégyzete be van jelölve a <STRONG>Projektkategóriák</STRONG> képernyő <STRONG>Projekt</STRONG> lapján. Ha azonban az <STRONG>Inaktív kategóriák</STRONG> jelölőnégyzet be van jelölve a <STRONG>Naplók</STRONG> lapon, a <STRONG>Projektvezetési és könyvelési paraméterek</STRONG> képernyőn, minden kategóriát ki lehet választani</P>

## <a name="project-parameters"></a>Projekt paraméterei

Ha a **Kilépett alkalmazottak** mező be van jelölve a **Naplók** lapon, a **Projektvezetési és könyvelési paraméterek** képernyőn, akkor az aktív alkalmazottak mellett az inaktívak is kiválaszthatók a **Szolgáltatási szerződések** és a **Szervizrendelések** képernyőn.

Emellett a **Szervizrendelések** képernyő **Projekt** lapján engedélyezheti a **Kezdő idő** és **Záró idő** mezőket, és ezután kezdő és záró időpontokat határozhat meg a szervizrendeléssorokon.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>A kezdő és záró időpont megadásának engedélyezése a szervizrendelésekhez

1.  Kattintson a **Projektvezetés és könyvelés** \> **Beállítás** \> **Projektvezetési és könyvelési paraméterek** lehetőségre.

2.  Kattintson a **Naplók** lapra, majd jelölje be a **Kezdő és záró időpont megjelenítése** jelölőnégyzetet.

3.  Kattintson a következőkre: **Projektvezetés és könyvelés** \> **Beállítás** \> **Naplók** \> **Naplók nevei**.

4.  Válassza ki a szervizrendeléshez csatolt napló nevét.

5.  Kattintson az **Általános** lapra, majd jelölje be a **Kezdő és záró időpont megjelenítése** jelölőnégyzetet.


> [!NOTE]
> <P>Válassza ki a szervizrendelés naplójának nevét a <STRONG>Szolgáltatáskezelés paraméterei</STRONG> képernyő <STRONG>Naplók</STRONG> lapjának <STRONG>Óra</STRONG> mezőjében.</P>






