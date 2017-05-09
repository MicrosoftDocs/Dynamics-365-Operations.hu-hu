---
title: "POS alkalmazást, és a felhasználó nyelvi beállítások"
description: "Ez a témakör azt mutatja be, hogyan végezhető el a Retail Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf5b75572529bb497d3079752de187f30aa59294
ms.lasthandoff: 03/31/2017


---

# <a name="pos-application-and-user-language-settings"></a>POS alkalmazást, és a felhasználó nyelvi beállítások

[!include[banner](includes/banner.md)]


Ez a témakör azt mutatja be, hogyan végezhető el a Retail Modern POS (MPOS) és a felhőalapú POS nyelvének módosítása.

<a name="overview"></a>Áttekintés
========

A Retail Modern POS (MPOS) és a felhőalapú POS támogatja az olyan környezeteket, ahol a nyelvi beállítás és a fordítás eltérhetnek egymástól az üzlet- és felhasználói beállításoknál. Például az üzlet olyan területen is lehet, ahol az angol a leggyakrabban használt nyelv az ügyfelek körében, de egyes munkavállalók inkább francia fordításban szeretnék használni az alkalmazást.

## <a name="data-language"></a>Adatnyelv
A felhasználói beállításoktól függetlenül az MPOS és a felhőalapú POS mindig az üzlet nyelvi beállításait használja az adatokhoz használt fordítások meghatározásához. Ez biztosítja, hogy a felhasználók és a vevők következetes felhasználói élményt kapjanak.  Néhány példa az adatokra:

-   Termékek
-   Sorattribútumok értékei
-   Kategórianév
-   Nyomtatott vagy e-mailben küldött nyugták
-   Fizetési mód neve
-   Sormegjelenítési paraméterek

Az üzlet nyelve lesz a fő POS bejelentkezési képernyő nyelve is, mivel a felhasználó a bejelentkezés előtt nem ismert. Ha az üzlet nyelvéhez nem érhető el fordítás, a pénztár visszaáll a vállalat nyelvére.

### <a name="configuring-the-stores-language-setting"></a>Az üzlet nyelvbeállítás konfigurálása

Az üzlet nyelvének beállítása a **Minden kiskereskedelmi egység** részben történik a **Kiskereskedelmi üzlet** oldalon az **Általános &gt; Területi beállítások &gt; Nyelv részben. ** Használja a legördülő menüt minden egyes üzlet nyelvének kiválasztásához.

## <a name="user-interface-language"></a>Felhasználói felület karbantartása
A POS-felhasználó nyelvi beállítás határozza meg a felhasználói felületen használt fordításokat. Ez magában foglalja az összes feliratot, menüt és listát, amelyek nem minősülnek adatnak. Egyetlen kivétel ez alól a POS-gombrácson megjelenő szöveg. A gombrácsok nem támogatják a fordításokat, így mindig a gombon definiált szöveget jelenítik meg. A lefordított gombok támogatásához külön gombrácsokat kell másolni és karbantartani, valamint a felhasználókhoz rendelni szükség szerint.

### <a name="configuring-the-users-language-setting"></a>Az üzlet nyelvbeállítás konfigurálása

A pénztárfelhasználó nyelvének beállítása a **Minden dolgozó** részben történik a **Dolgozó** lapon, a **Kiskereskedelem &gt; Nyelv** alatt.  Nincs beállítva a fő Profil lapon.  Ez a beállítás nincs használatban a pénztár esetében. A felhasználó nyelve nincs beállítva, vagy a változó értéke egy nyelvet Ha fordítások nem állnak rendelkezésre, ha az üzlet nyelv visszaáll a POS-nál.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | **Felhasználói felület nyelve** ** **      | **Adatok nyelv (termékek nyugtaformátumokat, sorkijelző, stb.)** |
| **Vállalat** | Alapértelmezett                    | Alapértelmezett                                                           |
| **Üzlet**   | Felülbírálja a vállalat          | Felülbírálja a vállalat                                                 |
| **Felhasználó**    | Felülbírálás üzlet vagy a vállalat | Soha                                                             |






