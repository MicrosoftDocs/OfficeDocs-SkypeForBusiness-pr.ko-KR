---
title: 'Lync Server 2013: (선택 사항) 전화 접속 회의 설정 확인'
description: 'Lync Server 2013: (선택 사항) 전화 접속 회의 설정을 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec002cfbd7cdd67498768a360143f88ab4f8e1b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572564"
---
# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a><span data-ttu-id="e2906-103">반드시 Lync Server 2013에서 전화 접속 회의 설정 확인</span><span class="sxs-lookup"><span data-stu-id="e2906-103">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2906-104">_**마지막으로 수정 된 항목:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="e2906-104">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="e2906-p101">전화 접속 회의 구성의 최종 확인 작업으로 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 다이얼 플랜 및 전화 접속 회의 지역이 할당되지 않은 액세스 번호를 검색할 수 있습니다. 이 단계는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-p101">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region. This step is optional.</span></span>

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="e2906-107">액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 다이얼 플랜을 찾으려면</span><span class="sxs-lookup"><span data-stu-id="e2906-107">To find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1.  <span data-ttu-id="e2906-108">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="e2906-109">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e2906-110">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    <span data-ttu-id="e2906-111">이 cmdlet은 액세스 번호에서 사용되지 않은 전화 접속 회의 지역이 포함된 모든 다이얼 플랜을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a><span data-ttu-id="e2906-112">지역이 할당되지 않은 액세스 번호를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="e2906-112">To find access numbers without assigned regions</span></span>

1.  <span data-ttu-id="e2906-113">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="e2906-114">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e2906-115">명령 프롬프트에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-115">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    <span data-ttu-id="e2906-116">이 cmdlet은 지역과 연관되지 않은 모든 전화 접속 회의 액세스 번호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e2906-116">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

