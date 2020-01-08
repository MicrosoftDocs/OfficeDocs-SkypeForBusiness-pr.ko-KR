---
title: 'Lync Server 2013: A/V Edge 서버 구성 정보 반환'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15096099184525890328dbe1c89d891487b46d87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="55367-102">Lync Server 2013에서 A/V Edge 서버 구성 정보 반환</span><span class="sxs-lookup"><span data-stu-id="55367-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55367-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="55367-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="55367-104">A/V Edge 서비스는 내부 사용자 (조직의 네트워크에 로그온 한 사용자)가 외부 사용자 (조직의 네트워크에 로그인 하지 않은 사용자)와 오디오 및 비디오를 공유 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="55367-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="55367-105">A/V Edge 서비스는 사이트 범위 또는 서비스 범위 (개별 A/V Edge 서버에 대해 구성할 수 있음)에서 구성할 수 있는 설정인 A/V Edge 구성 설정을 사용 하 여 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55367-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="55367-106">조직에서 사용 중인 A/V Edge 구성 설정에 대 한 정보를 반환 하려면 Windows PowerShell 및 CsAVEdgeConfiguration cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55367-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="55367-107">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55367-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="55367-108">CsAVEdgeConfiguration cmdlet에서 반환 되는 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55367-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="55367-109">모든 A/V Edge 구성 설정에 대 한 정보를 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="55367-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="55367-110">다음 명령은 조직에서 현재 사용 중인 모든 A/V Edge 구성 설정에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55367-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="55367-111">사이트 범위 A/V Edge 구성 설정에 대 한 정보를 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="55367-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="55367-112">A/V Edge 구성 설정의 특정 컬렉션에 대 한 정보를 반환 하려면 CsAVEdgeConfiguration cmdlet을 실행할 때 해당 컬렉션의 Id를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55367-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="55367-113">예를 들어이 명령은 Redmond 사이트에 적용 된 설정에 대 한 정보만 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55367-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="55367-114">서비스 범위 A/V Edge 구성 설정에 대 한 정보를 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="55367-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="55367-115">이 명령은 특정 A/V Edge 서버를 적용 한 설정에 대해서만 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="55367-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55367-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55367-116">See Also</span></span>


[<span data-ttu-id="55367-117">Lync Server 2013에서 A/V Edge 서버 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="55367-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="55367-118">Lync Server 2013에서 A/V Edge 서버 구성 설정의 기존 컬렉션 삭제</span><span class="sxs-lookup"><span data-stu-id="55367-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="55367-119">Lync Server 2013의 오디오/비디오 (A/V) Edge 서버</span><span class="sxs-lookup"><span data-stu-id="55367-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

