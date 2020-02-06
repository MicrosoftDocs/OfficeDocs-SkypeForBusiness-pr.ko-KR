---
title: Windows 기반 장치가 아닌 장치의 QoS를 사용 하도록 설정
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Windows 이외의 운영 체제를 사용 하는 조직에서 사용 되는 디바이스에 대해 QoS를 사용 하도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 74f964f6156c8b2f2d7a7359193b5dbffe95a011
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817417"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="cc639-103">비즈니스용 Skype 서버에서 QoS를 사용 하도록 설정 하는 경우 Windows를 기반으로 하지 않는 장치</span><span class="sxs-lookup"><span data-stu-id="cc639-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="cc639-104">비즈니스용 Skype Server를 설치 하는 경우 Windows 이외의 운영 체제를 사용 하는 조직에서 사용 하는 디바이스에 대해 QoS (서비스 품질)를 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="cc639-105">비즈니스용 Skype ServerManagement Shell 내에서 다음 명령을 실행 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="cc639-106">미디어 구성 설정을 변경 하지 않은 경우 다음과 같은 정보가 다시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="cc639-107">앞의 출력과 같이 EnableQoS 속성을 False로 설정 하면 Windows 이외의 운영 체제를 사용 하는 컴퓨터 및 장치에 대해 서비스 품질을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="cc639-108">전역 범위에서 서비스 품질을 사용 하도록 설정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="cc639-109">앞의 명령을 사용 하면 전역 범위에서 QoS를 사용할 수 있습니다. 그러나 미디어 구성 설정이 사이트 범위에도 적용 될 수 있다는 것을 기억해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="cc639-110">사이트의 서비스 품질을 사용 해야 하는 경우 Set-CsMediaConfiguration를 호출할 때 구성 설정의 Id를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="cc639-111">예를 들어이 명령은 Redmond 사이트에 대해 QoS를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="cc639-112">사이트 범위에서 QoS를 사용 하도록 설정 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="cc639-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="cc639-113">사정에 따라 달라요.</span><span class="sxs-lookup"><span data-stu-id="cc639-113">That depends.</span></span> <span data-ttu-id="cc639-114">사이트 범위에 할당 된 설정은 전역 범위에 할당 된 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="cc639-115">전역 범위에서 QoS를 사용 하도록 설정 했지만 사이트 범위 (Redmond 사이트의 경우)에서 사용할 수 없는 경우를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="cc639-116">이 경우 Redmond 사이트에 대 한 서비스 품질을 사용할 수 없습니다. 사이트 설정이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="cc639-117">Redmond 사이트에 대해 QoS를 사용 하도록 설정 하려면 해당 사이트에 적용 된 미디어 구성 설정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="cc639-118">범위에 관계 없이 모든 미디어 구성 설정에 대해 동시에 QoS를 사용 하도록 설정 하려면 LSkype for Business 서버 관리 셸에서이 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="cc639-119">EnableQoS 속성 값을 False로 설정 하 여 Windows 이외의 운영 체제를 사용 하는 디바이스에 대해 QoS를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="cc639-120">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="cc639-121">이렇게 하면 네트워크의 다른 부분에서 서비스 품질을 사용 하지 않도록 설정 하는 동안 네트워크의 일부 부분 (예: Redmond 사이트)에 QoS를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="cc639-122">QoS는 Windows PowerShell을 사용 하 여 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="cc639-123">이 옵션은 비즈니스용 Skype Server 제어판에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="cc639-124">IOS 버전 6.17 이상 용 비즈니스용 Skype 클라이언트는 이제 QoS를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="cc639-125">이 QoS 접근 권한 값은 비즈니스용 Skype 클라이언트와 관리 네트워크의 Lync 풀 서버에 직접 등록 된 IP 전화 장치에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="cc639-126">QoS는 인터넷 상에 서 라우팅된 트래픽에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc639-126">QoS is not applicable for traffic routed over the Internet.</span></span>



