---
title: A/V Edge 서버 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of A/V Edge Server configuration settings
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49733630
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4010c209e1231c47c328d616f686f55fc89008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-av-edge-server-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="efa09-102">Lync Server 2013에서 A/V Edge 서버 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="efa09-102">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efa09-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="efa09-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="efa09-104">A/V Edge 서비스는 내부 사용자 (조직의 네트워크에 로그온 한 사용자)가 외부 사용자 (조직의 네트워크에 로그인 하지 않은 사용자)와 오디오 및 비디오를 공유 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="efa09-105">A/V Edge 서비스는 사이트 범위 또는 서비스 범위 (개별 A/V Edge 서버에 대해 구성할 수 있음)에서 구성할 수 있는 설정인 A/V Edge 구성 설정을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="efa09-106">Lync Server를 설치할 때 A/V Edge 구성 설정의 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-106">When you install Lync Server, a global collection of A/V Edge configuration settings is created for you.</span></span> <span data-ttu-id="efa09-107">이 외에도 Windows PowerShell 및 CsAVEdgeConfiguration cmdlet을 사용 하 여 사이트 범위 또는 서비스 범위 (즉, 개별 A/V Edge 서버의 경우)에 대 한 새 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-107">In addition to that, you can use the Windows PowerShell and the New-CsAVEdgeConfiguration cmdlet to create new settings at the site scope or the service scope (that is, for an individual A/V Edge server).</span></span> <span data-ttu-id="efa09-108">새 설정을 만드는 경우 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="efa09-108">If you create new settings keep in mind that:</span></span>

  - <span data-ttu-id="efa09-109">서비스 범위 (즉, 개별 서버)에 구성 된 설정은 모두에 게 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-109">Settings configured at the service scope (that is, on an individual server) take priority over everything.</span></span>

  - <span data-ttu-id="efa09-110">사이트 범위에서 구성 된 설정은 전역 범위에서 구성 된 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-110">Settings configured at the site scope take priority over settings configured at the global scope.</span></span> <span data-ttu-id="efa09-111">그러나 서비스 범위 설정 에서도 사이트 범위 설정이 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-111">However, service scope settings will also supersede site-scope settings.</span></span>

  - <span data-ttu-id="efa09-112">전역 범위의 설정은 개별 서버에 구성 된 서비스 설정이 없고 해당 서버가 있는 사이트에 대 한 사이트 설정이 없는 경우에만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-112">Settings at the global scope will be used only if there are no service settings configured on the individual server and if there are no site settings for the site where that server is located.</span></span>

<span data-ttu-id="efa09-113">그런 다음 CsAVEdgeConfiguration cmdlet을 사용 하 여 모든 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-113">Any of your settings can then be modified by using the Set-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="efa09-114">자세한 내용은 [새 CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) 및 [CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="efa09-114">For more information, see the help topics for the [New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15)) and the [Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15)) cmdlets.</span></span>

<div>

## <a name="to-create-new-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="efa09-115">사이트 범위에서 새 A/V Edge 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="efa09-115">To create new A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="efa09-116">다음 명령은 Redmond 사이트에 대 한 A/V Edge 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-116">The following command creates a new collection of A/V Edge configuration settings for the Redmond site:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-site-scope"></a><span data-ttu-id="efa09-117">사이트 범위에서 사용자 지정 A/V Edge 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="efa09-117">To create custom A/V Edge configuration settings at the site scope</span></span>

  - <span data-ttu-id="efa09-118">추가 매개 변수가 포함 되지 않았으므로 이러한 새 설정에서는 A/V Edge 서비스에 대 한 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-118">Because no additional parameters were included, these new settings will use the default values for the A/V Edge service.</span></span> <span data-ttu-id="efa09-119">또는 매개 변수 및 매개 변수 값을 더 추가 하 여 사용자 지정 컬렉션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-119">Alternatively, you can add additional parameters and parameter values to create a custom collection.</span></span> <span data-ttu-id="efa09-120">예를 들어이 명령은 MaxTokenLifetime 속성을 4 시간 (04 시간: 00 분: 00 초)으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-120">For example, this command sets the MaxTokenLifetime property to 4 hours (04 hours : 00 minutes : 00 seconds):</span></span>
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-create-custom-av-edge-configuration-settings-at-the-service-scope"></a><span data-ttu-id="efa09-121">서비스 범위에서 사용자 지정 A/V Edge 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="efa09-121">To create custom A/V Edge configuration settings at the service scope</span></span>

  - <span data-ttu-id="efa09-122">이 명령은 A/V Edge 서버 atl-edge-001.litwareinc.com에 적용 된 유사한 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-122">This command creates a similar collection applied to the A/V Edge server atl-edge-001.litwareinc.com:</span></span>
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

</div>

<div>

## <a name="to-modify-existing-av-edge-configuration-settings"></a><span data-ttu-id="efa09-123">기존 A/V Edge 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="efa09-123">To modify existing A/V Edge configuration settings</span></span>

  - <span data-ttu-id="efa09-124">이 예제에서는 집합-CsAVEdgeConfiguration cmdlet을 사용 하 여 Redmond 사이트의 최대 토큰 수명을 12 시간으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="efa09-124">In this example, the Set-CsAVEdgeConfiguration cmdlet is used to change the maximum token lifetime for the Redmond site to 12 hours:</span></span>
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efa09-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="efa09-125">See Also</span></span>


[<span data-ttu-id="efa09-126">Lync Server 2013에서 A/V Edge 서버 구성 정보 반환</span><span class="sxs-lookup"><span data-stu-id="efa09-126">Return A/V Edge Server configuration information in Lync Server 2013</span></span>](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[<span data-ttu-id="efa09-127">Lync Server 2013에서 A/V Edge 서버 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="efa09-127">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="efa09-128">Lync Server 2013의 오디오/비디오 (A/V) Edge 서버</span><span class="sxs-lookup"><span data-stu-id="efa09-128">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
<span data-ttu-id="efa09-129">[새로운 CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="efa09-129">[New-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412884(v=OCS.15))</span></span>  
<span data-ttu-id="efa09-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="efa09-130">[Set-CsAVEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg412869(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

