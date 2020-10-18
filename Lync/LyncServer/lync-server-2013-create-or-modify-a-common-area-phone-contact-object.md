---
title: 'Lync Server 2013: 공통 영역 전화 연락처 개체 만들기 또는 수정'
description: 'Lync Server 2013: 공통 영역 전화 연락처 개체를 만들거나 수정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc5ede23f495a63b2d556b556817d4171a08723
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578234"
---
# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="1c0df-103">Lync Server 2013에서 공통 영역 전화 연락처 개체 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="1c0df-103">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c0df-104">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="1c0df-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="1c0df-105">모든 공통 영역 전화에 대 한 Active Directory 도메인 서비스 대화 상대 개체를 만들려면 **move-cscommonareaphone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-105">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="1c0df-106">이 cmdlet은 공통 영역 전화와 함께 사용할 새 대화 상대 개체를 만들거나 기존 연락처 개체를 새 공통 영역 전화와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-106">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="1c0df-107">공통 영역 전화와 연결 된 대화 상대 개체의 속성을 수정 하려면 **move-cscommonareaphone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-107">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="1c0df-108">**Move-cscommonareaphone** 의 선택적 매개 변수를 사용 하면 연락처의 Active Directory 표시 이름 또는 전화선과 연결 된 줄 URI (Uniform resource Identifier)와 같은 항목을 변경할 수 있으며 Lync Server에서 사용할 수 있도록 계정을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-108">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="1c0df-109">사용 가능한 모든 수정 사항에 대 한 자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)의 Parameters 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c0df-109">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="1c0df-110">**Move-cscommonareaphone** 매개 변수에 대 한 자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c0df-110">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="1c0df-111">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 이러한 두 가지 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-111">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1c0df-112">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c0df-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="1c0df-113">공통 영역 전화 연락처 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="1c0df-113">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="1c0df-114">새 공통 영역 전화 연락처 개체를 만들려면 **move-cscommonareaphone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-114">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="1c0df-115">연락처 개체를 만들 때는 최소한 다음 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-115">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="1c0df-116">**Lineuri**: 공통 영역 전화에 할당 된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-116">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="1c0df-117">전화 번호를 지정할 때는 E. 164 형식을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-117">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="1c0df-118">**RegistrarPool**: 연락처 개체를 호스팅할 등록자 풀의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-118">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="1c0df-119">**OU**: 연락처 개체를 만들 Active Directory 컨테이너의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-119">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="1c0df-120">또한 Active Directory 도메인 서비스 표시 이름을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-120">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="1c0df-121">그렇지 않은 경우에는 GUID를 사용 하 여 전화 Id를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-121">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="1c0df-122">예제:</span><span class="sxs-lookup"><span data-stu-id="1c0df-122">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="1c0df-123">공통 영역 전화 연락처 개체 수정</span><span class="sxs-lookup"><span data-stu-id="1c0df-123">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="1c0df-124">기존 공통 영역 전화의 속성을 수정 하려면 contact 개체는 **move-cscommonareaphone** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-124">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="1c0df-125">예를 들어 다음 명령은 DisplayName 로비를 사용 하 여 공통 영역 전화에 대 한 SIP 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0df-125">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="1c0df-126">자세한 내용은 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 및 [move-cscommonareaphone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) Cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c0df-126">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

