---
title: 'Lync Server 2013: 호스팅된 Exchange 연락처 개체 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dae7088982fd3f28ead762c6f50ed4543a5cdef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528195"
---
# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="91500-102">Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리</span><span class="sxs-lookup"><span data-stu-id="91500-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91500-103">_**마지막으로 수정 된 항목:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="91500-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="91500-104">교차 프레미스 배포에서 각 자동 전화 교환 번호 및 구독자 액세스 번호에 대해 대화 상대 개체를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="91500-105">호스팅된 Exchange UM과의 통합 시 Active Directory Exchange UM 설정에 따라 달라지므로 ocsumutil.exe를 사용하여 연락처 개체를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91500-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="91500-106">크로스-프레미스 배포에서 Lync Server 2013와 호스트 된 Exchange UM은 별도의 포리스트에 따로 트러스트 없이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91500-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="91500-107">보안상의 이유로 Lync Server 2013 관리자는 Exchange UM Active Directory 설정에 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91500-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="91500-108">따라서 Lync Server 2013에서는 Lync Server 2013 및 호스팅된 Exchange UM 서비스 모두에 액세스할 수 있는 *공유 SIP 주소 공간* 에서 연락처 개체를 관리 하기 위한 다양 한 모델을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="91500-109">호스팅된 대화 상대 개체 워크플로</span><span class="sxs-lookup"><span data-stu-id="91500-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="91500-110">다음은 대화 상대 개체를 관리하기 위해 호스팅된 Exchange 테넌트 관리자가 수행하는 일반적인 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="91500-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="91500-111">Exchange 관리자가 Exchange UM 구독자 액세스 및 자동 전화 교환 대화 상대 개체에 대한 전화 번호를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="91500-112">Lync Server 2013 관리자가 각 전화 번호에 대 한 연락처 개체를 만들고 각 대화 상대 개체에 대해 호스팅된 음성 메일 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="91500-113">Lync Server 2013 관리자는 Exchange 관리자에 게 전화 번호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="91500-114">Exchange 관리자가 자동 전화 교환 및 구독자 액세스에 적합한 Exchange UM 다이얼 플랜에 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91500-115">온-프레미스 배포와 마찬가지로 연락처 개체에 대해 Lync Server 2013 다이얼 플랜 설정을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91500-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="91500-116">호스팅된 대화 상대 개체 구성</span><span class="sxs-lookup"><span data-stu-id="91500-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="91500-117">Lync Server 2013 Contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정할 수 있으려면 먼저 해당 연락처에 적용 되는 호스팅된 음성 메일 정책을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="91500-118">사용하도록 설정할 연락처 개체에 적용되는 경우에는 정책 범위를 전역, 사이트 수준 또는 사용자별로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91500-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="91500-119">자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="91500-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="91500-120">교차 프레미스 배포에서 호스팅된 자동 전화 교환 및 구독자 액세스 대화 상대 개체를 구성하려면 다음 cmdlet를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="91500-121">**New-CsExUmContact** - 호스팅된 UM에 대해 새 대화 상대 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91500-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="91500-122">**Set-CsExUmContact** - 호스팅된 Exchange UM에 대해 기존의 대화 상대 개체를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="91500-123">다음은 자동 전화 교환 대화 상대 개체를 만드는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="91500-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="91500-124">이 예에서는 SIP 주소 sip:exumaa1@fabrikam.com을 사용 하 여 새 Exchange UM 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="91500-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="91500-125">Lync Server 2013 등록자 서비스가 실행 되는 풀의 이름은 RedmondPool.litwareinc.com입니다.</span><span class="sxs-lookup"><span data-stu-id="91500-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="91500-126">이 정보가 저장 되는 Active Directory 조직 구성 단위는 OU = ExUmContacts, DC = litwareinc, DC = com입니다.</span><span class="sxs-lookup"><span data-stu-id="91500-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="91500-127">연락처 개체의 전화 번호는 2065554567입니다.</span><span class="sxs-lookup"><span data-stu-id="91500-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="91500-128">Optional-attendant $True 매개 변수는이 개체가 자동 전화 교환 대화 상대 개체 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="91500-129">-자동 전화 교환 매개 변수를 False (기본값)로 설정 하면 구독자 액세스 대화 상대 개체를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91500-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="91500-130">New-CsExUmContact 및 Set-CsExUmContact cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="91500-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

