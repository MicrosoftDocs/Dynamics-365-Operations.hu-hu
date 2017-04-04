---
title: "POS alkalmazást, és a felhasználó nyelvi beállítások"
description: "Ez a témakör ismerteti a kiskereskedelmi Modern POS (MPOS) és a felhő POS nyelvi beállítások módosítása."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
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

Ez a témakör ismerteti a kiskereskedelmi Modern POS (MPOS) és a felhő POS nyelvi beállítások módosítása.

<a name="overview"></a>Áttekintés
========

Kiskereskedelmi Modern POS (MPOS) és a felhő POS támogatja a környezetben, ahol nyelvi beállítások és a fordítások eltérhetnek egymástól a tároló és a felhasználói beállításokat. Például a tároló kell található terület, ahol angol leggyakrabban az ügyfelek számára, de egyes munkavállalók szeretné használni az alkalmazás francia fordítás.

## <a name="data-language"></a>Adatnyelv
A felhasználói beállítások, függetlenül MPOS és felhő POS mindig használja az üzlet nyelvi beállítások meghatározásához használt adatokat a fordításokat. Ez biztosítja, hogy a felhasználók és a vevők lesz következetes.  Az adatok közé tartoznak:

-   Termékek
-   Sorattribútumok értékei
-   Kategórianév
-   Nyomtatott vagy e-mailben küldött nyugták
-   Fizetési mód neve
-   Sormegjelenítési paraméterek

Az üzlet nyelv lesz is a fő POS bejelentkezési képernyő óta a felhasználói bejelentkezés előtt nem ismert. Fordítását az üzlet nyelvhez nem érhető el, ha a vállalat nyelve visszaáll a POS.

### <a name="configuring-the-stores-language-setting"></a>Az üzlet nyelvbeállítás konfigurálása

Az üzlet nyelvi beállítása a **minden kiskereskedelmi üzletek** a a **Retail Store** alatt oldal ** általános &gt;területi beállítások &gt;nyelv. ** Használja a közvetlen le minden egyes üzlethez nyelvének kiválasztása.

## <a name="user-interface-language"></a>Felhasználói felület karbantartása
A POS-felhasználó nyelvi beállítás határozza meg a felhasználói felületen használt fordításokat. Ez magában foglalja az összes feliratok, menük és listák, amelyek nem minősülnek adatokat. Egyetlen kivétel ez alól a POS-gombrács megjeleníteni kívánt szöveget. A gombrácsokat nem támogatják a fordításokat, így azok mindig jelennek meg a szöveget, a gombon definiált. Lefordított gombok támogatásához is kell másolni, és külön gombrácsok karbantartása, és rendelje hozzá a felhasználók szükség szerint.

### <a name="configuring-the-users-language-setting"></a>Az üzlet nyelvbeállítás konfigurálása

A POS felhasználói nyelvének beállítása a **minden munkavállaló** a a **dolgozó** a lap **kiskereskedelmi &gt;nyelv**.  Nincs beállítva a fő profil lapon.  POS nem használja ezt a beállítást. A felhasználó nyelve nincs beállítva, vagy a változó értéke egy nyelvet Ha fordítások nem állnak rendelkezésre, ha az üzlet nyelv visszaáll a POS-nál.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | **A felhasználói felület nyelve** ** **      | **Adatok nyelv (termékek nyugtaformátumokat, sorkijelző, stb.)** |
| **Vállalat** | Alapértelmezett                    | Alapértelmezett                                                           |
| **Üzlet**   | Felülbírálja a vállalat          | Felülbírálja a vállalat                                                 |
| **User**    | Felülbírálás üzlet vagy a vállalat | Soha                                                             |




