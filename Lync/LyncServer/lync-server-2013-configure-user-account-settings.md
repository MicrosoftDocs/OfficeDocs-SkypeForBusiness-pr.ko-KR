---
title: 'Lync Server 2013: 사용자 계정 설정 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b3c8ea077b6dee724d131ea117aa7bf304e114
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="d1006-102">Lync Server 2013에서 사용자 계정 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d1006-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1006-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="d1006-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="d1006-104">전화 접속 사용자는 전화 번호나 내선 번호를 입력 하 여 인증 된 사용자로 회의에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="d1006-105">Lync Server 사용자 계정에 지정 된 전화 통신 **회선 URI** 가 인증에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="d1006-106">이 항목의 절차에서는 단일 사용자 계정에 대해 **줄 URI**를 할당하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="d1006-107">여러 사용자 계정에 대해 **줄 URI**를 할당해야 하는 경우 **Set-CsUser** cmdlet이 사용되는 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="d1006-108">샘플 스크립트를 사용 하 여 여러 사용자 계정에 **줄 URI** 를 할당 하는 방법에 대 한 자세한 내용은의 "여러 사용자 [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945)에 게 줄 uri 할당"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1006-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="d1006-109">사용자 계정 설정을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="d1006-109">To configure user account settings</span></span>

1.  <span data-ttu-id="d1006-110">RTCUniversalServerAdmins 그룹의 구성원이나 **Cs-UserAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="d1006-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d1006-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d1006-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d1006-113">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d1006-114">검색 필드에 전화 접속 회의에 대해 구성할 사용자 이름을 입력하거나 **필터 추가**를 클릭하여 검색 필드를 지정한 다음 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="d1006-115">사용자 이름을 두 번 클릭 하 여 **Lync Server 사용자 편집** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="d1006-116">**전화 통신**의 **줄 URI** 필드에 정규화된 고유한 전화 번호를 입력합니다(예: tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="d1006-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d1006-117"><STRONG>줄 URI</STRONG> 는 <STRONG>전화 통신이</STRONG> <STRONG>pc 대 pc 전용</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>원격 통화 제어</STRONG> 또는 <STRONG>원격 통화 제어 전용</STRONG>으로 설정 된 경우에만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="d1006-118">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d1006-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

