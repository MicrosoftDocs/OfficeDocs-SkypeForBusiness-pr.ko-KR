---
title: 'Lync Server 2013: 음성 라우팅 테스트 사례 가져오기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43ab26d61009683623d3c536a26c8be04a3846e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a><span data-ttu-id="f7a8f-102">Lync Server 2013에서 음성 라우팅 테스트 사례 가져오기</span><span class="sxs-lookup"><span data-stu-id="f7a8f-102">Import voice routing test cases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7a8f-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f7a8f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f7a8f-104">테스트 사례를 통해 조직에서 음성 경로를 테스트할 수 있습니다. 전화를 걸고 사용할 번호와 다이얼 플랜 및 음성 정책을 정의 하 고 Lync Server 2013에서 제공 된 succes 수 있는지 확인할 수 있습니다. sfully PSTN 네트워크로 완전히 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-104">Test cases provide a way for you to test voice routes in your organization: you define such things as the number to be dialed and the dial plan and voice policy to be employed, and Lync Server 2013 can then verify that, given those conditions, the supplied number can successfully be routed to the PSTN network.</span></span>

<span data-ttu-id="f7a8f-105">Lync Server 제어판을 사용 하 여 만들 수 있는 테스트 사례는 일반적으로 대/소문자를 처음 만든 후 실행 한 서버에만 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-105">Test cases, which can be created by using Lync Server Control Panel, are typically saved only on the server where the case was originally created and run.</span></span> <span data-ttu-id="f7a8f-106">하지만 이러한 테스트 사례를 XML 파일(.vtest 확장명)로 내보내고 다른 서버에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-106">However, these test cases can be exported as XML files (with the .vtest extension) and then imported on other servers.</span></span> <span data-ttu-id="f7a8f-107">이러한 방식을 통해 토폴로지의 여러 지점에 있는 서로 다른 컴퓨터에서 동일한 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-107">This enables you to run the same tests on different computers located at different points in your topology.</span></span>

<div>

## <a name="to-import-a-voice-routing-test-case"></a><span data-ttu-id="f7a8f-108">음성 라우팅 테스트 사례를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="f7a8f-108">To import a voice routing test case</span></span>

1.  <span data-ttu-id="f7a8f-109">RTCUniversalServerAdmins 그룹의 구성원으로 또는 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 역할의 구성원으로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f7a8f-110">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f7a8f-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f7a8f-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f7a8f-113">왼쪽 탐색 모음에서 **음성 라우팅**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-113">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="f7a8f-114">**동작** 메뉴에서 **테스트 사례 가져오기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-114">On the **Actions** menu, click **Import test cases**.</span></span>

5.  <span data-ttu-id="f7a8f-115">가져올 테스트 사례 파일 (vtest)을 찾은 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-115">Find the test case file (.vtest) that you want to import, and then click **Open**.</span></span>

6.  <span data-ttu-id="f7a8f-116">**커밋**을 클릭한 후 **모두 커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-116">Click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7a8f-117">Vtest 파일을 가져올 때마다 <STRONG>모두 커밋</STRONG> 명령을 실행 하 여 테스트 사례를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-117">Whenever you import a .vtest file, you must run the <STRONG>Commit all</STRONG> command to publish the test case.</span></span> <span data-ttu-id="f7a8f-118">자세한 내용은 작업 설명서의 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f7a8f-118">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7a8f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7a8f-119">See Also</span></span>


[<span data-ttu-id="f7a8f-120">Lync Server 2013에서 음성 라우팅 테스트 사례 내보내기</span><span class="sxs-lookup"><span data-stu-id="f7a8f-120">Export voice routing test cases in Lync Server 2013</span></span>](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

