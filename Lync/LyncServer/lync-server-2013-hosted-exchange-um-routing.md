---
title: 'Lync Server 2013: 호스팅된 Exchange UM 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90cc1112effd0eac0a25614ee50d7008ee1c5e37
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="f6c6d-102">Lync Server 2013의 호스팅된 Exchange UM 라우팅</span><span class="sxs-lookup"><span data-stu-id="f6c6d-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6c6d-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f6c6d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f6c6d-104">Exchange UM 라우팅 응용 프로그램은 프런트 엔드 서버에서 실행 되어 온-프레미스 Microsoft Exchange Server UM (통합 메시징) 배포 또는 호스팅된 Exchange UM 서비스에 호출을 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="f6c6d-105">ExUM 라우팅 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="f6c6d-105">The ExUM Routing Application</span></span>

<span data-ttu-id="f6c6d-106">Lync Server 2013 Exchange UM 라우팅 응용 프로그램은 사용자 계정 설정 및 호스팅된 음성 메일 정책 매개 변수의 정보를 사용 하 여 다음 다이어그램과 같이 호스팅된 음성 메시지의 호출을 라우팅하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="f6c6d-107">**Exchange UM 라우팅의 혼합 배포 예제**</span><span class="sxs-lookup"><span data-stu-id="f6c6d-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="f6c6d-108">온-프레미스 lync ![Server exchange um 배포](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "온-프레미스 LYNC server exchange um 배포")</span><span class="sxs-lookup"><span data-stu-id="f6c6d-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="f6c6d-109">온-프레미스 Exchange UM에 대해 사용 하도록 설정 된 사용자, 호스트 된 Exchange UM에 대해 사용 하도록 설정 된 사용자 또는 둘의 조합에 대 한 통화를 라우팅하도록 Exchange UM 라우팅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="f6c6d-110">예를 들어 Roy의 사서함 및 Exchange UM 서비스가 온-프레미스 Exchange 배포에 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="f6c6d-111">Roy의 사용자 계정에 있는 프록시 주소 정보는 ExUM Routing application이 온-프레미스 Exchange UM 서버로의 호출을 라우팅하는 데 사용 하는 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="f6c6d-112">Alice의 사서함과 Exchange UM 서비스는 호스팅된 Exchange 서비스 공급자의 데이터 센터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="f6c6d-113">Exchange UM 통화에 대 한 라우팅은 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="f6c6d-114">Alice의 사용자 계정에 있는 msExchUCVoiceMailSettings 특성에 설정 된 값은 호스팅된 음성 메일 정책에서 라우팅 세부 정보를 확인 하도록 ExUM 라우팅 응용 프로그램에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6c6d-115">MsExchUCVoiceMailSettings 특성 값은 Exchange 서비스 공급자 또는 Lync Server 2013 관리자가 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="f6c6d-116">앞의 다이어그램에 표시 된 예제에서 Lync Server 2013 관리자가 Alice에 대해 호스팅된 음성 메일을 사용 하도록 설정 하 여 값 (CsHostedVoiceMail 메일 = 1)을 설정한 경우</span><span class="sxs-lookup"><span data-stu-id="f6c6d-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="f6c6d-117">이 특성에 대 한 자세한 내용은 <A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013에서 호스트 된 Exchange 사용자 관리</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="f6c6d-118">Alice의 사용자 계정에 할당 된 호스트 된 음성 메일 정책은 라우팅 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="f6c6d-119">대상은 호스트 된 Exchange UM 서비스 공급자 (1!)입니다. ExUm. \<이\>예제에서는 hostedExchangeServer.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="f6c6d-120">조직에는 ls에 있는 Exchange Server 테 넌 트에 대 한 SIP 메시지의 라우팅 Fqdn 인 테 넌 트 Id가 식별 됩니다. ExUm. \<hostedExchangeServer\>(이 예에서는 corp.contoso.com 및 corp.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="f6c6d-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f6c6d-121">Exchange Online에 대 한 FQDN은 exap.um.outlook.com입니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="f6c6d-122">자세한 내용은 [Lync Server 2013의 호스팅된 음성 메일 정책을](lync-server-2013-hosted-voice-mail-policies.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f6c6d-123">사용자 계정에 msExchUCVoiceMailSettings 특성 및 UM 프록시 주소 설정이 둘 다 있는 경우 msExchUCVoiceMailSettings 특성이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f6c6d-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

