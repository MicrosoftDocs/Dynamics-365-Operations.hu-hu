---
title: Minőségbiztosítási tesztműszerek
description: Ez a témakör azt mutatja be, hogyan lehet tesztműszereket létrehozni, amelyek a minőségi rendelések tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3806ca26b8909b03768dad54ddad0084e1cea4a6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021732"
---
# <a name="quality-management-test-instruments"></a><span data-ttu-id="c273f-103">Minőségbiztosítási tesztműszerek</span><span class="sxs-lookup"><span data-stu-id="c273f-103">Quality management test instruments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c273f-104">Ez a témakör azt mutatja be, hogyan lehet tesztműszereket létrehozni, amelyek a minőségi rendelések tesztjeihez használhatók a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="c273f-104">This topic describes how to create test instruments that can be used for tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="c273f-105">A **Teszteszközök** lapon lehet meghatározni és megtekinteni a minőségi rendeléseken végzett tesztekhez használt eszközök részletes adatait.</span><span class="sxs-lookup"><span data-stu-id="c273f-105">You use the **Test instruments** page to define and view details about the devices that are used to perform tests on quality orders.</span></span> <span data-ttu-id="c273f-106">Ezek a műszerek opcionálisak.</span><span class="sxs-lookup"><span data-stu-id="c273f-106">Test instruments are optional.</span></span> <span data-ttu-id="c273f-107">A minőségbiztosító dolgozóknak segíthet ezzel, hogy tudják, milyen eszközt vagy szerszámot kell használniuk egy adott teszt elvégzéséhez.</span><span class="sxs-lookup"><span data-stu-id="c273f-107">However, they can help quality workers know which device or tool they should use to perform a specific test.</span></span>

## <a name="test-instrument-example"></a><span data-ttu-id="c273f-108">Tesztműszer – példa</span><span class="sxs-lookup"><span data-stu-id="c273f-108">Test instrument example</span></span>

<span data-ttu-id="c273f-109">Különféle teszteket végez a elektromos alkatrészeken.</span><span class="sxs-lookup"><span data-stu-id="c273f-109">You're performing various tests on electrical components.</span></span> <span data-ttu-id="c273f-110">Egyes tesztek az összetevők kimeneti feszültéségét ellenőrzik, egy teszt a hőmérsékletüket, és egy teszt a súlyukat.</span><span class="sxs-lookup"><span data-stu-id="c273f-110">Some tests are for the voltage output of the components, one test is for their temperature, and one test is for their weight.</span></span> <span data-ttu-id="c273f-111">Az egyes tesztek végrehajtásához különböző szerszámok, eszközök és berendezések használhatók.</span><span class="sxs-lookup"><span data-stu-id="c273f-111">Different tools, devices, or equipment is used to perform each test.</span></span> <span data-ttu-id="c273f-112">Például egy voltmérő segítségével mérik a feszültséget a hőmérsékletet egy hőmérővel, a súly mérésére pedig mérleget használnak.</span><span class="sxs-lookup"><span data-stu-id="c273f-112">For example, a voltage meter is used to measure voltage, a thermometer is used to measure temperature, and a scale is used to measure weight.</span></span> <span data-ttu-id="c273f-113">Ezeket az eszközöket konfigurálni lehet tesztműszerként, és jelezni lehet, hogy a teszteredményeket milyen mértékegységgel kell rögzíteni.</span><span class="sxs-lookup"><span data-stu-id="c273f-113">You can configure each of these devices as a test instrument and indicate the unit of measure that the test results should be recorded in.</span></span> <span data-ttu-id="c273f-114">Például a feszültségmérő eredményeit a voltokban rögzítik, a hőmérőből származó eredményeket Fahrenheitben vagy Celsiusban, a mérlegből származó eredményeket pedig fontban vagy kilogrammban rögzíti a rendszer.</span><span class="sxs-lookup"><span data-stu-id="c273f-114">For example, results from the voltage meter are recorded in volts, results from the thermometer are recorded in degrees Fahrenheit or degrees Celsius, and results from the scale are recorded in pounds or kilograms.</span></span>

## <a name="create-a-test-instrument"></a><span data-ttu-id="c273f-115">Tesztműszer létrehozása</span><span class="sxs-lookup"><span data-stu-id="c273f-115">Create a test instrument</span></span>

1. <span data-ttu-id="c273f-116">Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztműszerek** elemre.</span><span class="sxs-lookup"><span data-stu-id="c273f-116">Go to **Inventory management \> Setup \> Quality control \> Test instruments**.</span></span>
1. <span data-ttu-id="c273f-117">A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.</span><span class="sxs-lookup"><span data-stu-id="c273f-117">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="c273f-118">Ezután új sorhoz állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="c273f-118">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="c273f-119">**Tesztműszer** – Adja meg a tesztműszer egyedi azonosítóját vagy nevét.</span><span class="sxs-lookup"><span data-stu-id="c273f-119">**Test instrument** – Enter a unique ID or name for the test instrument.</span></span>
    - <span data-ttu-id="c273f-120">**Leírás** – Adja meg a tesztműszer részletes leírását.</span><span class="sxs-lookup"><span data-stu-id="c273f-120">**Description** – Enter a detailed description of the test instrument.</span></span>
    - <span data-ttu-id="c273f-121">**Egység** – válassza ki a mértékegységet, amelyben a tesztműszer mér.</span><span class="sxs-lookup"><span data-stu-id="c273f-121">**Unit** – Select the unit that the instrument measures results in.</span></span> <span data-ttu-id="c273f-122">A Program automatikusan bejelzi a **Pontosság** mezőt a kiválasztott mértékegység alapján.</span><span class="sxs-lookup"><span data-stu-id="c273f-122">The **Precision** field is automatically set, based on the unit that you select.</span></span>

1. <span data-ttu-id="c273f-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c273f-123">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c273f-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c273f-124">Additional resources</span></span>

- [<span data-ttu-id="c273f-125">Minőségbiztosítási teszt</span><span class="sxs-lookup"><span data-stu-id="c273f-125">Quality management test</span></span>](quality-tests.md)
- [<span data-ttu-id="c273f-126">Minőségbiztosítási tesztcsoportok</span><span class="sxs-lookup"><span data-stu-id="c273f-126">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
