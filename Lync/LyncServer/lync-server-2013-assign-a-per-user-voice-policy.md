---
title: 'Lync Server 2013: 사용자별 음성 정책 할당'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943931"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="830e6-102">Lync Server 2013에서 사용자별 음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="830e6-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="830e6-103">전역 및 사이트 수준 음성 정책은 Enterprise Voice를 사용 하도록 설정 된 모든 Lync Server 2013 사용자 계정에 자동으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="830e6-104">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸을 사용 하 여 특정 사용자에 게 음성 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="830e6-105">사용자 단위 정책을 Lync Server 사용자에 게 명시적으로 할당 하려면이 항목의 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="830e6-106">Lync Server 제어판을 사용 하 여 사용자 관련 음성 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="830e6-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="830e6-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="830e6-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="830e6-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="830e6-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="830e6-110">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성할 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="830e6-111">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="830e6-112">**음성 정책** 아래의 **Lync Server 사용자 편집**에서 적용할 사용자 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="830e6-113"><STRONG> &lt; 자동 &gt; </STRONG> 설정은 기본 서버 또는 전역 정책 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="830e6-114">사용자별 음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="830e6-114">Assign per-user voice policies</span></span>

<span data-ttu-id="830e6-115">Windows PowerShell 및 **set-csvoicepolicy** cmdlet을 사용 하 여 사용자별 음성 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="830e6-116">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="830e6-117">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용을 보려면이 Lync Server Windows PowerShell 블로그 게시물: [빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync server 2010 관리](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="830e6-117">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="830e6-118">단일 사용자에 게 사용자별 음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="830e6-118">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="830e6-119">다음 명령은 사용자 Ken Myer에게 사용자별 음성 정책 RedmondVoicePolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="830e6-120">여러 사용자에 게 사용자별 음성 정책 할당</span><span class="sxs-lookup"><span data-stu-id="830e6-120">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="830e6-121">이 명령은 사용자별 음성 정책 FinanceVoicePolicy를 Active Directory의 Finance OU에 계정이 있는 모든 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="830e6-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="830e6-122">이 명령에 사용 되는 OU 매개 변수에 대 한 자세한 내용은 [csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) u i c c i c c a c c # cmdlet의 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="830e6-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="830e6-123">사용자별 음성 정책 할당 해제</span><span class="sxs-lookup"><span data-stu-id="830e6-123">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="830e6-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="830e6-124">The following command unassigns any per-user voice policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="830e6-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span><span class="sxs-lookup"><span data-stu-id="830e6-125">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="830e6-126">A site policy takes precedence over the global policy.</span><span class="sxs-lookup"><span data-stu-id="830e6-126">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="830e6-127">자세한 내용은 [set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="830e6-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="830e6-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="830e6-128">See Also</span></span>


[<span data-ttu-id="830e6-129">Lync Server 2013에서 Enterprise Voice에 대 한 사용자 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="830e6-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="830e6-130">Lync Server 2013 관리 셸</span><span class="sxs-lookup"><span data-stu-id="830e6-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

