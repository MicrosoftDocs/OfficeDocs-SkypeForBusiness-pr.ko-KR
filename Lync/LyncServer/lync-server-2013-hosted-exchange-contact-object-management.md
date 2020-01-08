---
title: 'Lync Server 2013: 호스팅된 Exchange 연락처 개체 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c67438745ee7cbb9de0ccfdef1d5d8959bb4679c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="7c03d-102">Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리</span><span class="sxs-lookup"><span data-stu-id="7c03d-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c03d-103">_**마지막으로 수정한 주제:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="7c03d-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="7c03d-104">교차 프레미스 배포에서 각 자동 전화 교환 번호와 구독자 액세스 번호에 대해 Contact 개체를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="7c03d-105">호스팅된 Exchange UM과 통합 하려면 연락처 개체를 관리 하는 데 Active Directory Exchange UM 설정에 종속 되어 있기 때문에 ocsumutil을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="7c03d-106">교차 프레미스 배포의 경우 Lync Server 2013 및 호스트 된 Exchange UM을 별도의 포리스트에 설치 하 고 그 사이에 신뢰 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="7c03d-107">보안상의 이유로 Lync Server 2013 관리자는 Exchange UM Active Directory 설정에 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="7c03d-108">결과적으로 Lync Server 2013는 Lync Server 2013 및 호스팅된 Exchange UM 서비스에 모두 액세스할 수 있는 *공유 SIP 주소 공간* 에서 연락처 개체를 관리 하는 다양 한 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="7c03d-109">호스팅된 연락처 개체 워크플로</span><span class="sxs-lookup"><span data-stu-id="7c03d-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="7c03d-110">다음은 호스팅된 Exchange 테 넌 트 관리자를 사용 하 여 연락처 개체를 관리 하는 일반적인 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="7c03d-111">Exchange 관리자는 Exchange UM 구독자 액세스 및 자동 전화 교환 연락처 개체에 대 한 전화 번호를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="7c03d-112">Lync Server 2013 관리자는 각 전화 번호에 대 한 연락처 개체를 만들고 각 연락처 개체에 대해 호스팅되는 음성 메일 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="7c03d-113">Lync Server 2013 관리자는 전화 번호를 Exchange 관리자에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="7c03d-114">Exchange 관리자는 자동 전화 교환 및 구독자 액세스를 위한 적절 한 Exchange UM 다이얼 플랜에 전화 번호를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c03d-115">온-프레미스 배포를 사용 하는 경우에는 연락처 개체에 Lync Server 2013 다이얼 플랜 설정을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="7c03d-116">호스팅된 연락처 개체 구성</span><span class="sxs-lookup"><span data-stu-id="7c03d-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7c03d-117">Lync Server 2013 Contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정 하기 전에 먼저 호스트 된 음성 메일 정책을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="7c03d-118">사용 하려는 연락처 개체에 적용 되는 한 정책은 전역, 사이트 수준 또는 사용자 단위 범위로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="7c03d-119">자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013의 호스팅된 음성 메일 정책을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c03d-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7c03d-120">교차 프레미스 배포에서 호스트 된 자동 전화 교환 및 구독자 액세스 연락처 개체를 구성 하려면 다음 cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="7c03d-121">**새-c간 Umcontact** 는 호스팅된 UM에 대 한 새 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="7c03d-122">**Set-c고 Umcontact** 는 호스팅된 Exchange UM에 대 한 기존 contact 개체를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="7c03d-123">다음 예에서는 자동 전화 교환 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="7c03d-124">이 예제에서는 SIP 주소 sip:exumaa1@fabrikam.com를 사용 하 여 새 Exchange UM Contact 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="7c03d-125">Lync Server 2013 등록자 서비스가 실행 되는 풀의 이름이 RedmondPool.litwareinc.com입니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="7c03d-126">이 정보가 저장 되는 Active Directory 조직 구성 단위는 OU = ExUmContacts, DC = litwareinc, DC = com입니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="7c03d-127">연락처 개체의 전화 번호는 2065554567입니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="7c03d-128">선택적-자동 전화 교환 $True 매개 변수는이 개체가 자동 수행자 연락처 개체 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="7c03d-129">-자동 전화 교환 매개 변수를 False (기본값)로 설정 하면 구독자 액세스 연락처 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c03d-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="7c03d-130">새-CsExUmContact 및 Set-CsExUmContact cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7c03d-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

