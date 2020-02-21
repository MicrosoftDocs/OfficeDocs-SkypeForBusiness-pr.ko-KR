---
title: 중앙 로깅 서비스 구성 설정 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7811c8c55a7c759076382ecf102868cc6c7abf09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="96a34-102">Lync Server 2013에서 중앙 로깅 서비스 구성 설정 관리</span><span class="sxs-lookup"><span data-stu-id="96a34-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96a34-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="96a34-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="96a34-104">중앙 로깅 서비스는 CLSController (중앙화 된 로깅 서비스 컨트롤러)에서 만들고 사용 하 여 개별 컴퓨터의 중앙 로깅 서비스 에이전트에 명령을 전송 하는 설정 및 매개 변수를 통해 제어 및 구성 됩니다 ( CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="96a34-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="96a34-105">에이전트는 여기에 전송 되는 명령, 즉 시작 명령의 경우에는 제공 된 구성 정보에 따라 추적 로그 수집을 시작 하기 위한 시나리오, 공급자, 로그 크기, 추적 기간 및 플래그 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a34-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="96a34-106">중앙 로깅 서비스에 대해 나열 된 모든 Windows PowerShell cmdlet은 Lync Server 2013 온-프레미스 배포에 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="96a34-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="96a34-107">다음과 같은 cmdlet은 작동 하는 것 처럼 보일 수 있지만 Lync Server 2013 온-프레미스 배포에서는 작동 하도록 설계 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="96a34-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="96a34-108"><STRONG>CsClsRegion cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A> 및 <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span><span class="sxs-lookup"><span data-stu-id="96a34-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="96a34-109"><STRONG>CsClsSearchTerm cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> 및 <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span><span class="sxs-lookup"><span data-stu-id="96a34-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="96a34-110"><STRONG>CsClsSecurityGroup cmdlet:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A> 및 <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span><span class="sxs-lookup"><span data-stu-id="96a34-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="96a34-111">이러한 cmdlet에 정의 된 설정은 방해 하거나 부정적인 동작이 발생 하지 않지만, 이러한 기능은 Microsoft Office 365에서 사용 하도록 디자인 되었으며, 온-프레미스 배포에서 예상 결과를 얻지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="96a34-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="96a34-112">이 말이 온-프레미스 배포에서 이러한 cmdlet을 사용할 수 없음을 의미하는 것은 아니지만 이 설명서에서는 이러한 cmdlet의 용도에 대해 설명하지 않겠습니다.</span><span class="sxs-lookup"><span data-stu-id="96a34-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="96a34-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="96a34-113">In This Section</span></span>

<span data-ttu-id="96a34-114">이 섹션의 항목에서는 중앙 로깅 서비스에 대 한 구성 옵션, 매개 변수 및 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="96a34-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="96a34-115">중앙 로깅 서비스를 구성 하는 방법, 구성 설정을 검색 하는 방법, 시나리오를 만드는 방법, 중앙화 된 로깅 서비스에 대 한 보안 그룹 관리, 검색 등에 대 한 자세한 내용은 다음 항목에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96a34-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="96a34-116">Lync Server 2013에서 컴퓨터, 사이트 및 전역 중앙화 된 로깅 서비스 구성 관리</span><span class="sxs-lookup"><span data-stu-id="96a34-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="96a34-117">Lync Server 2013에서 중앙 로깅 서비스에 대 한 공급자 구성</span><span class="sxs-lookup"><span data-stu-id="96a34-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="96a34-118">Lync Server 2013에서 중앙 로깅 서비스에 대 한 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="96a34-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96a34-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96a34-119">See Also</span></span>


[<span data-ttu-id="96a34-120">Lync Server 2013의 중앙 로깅 서비스 개요</span><span class="sxs-lookup"><span data-stu-id="96a34-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="96a34-121">Lync Server 2013의 중앙 로깅 cmdlet</span><span class="sxs-lookup"><span data-stu-id="96a34-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

