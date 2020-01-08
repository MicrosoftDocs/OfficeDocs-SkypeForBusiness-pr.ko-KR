---
title: 'Lync Server 2013: 호스팅된 Exchange UM에 대한 대화 상대 개체 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d5bdfe3b341f534a3e8066fe85be5e93b0a7f7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40985762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="596ea-102">Lync Server 2013에서 호스팅된 Exchange UM에 대한 대화 상대 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="596ea-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="596ea-103">_**마지막으로 수정한 주제:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="596ea-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="596ea-104">다음 절차에서는 호스팅된 Exchange UM (통합 메시징)에 대 한 자동 전화 교환 (AA) 또는 SA (구독자 액세스) 연락처 개체를 만드는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="596ea-105">자세한 내용은 계획 설명서의 [Lync Server 2013에서 호스팅된 Exchange 연락처 개체 관리](lync-server-2013-hosted-exchange-contact-object-management.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="596ea-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="596ea-106">연락처 개체를 구성 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="596ea-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="596ea-107">신규-C또는 Um연락처</span><span class="sxs-lookup"><span data-stu-id="596ea-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="596ea-108">Set-C간 Umcontact</span><span class="sxs-lookup"><span data-stu-id="596ea-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="596ea-109">Lync Server 2013 contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정 하기 전에 먼저 호스트 된 음성 메일 정책을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="596ea-110">자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013의 호스팅된 음성 메일 정책을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="596ea-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="596ea-111">호스팅된 Exchange UM에 대 한 AA 또는 SA 연락처 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="596ea-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="596ea-112">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="596ea-113">새-CsExUmContact cmdlet을 실행 하 여 배포에 필요한 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="596ea-114">예를 들어 AA 및 SA contact 개체를 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="596ea-115">이러한 예제에서는 다음 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="596ea-116">**SipAddress** 는 연락처 개체의 SIP 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="596ea-117">Active Directory 도메인 서비스에서 사용자 또는 연락처 개체를 구성 하는 데 아직 사용 되지 않은 주소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="596ea-118">이 값은 앞의 예제에 표시 된 대로\<"sip:*sip 주소*\>" 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="596ea-119">**RegistrarPool** 는 등록자 서비스가 실행 되는 풀의 FQDN (정규화 된 도메인 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="596ea-120">Exchange UM 연락처 개체는 Lync server 2013 이전의 Lync Server 2013 배포에 포함 된 풀로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="596ea-121">**OU** 이 연락처 개체를 배치할 Active Directory 조직 구성 단위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="596ea-122">**Displaynumber** 연락처 개체의 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="596ea-123">각 연락처 개체의 전화 번호는 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="596ea-124">자동 **전화 교환** 연락처 개체가 자동 전화 교환 인지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="596ea-125">자동 전화 교환은 발신자가 전화 시스템을 탐색 하 고 연락 하려는 상대방에 게 연락할 수 있는 음성 프롬프트 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="596ea-126">이 매개 변수의 값이 **False** (기본값) 인 경우 구독자 액세스 연락처 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="596ea-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

