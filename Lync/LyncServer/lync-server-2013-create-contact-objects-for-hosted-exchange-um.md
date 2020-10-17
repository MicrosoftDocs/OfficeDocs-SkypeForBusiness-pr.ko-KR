---
title: 'Lync Server 2013: 호스팅된 Exchange UM에 대 한 연락처 개체 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 051b7f483ec3e3a59d5025c670b63b97765016b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532305"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="e4e22-102">Lync Server 2013에서 호스팅된 Exchange UM에 대 한 대화 상대 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="e4e22-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4e22-103">_**마지막으로 수정 된 항목:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="e4e22-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="e4e22-104">다음 절차는 호스팅된 Exchange UM(통합 메시징)에 대한 AA(자동 전화 교환), SA(구독자 액세스) 연락처 개체를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="e4e22-105">자세한 내용은 계획 설명서에서 [Lync Server 2013의 호스팅된 Exchange 연락처 개체 관리](lync-server-2013-hosted-exchange-contact-object-management.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4e22-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="e4e22-106">대화 상대 개체를 구성 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4e22-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="e4e22-107">새 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="e4e22-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="e4e22-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="e4e22-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="e4e22-109">Lync Server 2013 contact 개체를 호스팅된 Exchange UM에 대해 사용 하도록 설정할 수 있으려면 먼저 해당 연락처에 적용 되는 호스팅된 음성 메일 정책을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="e4e22-110">자세한 내용은 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013에서 호스팅된 음성 메일 정책</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4e22-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="e4e22-111">호스팅된 Exchange UM에 대한 AA 또는 SA 연락처 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e4e22-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="e4e22-112">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e4e22-p102">New-CsExUmContact cmdlet을 실행하여 배포에 필요한 연락처 개체를 만듭니다. 예를 들어 다음을 실행하여 AA 및 SA 연락처 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="e4e22-115">이러한 예는 다음 매개 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="e4e22-116">**Nm-server-w15-short** 은 연락처 개체의 SIP 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="e4e22-117">Active Directory 도메인 서비스에서 사용자 또는 연락처 개체를 구성 하는 데 사용 되지 않은 주소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="e4e22-118">이 값은 \<*SIP address*\> 앞의 예제에 표시 된 대로 "sip:" 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="e4e22-119">**RegistrarPool**은 등록자 서비스가 실행되고 있는 풀의 FQDN(정규화된 도메인 이름)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="e4e22-120">Exchange UM 연락처 개체는 Lync Server 2013 이전의 Lync Server 2013 배포에 속하는 풀로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="e4e22-121">**OU**는 이 연락처 개체가 위치할 Active Directory 조직 구성 단위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="e4e22-p104">**DisplayNumber**는 연락처 개체의 전화 번호를 지정합니다. 각 연락처 개체의 전화 번호는 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="e4e22-p105">**AutoAttendant**는 연락처 개체가 자동 전화 교환인지 여부를 지정합니다. 자동 전화 교환은 발신자가 전화 시스템을 탐색하여 연결할 상대방을 찾을 수 있게 하는 음성 안내 집합을 제공합니다. 이 매개 변수의 값이 **False**(기본값)일 경우 연락처 개체는 구독자 액세스 연락처 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e4e22-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

