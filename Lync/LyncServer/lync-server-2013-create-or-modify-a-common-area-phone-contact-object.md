---
title: 'Lync Server 2013: 공통 영역 전화 연락처 개체 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1345477178d7991083332e809de3f764be4c3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="6a1a8-102">Lync Server 2013에서 공통 영역 전화 연락처 개체 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="6a1a8-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a1a8-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="6a1a8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="6a1a8-104">모든 공통 영역 전화기에 대 한 Active Directory 도메인 서비스 연락처 개체를 만들려면 **CsCommonAreaPhone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="6a1a8-105">이 cmdlet은 공통 영역 전화기와 함께 사용할 새 연락처 개체를 만들거나 기존 연락처 개체를 새 공통 영역 휴대폰에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="6a1a8-106">일반 지역 전화와 연결 된 contact 개체의 속성을 수정 하려면 **CsCommonAreaPhone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="6a1a8-107">**CsCommonAreaPhone** 에 대 한 선택적 매개 변수를 사용 하면 연락처의 Active Directory 표시 이름 또는 휴대폰과 연결 된 줄의 URI (Uniform resource identifier)와 같은 항목을 변경 하 고 Lync Server에서 계정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="6a1a8-108">사용 가능한 모든 수정 사항에 대 한 자세한 내용은 [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)의 Parameters 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="6a1a8-109">**CsCommonAreaPhone** 매개 변수에 대 한 자세한 내용은 [new-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="6a1a8-110">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 두 개의 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a1a8-111">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="6a1a8-112">공통 영역 전화 연락처 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="6a1a8-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="6a1a8-113">새 공통 영역 휴대폰 연락처 개체를 만들려면 **CsCommonAreaPhone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="6a1a8-114">최소한 연락처 개체를 만들 때는 다음 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="6a1a8-115">**Lineuri**: 일반 지역 전화에 할당 된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="6a1a8-116">전화 번호를 지정할 때에는 E 164 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="6a1a8-117">**RegistrarPool**: 연락처 개체를 호스팅할 레지스트라 풀의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="6a1a8-118">**OU**: 연락처 개체가 생성 되는 Active Directory 컨테이너의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="6a1a8-119">또한 Active Directory 도메인 서비스 표시 이름을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="6a1a8-120">그렇지 않은 경우에는 GUID를 사용 하 여 전화 Id를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="6a1a8-121">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="6a1a8-122">일반 지역 전화 연락처 개체 수정</span><span class="sxs-lookup"><span data-stu-id="6a1a8-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="6a1a8-123">기존 공통 영역 휴대폰의 속성을 수정 하려면 contact 개체에서 **CsCommonAreaPhone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="6a1a8-124">예를 들어이 명령은 DisplayName 대기실를 사용 하 여 일반적인 지역 전화에 대 한 SIP 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="6a1a8-125">자세한 내용은 [새 CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 및 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) Cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a1a8-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

