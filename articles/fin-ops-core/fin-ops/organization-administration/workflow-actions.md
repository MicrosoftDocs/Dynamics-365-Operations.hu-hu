---
title: Jóváhagyási folyamatok műveletei
description: Ez a cikk ismerteti a munkafolyamat elfogadási folyamatának egyes résztvevői által vállalható műveleteket.
author: ChrisGarty
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56411
ms.assetid: 65fb711c-6474-42d1-81ed-ca657c29bf1f
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df08bdffb2bda67269eec9f1572bd76af9ae1e11
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747177"
---
# <a name="actions-in-workflow-approval-processes"></a>Jóváhagyási folyamatok műveletei

[!include [banner](../includes/banner.md)]

Ez a cikk ismerteti a munkafolyamat elfogadási folyamatának egyes résztvevői által vállalható műveleteket.

A munkafolyamat több csoportot is tartalmazhat: a létrehozó, a feladathoz hozzárendelt személyek, döntéshozók, valamint jóváhagyók. Például, az alábbi a költségjelentés munkafolyamatánál Balázs a létrehozó, a várólista tagjai a hozzárendelt személyek, János a döntéshozó, illetve Ferenc, Zsuzsanna és Anna a jóváhagyók.

[![Munkafolyamat\_WithManualDecision](./media/workflow_withmanualdecision.gif)](./media/workflow_withmanualdecision.gif)

Az alábbi szakaszok leírják az egyes csoportok által a munkafolyamatban végrehajtható műveleteket.

## <a name="actions-that-an-originator-can-perform"></a>A létrehozó által végrehajtható műveletek

A létrehozó a munkafolyamat egy példányát dokumentum feldolgozásra vagy jóváhagyásra történő elküldésével indítja el. Például, Balázs kattintson a **Küldés** gombra a **Költségjelentés** lapon, hogy benyújtsa a költségjelentést.

## <a name="actions-that-a-task-assignee-can-perform"></a>A feladat megbízottja által végrehajtható műveletek

Egy feladatot végezhet több személy, vagy egy munkatétel-várólista, amit néhány ember felügyel. Azonban egy feladatot csak egy ember fejezhet be. Például Balázs elküldött egy költségjelentést, és a nyugtáit a szervezetének költségjelentési részlegébe küldte ellenőrzésre.

A Kalandorbolt költségjelentési részlegének tagjai követik nyomon a várólistát. Ágnes, annak a részlegnek az egyik tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségjelentését és nyugtáit. A következő műveletek egyikét hajthatja most végre: elutasíthatja, delegálhatja, módosíthatja a kérést, újra hozzárendelhet vagy kiadhatja.

> [!NOTE]
> Az elérhető műveletek változhatnak, attól függően, hogy a szoftverfejlesztő hogyan tervezte meg a feladatot.

### <a name="complete"></a>Befejezés

Amikor egy felhasználó befejez egy feladatot, a feldolgozásra küldött dokumentumot a rendszer szükség esetén a munkafolyamat következő felhasználójához rendeli hozzá. Amennyiben nincs szükség további feldolgozásra, a munkafolyamat befejeződik.

Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit. Miután Ágnes befejezte az ellenőrzést, a dokumentum Jánoshoz kerül.

### <a name="reject"></a>Elutasítás

Amikor egy felhasználó elutasítja a dokumentumot, a munkafolyamat véget ér.

Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit. Ha Ágnes visszautasítja a költségjelentést, a munkafolyamat befejeződik.

Balázs ezután újraküldheti a költségjelentést. Akkor módosíthatja is először, vagy dönthet úgy, hogy újraküldi az eredeti verziót. Ha Balázs újraküldi a költségjelentést, akkor a munkafolyamat a manuális ellenőrzési folyamatnál kezdődik.

### <a name="delegate"></a>Delegált

Amikor egy felhasználó feladatot delegál, másik felhasználóhoz rendeli hozzá a feladatot.

Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit. Ágnes ezt a feladatot Timihez delegálja, aki az ő asszisztense.

Timi ezután Ágnes nevében jár el. Ezért mikor Timi befejezi az ellenőrzést, a költségjelentés Jánoshoz kerül, mintha Ágnes fejezte volna be a feladatot.

### <a name="request-change"></a>Változtatás kérése

Amikor az egyik felhasználó az elküldött dokumentum változtatását kéri, a dokumentumot visszaküldi a rendszer a létrehozónak.

Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit. Ágnes talál néhány hibát a jelentésben, ezért változtatásokat kér. A költségjelentés visszakerül Balázshoz.

Balázs ezután újraküldheti a költségjelentést. Elvégezheti a javasolt változtatásokat, vagy dönthet úgy, hogy újraküldi az eredeti verziót. Ha Balázs újraküldi a költségjelentést, a munkatétel-várólista egyik tagjának ellenőriznie kell a jelentést és a nyugtákat ismét.

### <a name="reassign"></a>Ismételt hozzárendelés

A munkatétel-várólista tagjai átadhatják a várólistán szereplő dokumentumokat egy másik várólistának.

Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja követi nyomon a várólistát. A munkaterhelés elosztásának érdekében Ágnes áthelyezheti a költségjelentést és a hozzá tartozó nyugtákat egy másik várólistához.

### <a name="release"></a>Kiadás

Néha előfordul, hogy egy munkatétel-várólista tagja elfogad egy feladatot, majd később úgy dönt, hogy nem tudja befejezni azt. Ebben az esetben az a személy, aki elfogadta a feladatot, kiadhatja a dokumentumot, vissza a munkatétel-várólistára.

Például Ágnes, a Kalandorbolt költségjelentési részlegének tagja, elfogadta a feladatot, hogy ellenőrizze Balázs költségvetését és nyugtáit. Ha Ágnes úgy dönt, hogy nem tudja végrehajtani a feladatot, kiadhatja a dokumentumot. A költségjelentés visszakerül a várólistára, így a Kalandorbolt költségjelentési részlegének további tagjai elvégezhetik a feladatot.

## <a name="actions-that-a-decision-maker-can-perform"></a>A feladat döntéshozója által végrehajtható műveletek

Általában egy dokumentum van a döntéshozóhoz rendelve, mert van egy kérdés, amit a döntéshozónak meg kell válaszolni. A válasz a kérdésre általában **Igen** vagy **Nem**, vagy **Igaz** vagy **Hamis**. Ha a döntés készítője nem választja ki az egyik választ, delegálhatja a döntést.

### <a name="choice-1-or-choice-2"></a>\[1. lehetőség\] vagy \[. lehetőség\]

A döntéshozónak választ kell adnia egy, a dokumentumot érintő kérdésre. A válasz a kérdésre általában **Igen** vagy **Nem**, vagy **Igaz** vagy **Hamis**. A döntéshozó válasza fogja eldönteni, hogy a dokumentum feldolgozása melyik munkafolyamat-ágon fog elindulni.

Például, Balázs költségjelentése Jánoshoz van rendelve. Jánosnak el kell döntenie, hogy a dokumentumban található információ miatt felhívja-e Balázs menedzserét. Ha János úgy dönt, hogy szükséges a hívás, a költségjelentés Ilonához lesz rendelve, akinek fel kell hívnia Balázs menedzserét. Ha János úgy dönt, hogy nem szükséges a hívás, a költségjelentés Ferenchez lesz rendelve jóváhagyásra.

### <a name="delegate"></a>Delegált

Mikor a döntéshozó delegálja a döntést, a dokumentum egy másik felhasználóhoz lesz rendelve, akinek meg kell hoznia a döntést.

Például, Balázs költségjelentése Jánoshoz van rendelve. János Máriához, az asszisztenséhez delegálja a döntést.

Mária ezután János nevében jár el. Ha Mária úgy dönt, hogy szükséges a hívás, a költségjelentés Ilonához lesz rendelve, akinek fel kell hívnia Balázs menedzserét. Ha Mária úgy dönt, hogy nem szükséges a hívás, a költségjelentés Ferenchez lesz rendelve jóváhagyásra.

## <a name="actions-that-an-approver-can-perform"></a>A jóváhagyó által végrehajtható műveletek

Amikor a dokumentum a jóváhagyóhoz jut, a jóváhagyó a következő műveletek valamelyikét végezheti el: jóváhagyás, visszautasítás, delegálás vagy változtatás kérése.

### <a name="approve"></a>Jóváhagyás

Amikor a jóváhagyó jóváhagyja a dokumentumot, a rendszer szükség esetén a munkafolyamat következő felhasználójához rendeli hozzá azt. Amennyiben nincs szükség további feldolgozásra, a munkafolyamat befejeződik.

Például, Balázs elküldött egy 6000 USD dollárról szóló költségjelentést, és a dokumentum Ferenchez lett rendelve. Ha Ferenc jóváhagyja a dokumentumot, akkor az Zsuzsannához kerül jóváhagyásra. Miután Zsuzsanna jóváhagyja a költségjelentést, a munkafolyamat befejeződik.

### <a name="reject"></a>Elutasítás

Amikor a jóváhagyó elutasítja a dokumentumot, a munkafolyamat véget ér.

Például, Balázs elküldött egy 12,000 USD dollárról szóló költségjelentést, és a dokumentum Zsuzsannához lett rendelve. Ha Zsuzsanna visszautasítja a költségjelentést, a munkafolyamat befejeződik.

Balázs ezután újraküldheti a költségjelentést. Elvégezhet változtatásokat, vagy újraküldheti a költségjelentés eredeti verzióját. Ha Balázs újraküldi a költségjelentést, akkor a munkafolyamat újrakezdődik a jóváhagyási fázistól.

### <a name="delegate"></a>Delegált

Amikor a jóváhagyó feladatot delegál, másik felhasználóhoz rendeli hozzá a dokumentumot jóváhagyásra.

Például, Balázs elküldött egy 12,000 USD dollárról szóló költségjelentést, és a dokumentum Ferenchez lett rendelve. Ferenc delegálja a költségjelentést Annának.

Anna ekkor Ferenc nevében jár el. Ez azt jelenti, hogy miután Anna jóváhagyta a dokumentumot, az ugyanúgy Zsuzsannához kerül jóváhagyásra, mintha Ferenc hagyta volna jóvá. Miután Zsuzsanna jóváhagyta, a dokumentum Annához kerül jóváhagyásra.

### <a name="request-change"></a>Változtatás kérése

Amikor a jóváhagyó a dokumentum változtatását kéri, a dokumentumot visszaküldi a rendszer a létrehozónak.

Például, Balázs elküldött egy 12,000 USD dollárról szóló költségjelentést, és a dokumentum Zsuzsannához lett rendelve. Ha Zsuzsanna változtatást kér, akkor költségjelentés visszakerül Balázshoz.

Balázs ezután újraküldheti a költségjelentést. Elvégezheti a javasolt változtatásokat, vagy újraküldheti a költségjelentés eredeti verzióját. Ha Balázs visszaküldi a költségjelentést, akkor az Ferenchez kerül vissza jóváhagyásra, ugyanis Ferenc a jóváhagyás folyamatának első jóváhagyója.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]