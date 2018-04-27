---
title: "Lean szervezeti modellezése"
description: "A cikk a lean szervezet modellezésében szereplő kulcsokról nyújt tájékoztatást."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53141
ms.assetid: 4f272f2f-ec2c-4b0d-a652-00a63b719b9e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: c8e24234cfa54dcbbf3638c31ced7fb83881bb9f
ms.contentlocale: hu-hu
ms.lasthandoff: 03/26/2018

---

# <a name="modeling-a-lean-organization"></a>Lean szervezeti modellezése

[!INCLUDE [banner](../includes/banner.md)]

A cikk a lean szervezet modellezésében szereplő kulcsokról nyújt tájékoztatást. 

A Lean manufacturing eset tipikusan több, mint csupán a nem kapcsolódó kanban-szabályok gyűjteménye vagy az anyagellátási irányelvek összessége. Az anyag és termékáramlás a munkacellákon és egy adott termékre vagy készletre vonatkozó helyszíneken leírható egy sorozatként, vagy a folyamat egy kis hálózataként vagy tranzakciós tevékenységként. A számsorozatot, vagy hálózatot termelési folyamatnak is nevezik.

## <a name="production-flows-in-lean-manufacturing"></a>Termelési folyamatok a Lean manufacturing során
A termelési rendeléseken alapuló termelési esetekben az anyagok egy adott termelési rendeléshez kerülnek kiadásra. A műveletek során az anyagjegyzéken (BOM) és az útvonalakon alapuló műveletek sorozata során létrejönnek a termékek és bevételezésre kerülnek végül a megadott helyen. A termelési rendelések átfutási ideje percekbe vagy hetekbe telhet. Minden kapcsolódó költség, anyag és munka a termelési rendelésben kerül összefoglalásra. 

A szállítási átfutási idők és a munkaközpontokban a kötegtermelés miatt keletkező felesleges készletek csökkentése érdekében a lean manufacturing bevezeti a kanban feltöltést és a gyártásban és a raktárfeltöltésben található szupermarketeket. Ezek a funkciók általában megszakítják a részlegesen független kanban-ciklusok termelését. Egy félkész termékre vonatkozó kanban feltöltést nem indít el egy befejezett termékre vonatkozó rendelés. 

A termelés és a Microsoft Dynamics 365 for Finance and Operations alkalmazásban javasolt különböző kanban-esetek költségkörnyezetének újraindításához, a tevékenység alapú termelési folyamatok alkották a lean manufacturing gerincét. Az összes kanbanszabály erre az előre definiált szerkezetre hivatkozik. A tevékenység-alapú modell támogatja a többféle esetek beállítását, mint a Dynamics AX Lean manufacturing korábbi eseteit. Azonban ez a modell nem adható hozzá az üzemi dolgozók összetettségéhez, mert az összes eset ugyanazt a tevékenység-alapú felhasználói felületet használja.

## <a name="semi-finished-products-non-bom-levels"></a>Félkész termékek (nem BOM-szintek)
A Microsoft Dynamics AX Lean manufacturing egyesíti a raktározott termékek és a félkész termékek kanbanjait egyetlen keretrendszerben, és azonfelül egységes felhasználói tapasztalatot nyújt minden esethez. A kiegészítő architektúra miatt a további Anyagjegyzékszinteket már nem kell bevezetni a félkész termékekhez használatos kanban-ok engedélyezéséhez. A felépítése minimálisra csökkentheti a készlet tranzakcióit.

## <a name="products-and-material-in-work-in-progress"></a>Termékek és anyagok folyamatban
A kötegek méreteinek csökkentése az ideális állapotra a lean manufacturing egyetlen folyamatában drámai növekedést eredményezhet a készlettranzakciókban, ha minden egyes kitárolási folyamat vagy kanbanregisztrálás tranzakciókat hoz létre a felhasznált cikkekhez. A termelési folyamat architektúrája lehetővé teszi az anyagtranszfer számára a termelési folyamathoz a kiszállítási kanbanok tároló vagy szállítási anyagkezelési egységek visszavonását. A kiadott anyagok értéke a termelési folyamathoz kapcsolódó folyamatban lévő termelés számlájához kerül hozzáadásra. Ez a viselkedés hasonlít egy termelési rendelésre kiadott anyag viselkedésére. Ugyanez az elv alkalmazható a termékekhez és a félkész termékekhez. Kivéve, ha ezeket a termékeket létrehoztak, átvittek vagy felhasználtak a termelési folyamatban, a készlettranzakciók választhatók. Miután a termékeket feladták a készletbe, a termelési folyamat befejezetlen termelésszámlája csökken a vonatkozó standard költség visszatérítésével.

## <a name="value-streams-and-value-stream-mapping"></a>Érték-előállítási folyamatok és érték-előállítási folyamat feltérképezése
A Microsoft Dynamics AX Lean manufacturing architektúrája Womack és Jones által megalkotott 5 Lean alapelven alapszik: Vevői érték, Érték-előállítási folyamat, Áramlás, lekérés és tökéletesség. A megvalósító lean manufacturing megoldásokra vonatkozó egy jóváhagyott módszere a gyártás fizikai világában az érték-előállítási folyamat feltérképezése (VSM). Ezt a módszert Rother és Shook a "Tanuljunk meg látni" című publikációjukban vezették be a Lean Manufacturing Intézetben. 

A Dynamics AX-ben a jövőbeli állapotú érték a termelési folyamat verziójaként lehet modellezni. Az érték-előállítási folyamat minden folyamata folyamattevékenységként kerül modellezésre. A mozgásokat vagy átviteleket transzfertevékenységekként lehet modellezni, ha a transzferállapotot regisztrálni kell vagy készletkitárolással, esetleg összevont szállítással ellátott integráció szükséges. 

Az érték-előállítási folyamatot egy üzemi egységként lehet modellezni a Microsoft Dynamics AX-ben. Emiatt az érték-előállítási folyamatot a pénzügyi dimenziókban is lehet használni.

## <a name="costing-for-lean-manufacturing-based-on-the-production-flow"></a>A lean manufacturing költségszámítása a termelési folyamaton alapszik.
A termelési folyamatra vonatkozó költségek időszakos konszolidációja korrigálja az érintett befejezetlen termelés számlát és lehetővé teszi a termelési folyamat által megadott termékek számára meghatározandó variánsokat.

## <a name="continuous-improvement"></a>Folyamatos javítás
A hatékonyabb folyamatos javítás érdekében a termelési folyamatok idő-érvényességi verziókban kerülnek alkalmazásra. Ezért a meglévő termelésifolyamat-verziót az összes kapcsolódó kanban-szabályokkal együtt a termelési folyamat jövőbeli verzióiban másolhatók. Ezenkívül a jövőbeli állami termelési folyamat modellezhető a termelés érvényesítése és aktiválása előtt. A gördülékeny anyagáramlás garantálásához az áttérési dátumon és kívül, a termelési folyamatverziókból származó meglévő kanbanjai automatikusan kapcsolódnak az új verzióhoz.

## <a name="simplicity"></a>Egyszerűség
A Lean manufacturing a Dynamics AX-ben történő feldolgozásához a termelési folyamat és tevékenység megközelítést választjuk, amely lehetővé teszi egyszerű és komplex termelési esetek modellezését egy méretezhető architektúrában. Jobban megvizsgálva a tevékenységkoncepciót egy új egyszerűsítés fedezhető fel, azoknak a felhasználóknak akiknek szükségük van rá: az üzemirányítóknak és a logisztikai dolgozóknak. Készlettranzakció helyett tevékenység alapú feladatok jelentésével egy egységes felhasználói felület alakítható ki az összes lean manufacturing variánshoz, amivel az üzlet bonyolultsága a felhasználói felületről a helyére kerül: a termelési folyamathoz, ami a lean manufacturing gerince.




