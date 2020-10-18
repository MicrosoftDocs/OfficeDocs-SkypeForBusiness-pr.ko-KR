---
title: A/V에 지 서버 구성 설정 모음 만들기 또는 수정
description: A/V에 지 서버 구성 설정 모음을 만들거나 수정 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cdf7dca19446f4eac584564eed776f7fde47bfe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578344"
---
# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d733c-103">Lync Server 2013에서 A/V에 지 서버 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d733c-103">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d733c-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d733c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d733c-p101">A/V 에지 서비스는 내부 사용자(조직 단위 네트워크에 로그온된 사용자)가 외부 사용자(조직 단위 네트워크에 로그온되지 않은 사용자)와 오디오 및 비디오를 공유할 수 있는 방법을 제공합니다. A/V 에지 서비스는 주로 사이트 범위 또는 서비스 범위에서 구성할 수 있는(즉, 개별 A/V 에지 서버에 대해 구성할 수 있는) 설정인 A/V 에지 구성 설정을 사용해서 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-p101">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network). The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="d733c-107">Lync Server를 설치 하면 A/V에 지 구성 설정의 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-107">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="d733c-108">또한 Windows PowerShell 및 New-CsAVEdgeConfiguration cmdlet을 사용 하 여 사이트 범위 또는 서비스 범위 (즉, 개별 A/V에 지 서버에 대 한)에 새 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-108">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="d733c-109">새 설정을 만들 때는 다음을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-109">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="d733c-110">서비스 범위로(즉, 개별 서버에서) 구성된 설정은 다른 모든 것들보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-110">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="d733c-111">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-111">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="d733c-112">그러나 서비스 범위 설정도 사이트 범위 설정으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-112">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="d733c-113">전역 범위의 설정은 개별 서버에 구성된 서비스 설정이 없는 경우 그리고 서버가 배치된 위치에 사이트 설정이 없는 경우에만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-113">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="d733c-114">그런 후 Set-CsAVEdgeConfiguration cmdlet을 사용하여 모든 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-114">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d733c-115">자세한 내용은 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) 및 [get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d733c-115">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="d733c-116">사이트 범위에서 새 A/V에 지 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d733c-116">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="d733c-117">다음 명령은 Redmond 사이트에 대해 새로운 A/V 에지 구성 설정의 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-117">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="d733c-118">사이트 범위에서 사용자 지정 A/V에 지 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d733c-118">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="d733c-p105">추가 매개 변수가 포함되지 않았기 때문에 이러한 새 설정에는 A/V 에지 서비스에 대한 기본 값이 사용됩니다. 또는 추가 매개 변수 및 매개 변수 값을 추가하여 사용자 지정 컬렉션을 만들 수 있습니다. 예를 들어 이 명령은 MaxTokenLifetime 속성을 4시간으로 설정합니다(04시간 : 00분 : 00초).</span><span class="sxs-lookup"><span data-stu-id="d733c-p105">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service. Alternatively, you can add additional parameters and parameter values to create a custom collection. For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="d733c-122">서비스 범위에서 사용자 지정 A/V에 지 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d733c-122">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="d733c-123">이 명령은 A/V 에지 서버 atl-edge-001.litwareinc.com에 적용되는 비슷한 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-123">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="d733c-124">기존 A/V에 지 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="d733c-124">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="d733c-125">이 예에서 Set-CsAVEdgeConfiguration cmdlet은 Redmond 사이트의 최대 토큰 수명을 12시간으로 변경하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d733c-125">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d733c-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d733c-126">See Also</span></span>


[<span data-ttu-id="d733c-127">Lync Server 2013에서 A/V에 지 서버 구성 정보 반환</span><span class="sxs-lookup"><span data-stu-id="d733c-127">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="d733c-128">Lync Server 2013에서 A/V에 지 서버 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="d733c-128">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="d733c-129">Lync Server 2013의 A/V (오디오/비디오)에 지 서버</span><span class="sxs-lookup"><span data-stu-id="d733c-129">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="d733c-130">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d733c-130">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="d733c-131">[Get-csavedgeconfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="d733c-131">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

