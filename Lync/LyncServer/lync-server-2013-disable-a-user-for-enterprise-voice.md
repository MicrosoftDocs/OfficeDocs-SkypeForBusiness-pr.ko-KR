---
title: 'Lync Server 2013: 사용자가 Enterprise Voice를 사용 하지 않도록 설정'
description: 'Lync Server 2013: 사용자가 Enterprise Voice를 사용할 수 없도록 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d99916444e2b1c984e251f6e6289d88e31a538a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568214"
---
# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="70bde-103">Lync Server 2013에서 Enterprise Voice에 대 한 사용자 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="70bde-103">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70bde-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="70bde-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="70bde-105">다음 절차에 따라 Lync Server 2013에 대해 사용 하도록 설정 된 사용자 계정에 대해 Enterprise Voice를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-105">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="70bde-106">Enterprise Voice에 대 한 사용자 계정을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="70bde-106">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="70bde-107">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70bde-108">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="70bde-109">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="70bde-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70bde-110">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="70bde-111">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="70bde-112">테이블에서 Enterprise Voice를 사용 하도록 설정 하려는 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-112">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="70bde-113">**편집** 메뉴에서 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="70bde-114">**Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice**를 제외한 아무 옵션이나 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-114">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="70bde-115">사용자가 Lync를 사용 하 여 오디오 또는 비디오 통화를 수행 하지 못하도록 제한 하려면 <STRONG>전화 통신</STRONG>아래에서 <STRONG>오디오/비디오 사용 안 함을</STRONG>클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-115">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="70bde-116">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-116">Click **Commit**.</span></span>

<span data-ttu-id="70bde-117">이제 사용자가 Enterprise Voice 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70bde-117">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="70bde-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70bde-118">See Also</span></span>


[<span data-ttu-id="70bde-119">Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="70bde-119">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="70bde-120">Lync Server 2013의 사용자에 대 한 Enterprise Voice 관리</span><span class="sxs-lookup"><span data-stu-id="70bde-120">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="70bde-121">Lync Server 2013 관리 셸</span><span class="sxs-lookup"><span data-stu-id="70bde-121">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

