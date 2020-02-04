---
title: 'Lync Server 2013: 전화 접속 회의 액세스 번호 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="29d6b-102">Lync Server 2013에서 전화 접속 회의 액세스 번호 구성</span><span class="sxs-lookup"><span data-stu-id="29d6b-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29d6b-103">_**마지막으로 수정한 주제:** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="29d6b-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="29d6b-104">전화 접속 회의를 배포 하는 경우 오디오 회의에 참가 하기 위해 사용자가 PSTN (공개 전환 전화 네트워크)에서 전화를 걸 수 있는 전화 번호를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="29d6b-105">이러한 전화 접속 액세스 번호는 모임 초대 및 전화 접속 회의 설정 웹 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="29d6b-106">전화 접속 액세스 번호를 만들려면 먼저 전화 접속 회의 영역을 계획 한 다음 해당 지역으로 다이얼 플랜을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="29d6b-107">지역에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 전화 접속 회의 요구 사항을](lync-server-2013-dial-in-conferencing-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29d6b-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="29d6b-108">전화 접속 회의에 대 한 다이얼 플랜을 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 전화 접속 회의에 대 한 다이얼 플랜 구성을](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29d6b-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29d6b-109">해당 액세스 번호의 AD&nbsp;DS (Active Directory 도메인 서비스) 복제가 완료 될 때까지 새 전화 접속 액세스 번호를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="29d6b-110">복제를 완료 하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="29d6b-111">전화 접속 액세스 번호를 만든 후에는 사용자가 올바른 액세스 번호를 더 쉽게 식별할 수 있도록 Active Directory 연락처 개체의 표시 이름을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="29d6b-112"><STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet을 사용 하 여 표시 이름을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="29d6b-113">Active Directory 개체를 수동으로 수정 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29d6b-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="29d6b-114">액세스 번호를 수정 하는 방법에 대 한 자세한 내용은 <STRONG>CsDialInConferencingAccessNumber</STRONG> cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29d6b-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="29d6b-115">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="29d6b-115">In This Section</span></span>

[<span data-ttu-id="29d6b-116">Lync Server 2013에서 전화 접속 회의 액세스 번호 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="29d6b-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29d6b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="29d6b-117">See Also</span></span>


[<span data-ttu-id="29d6b-118">Lync Server 2013의 전화 접속 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="29d6b-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="29d6b-119">Lync Server 2013에서 전화 접속 회의에 대한 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="29d6b-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

