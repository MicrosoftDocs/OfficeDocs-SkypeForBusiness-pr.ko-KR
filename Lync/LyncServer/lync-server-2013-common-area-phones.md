---
title: 'Lync Server 2013: 공통 영역 전화'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common area phones
ms:assetid: d63bb3de-154e-4347-9251-9fa94e7d593a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994076(v=OCS.15)
ms:contentKeyID: 51803987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 523238887e8ed5ac7dc45fb05177ae0c5fa9f291
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="common-area-phones-in-lync-server-2013"></a><span data-ttu-id="e411d-102">Lync Server 2013의 공통 영역 전화</span><span class="sxs-lookup"><span data-stu-id="e411d-102">Common area phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e411d-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e411d-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e411d-104">공통 영역 전화는 개별 사용자와 연결 되지 않은 IP 전화입니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-104">Common area phones are IP phones that are not associated with an individual user.</span></span> <span data-ttu-id="e411d-105">일반적인 지역 전화는 다른 사람의 사무실에 위치 하는 대신, 로비, cafeterias, 직원 lounges, 회의실 및 다 수의 사용자가 수집할 수 있는 기타 위치를 구축 하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-105">Instead of being located in someone’s office, common area phones are typically located in building lobbies, cafeterias, employee lounges, meeting rooms, and other locations where a large number of people are likely to gather.</span></span> <span data-ttu-id="e411d-106">일반적으로 개별 사용자에 게 할당 되는 음성 정책 및 다이얼 플랜을 사용 하 여 유지 관리 되는 Lync Server의 다른 전화와 달리, 공통 영역 전화에는 개별 사용자가 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-106">Unlike other phones in Lync Server, which are typically maintained by using voice policies and dial plans that are assigned to individual users, common area phones do not have individual users assigned to them.</span></span> <span data-ttu-id="e411d-107">즉, 다른 전화기와는 다르게 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-107">This means that they must be managed differently than your other phones.</span></span>

<span data-ttu-id="e411d-108">공통 영역 전화를 관리 하려면 사용자 계정과 마찬가지로 정책 및 음성 요금제를 할당할 수 있는 모든 공통 영역 전화에 대 한 Active Directory 도메인 서비스 대화 상대 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-108">To manage common area phones, you create Active Directory Domain Services contact objects for all your common area phones that, like user accounts, can be assigned policies and voice plans.</span></span> <span data-ttu-id="e411d-109">이 방법을 사용 하면 전화가 개별 사용자와 연결 되어 있지 않더라도 공통 영역 전화에 대 한 제어를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-109">This approach enables you to maintain control over common area phones, even though those phones are not associated with an individual user.</span></span>

<span data-ttu-id="e411d-110">이 섹션의 항목을 사용 하 여 공통 영역 전화에 대 한 연락처 개체를 만들고, 수정 하 고, 삭제 하 고, 배포의 공통 영역 전화에 대 한 구성 정보를 구성 하 고 확인 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-110">Use the topics in this section to learn how to create contact objects for common area phones, modify and delete them, and configure and view configuration information about the common area phones in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e411d-111">공통 영역 전화에는 Aastra 6721ip 공통 영역 전화, HP 4110 IP 전화 및 Polycom CX500 IP 공통 영역 전화에 대 한 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-111">You have three options for common area phones: the Aastra 6721ip common area phone, the HP 4110 IP Phone, and the Polycom CX500 IP common area phone.</span></span> <span data-ttu-id="e411d-112">Polycom CX3000 IP 회의 전화가 또 다른 변형 공통 영역 전화입니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-112">The Polycom CX3000 IP conferencing phone is another variant common area phone.</span></span> <span data-ttu-id="e411d-113">그러나 회의실에서 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e411d-113">However, it is intended for use in conference rooms.</span></span> <span data-ttu-id="e411d-114">공통 영역 전화에 대 한 자세한 내용은 <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">새 장치 선택</A>의 일반 영역 전화 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e411d-114">For details about common area phones, see the Common Area Phones section of <A href="https://technet.microsoft.com/library/gg398958(v=ocs.14).aspx">Choosing New Devices</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e411d-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="e411d-115">In This Section</span></span>

  - [<span data-ttu-id="e411d-116">Lync Server 2013에서 공통 영역 전화 정보 보기</span><span class="sxs-lookup"><span data-stu-id="e411d-116">View common area phone information in Lync Server 2013</span></span>](lync-server-2013-view-common-area-phone-information.md)

  - [<span data-ttu-id="e411d-117">Lync Server 2013에서 공통 영역 전화 연락처 개체 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="e411d-117">Create or modify a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="e411d-118">Lync Server 2013에서 핫 desking 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="e411d-118">Enable or disable hot desking in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-hot-desking.md)

  - [<span data-ttu-id="e411d-119">Lync Server 2013에서 공통 영역 전화 연락처 개체 삭제</span><span class="sxs-lookup"><span data-stu-id="e411d-119">Delete a common area phone Contact object in Lync Server 2013</span></span>](lync-server-2013-delete-a-common-area-phone-contact-object.md)

  - [<span data-ttu-id="e411d-120">Lync Server 2013의 정책을 공통 영역 전화에 할당</span><span class="sxs-lookup"><span data-stu-id="e411d-120">Assign policies in Lync Server 2013 to a common area phone</span></span>](lync-server-2013-assign-policies-to-a-common-area-phone.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

