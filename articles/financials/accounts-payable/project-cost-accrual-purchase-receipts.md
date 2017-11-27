---
title: "Projektköltségek könyvelése beszerzési elismervényekkel"
description: "Ez a témakör leírja, hogy a beszerzési elismervényekkel elszámolt projektköltségek hogyan követhetők nyomom a Microsoft Dynamics 365 for Finance and Operations Enterprise edition programban."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0b54d48d5734cdbfba4a5de4356bff37c0a8d2d3
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="project-cost-accrual-on-purchase-receipts"></a>Projektköltségek könyvelése beszerzési elismervényekkel

[!include[banner](../includes/banner.md)]


Ez a témakör leírja, hogy a beszerzési elismervényekkel elszámolt projektköltségek hogyan követhetők nyomom a Microsoft Dynamics 365 for Finance and Operations Enterprise edition programban. 

A projekt számlái gyakran érkeznek később az árukhoz és a szolgáltatásokhoz képest, amely jelentős hatással lehet a projekt fő teljesítménymutatóira (KPI). Fontos, hogy ezeket a tranzakciókat nyomon követhessük a pénzügyi és a projektjelentésekben.

Az alábbi példa forgatókönyv ezt ábrázolja. 

A Contoso Consulting elindított egy új felhőtelepítési projektet. A beszerzési rendelést hoztak létre egy számítógép megvásárlására a projekt számára. A számítógép ára 1500 USA dollár, a telepítési szolgáltatás ára 150 USA dollár. A szállító leszállította és telepítette a számítógépet, de a számlát még nem kapta meg a Contoso Consulting. A projektmenedzser látni szeretné az 1650 USA dolláros projektköltség elhatárolását, még a számla érkezése előtt. A költségnek a vállalat hónap vége pénzügyi kimutatásában is tükröződnie kell. 

Az elhatárolt költséget jelentési célokra pénzügyi szinten és a projekt szintjén is rögzíteni kell. A Finance and Operations esetében a termékbevételezés pénzügyi frissítése a cikk és a beszerzés kategóriákban követhető nyomon. 

A cikkek esetében a **Kötelezettségek paraméterei** lapon válassza a **Termékbevételezés feladása a főkönyvben** lehetőséget.
[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png) 

A beszerzési kategóriák esetében a **Kategória-irányelvszabály** lapon adja meg a **Beszerzés** házirendet, és válassza ki a **Nyugta szerinti beszerzési költség** lehetőséget minden beszerzési kategóriához.
[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png) 

A rendszer a **Beszerzési kiadás, nem számlázott** és a **Beszerzés, elhatárolás** számlákat használja a **Feladás beállítása** részben a termékbevételezéshez kapcsolódó bizonylatok feladásakor.
[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png) 

Ugyanazt a forgatókönyvet használva nézzük meg, hogyan befolyásolja egy termékbevételezés feladása a főkönyv és a projekt adatait. 

**1. lépés:** Új beszerzési rendelés létrehozása és megerősítése a projekt számára a következő rögzítéséhez: számítógép vásárlása 1500 USA dollárért, valamint telepítési szolgáltatás 150 USA dollárért.
[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png) 

Amikor a beszerzési rendelés megerősítést nyer, a vállalt költségekhez tranzakciók jönnek létre a projekthez. 
[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png) 

> [!NOTE]
> A vállalt költség tranzakciókhoz a **Tranzakció eredete** mező értéke **Beszerzési rendelés** lesz. A beszerzési rendelés létrehozása és megerősítése nem hoz létre tranzakciókat a projekthez. 

**2. lépés:** Az árukat és szolgáltatásokat leszállítják, és egy szállítólevél regisztrálása történik. 

A termékbevételezés feladása bizonylat létrehozását főkönyvbe való feladását váltja ki. A bizonylat tartozik elemként kerül fel a beszerzési kiadások, nem számlázott kiadások és beszerzési jóváírás elhatárolása számlára. 
[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)

> [!NOTE]
> A termékbevételezés feladása a beszerzési kategóriák és a termékek feladási beállítását használja, és nem a projektkategóriák feladási beállítását. Annak érdekében, hogy megfelelően tükröződjön a beszerzési elhatárolások pénzügyi hatása, a beállítást igazítani kell. 

A **Beszerzési kategória** oldalon elvégezhető a projektkategóriák és a beszerzési kategóriák leképezése.
[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)

**3. lépés:** Szállítóiszámla-tervezet létrehozása. 

A Finance and Operations esetében egy termékbevételezés feladása nincs hatással a projektinformációkra. Megkerülő megoldásként közvetlenül a termékbevételezés feladása után létrehozható egy szállítóiszámla-tervezet. Keresse fel a következőt: **Beszerzési rendelés** lap &gt; **Számla lap** &gt; **Létrehozás** &gt; **Számla**. Ez létrehoz egy függőben lévő számladokumentumot, amely frissíti a projekt adatait. 

A szállítóiszámla-tervezet létrehozása függő projekttranzakciókat hoz létre. 
[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png) 

A **Vállalt költség** lapon, az 1. lépésben létrehozott bejegyzéseket a rendszer lezárja, és új rekordokat hoz létre, hogy tükrözze a függőben lévő szállítói számláról származó költség-kötelezettségvállalás. A **Tranzakció eredete** mező beállítása a vállalt költséghez **Szállítói számla** lesz.
[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)

A szállítói számla függő állapotban marad, amíg a tényleges szállítói számla megérkezik.




