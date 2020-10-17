---
title: 'Lync Server 2013: Windows를 기반으로 하지 않는 장치에 대해 QoS를 사용 하도록 설정'
description: 'Lync Server 2013: Windows를 기반으로 하지 않는 장치에 대해 QoS를 사용 하도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a09aaea599a28dae9bd2c227439da86e8761b10d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546454"
---
# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="e9d6e-103">Windows를 기반으로 하지 않는 장치에 대해 Lync Server 2013에서 QoS를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="e9d6e-103">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9d6e-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e9d6e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e9d6e-105">Microsoft Lync Server 2013을 설치 하면 조직에서 Windows 이외의 운영 체제를 사용 하는 장치에 대해 QoS (서비스 품질)를 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-105">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="e9d6e-106">Lync Server 2013 관리 셸 내에서 다음 명령을 실행 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-106">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="e9d6e-107">미디어 구성 설정을 변경 하지 않은 경우 다음과 같은 정보가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-107">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="e9d6e-108">EnableQoS 속성이 False (앞의 출력)로 설정 되어 있으면 Windows 이외의 운영 체제를 사용 하는 컴퓨터 및 장치에 대해 서비스 품질을 사용할 수 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-108">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="e9d6e-109">QoS는 Lync Phone Edition 장치에 기본적으로 사용 하도록 설정 되어 있습니다. 그러나 Lync Phone Edition에 대 한 서비스 품질을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-109">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="e9d6e-110">전역 범위에서 서비스 품질을 사용 하도록 설정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-110">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="e9d6e-111">위 명령은 전역 범위에서 QoS를 사용 하도록 설정 합니다. 그러나 미디어 구성 설정은 사이트 범위에도 적용할 수 있다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-111">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="e9d6e-112">사이트에 대 한 서비스 품질을 사용 하도록 설정 해야 하는 경우에는 Get-csmediaconfiguration를 호출할 때 구성 설정 Id를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-112">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="e9d6e-113">예를 들어이 명령은 Redmond 사이트에 대해 QoS를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-113">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="e9d6e-114">사이트 범위에서 QoS를 사용 하도록 설정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e9d6e-114">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="e9d6e-115">사정에 따라 달라요.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-115">That depends.</span></span> <span data-ttu-id="e9d6e-116">사이트 범위에 할당 된 설정은 전역 범위에 할당 된 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-116">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="e9d6e-117">QoS가 전역 범위에서 사용 하도록 설정 되어 있지만 사이트 범위에서 사용 하지 않도록 설정 되어 있다고 가정해 보겠습니다 (Redmond 사이트의 경우). 이 경우 Redmond 사이트에 대 한 서비스 품질은 사용 하지 않도록 설정 됩니다. 이는 사이트 설정이 우선적으로 적용 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-117">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="e9d6e-118">Redmond 사이트에 대해 QoS를 사용 하도록 설정 하려면 해당 사이트에 적용 된 미디어 구성 설정을 사용 하 여이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-118">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="e9d6e-119">범위에 관계 없이 모든 미디어 구성 설정에 대해 동시에 QoS를 사용 하도록 설정 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-119">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="e9d6e-120">EnableQoS 속성 값을 False로 설정 하 여 Windows 이외의 운영 체제를 사용 하는 장치에 대해 QoS를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-120">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="e9d6e-121">예제:</span><span class="sxs-lookup"><span data-stu-id="e9d6e-121">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="e9d6e-122">이렇게 하면 네트워크의 일부 부분에서 QoS를 구현할 수 있습니다 (예: Redmond 사이트에서), 네트워크의 다른 부분에서는 서비스 품질을 사용 하지 않도록 설정 된 상태로 유지 하는 기능이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-122">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="e9d6e-123">QoS는 Windows PowerShell을 사용 하 여 사용 하거나 사용 하지 않도록 설정할 수 있습니다 .이 옵션은 Lync Server 제어판에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9d6e-123">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

