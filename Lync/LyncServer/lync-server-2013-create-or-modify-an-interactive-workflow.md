---
title: 'Lync Server 2013: 대화형 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7173d739c66982d0995a478e086fee2442fcbd0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="851dc-102">Lync Server 2013에서 대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="851dc-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="851dc-103">_**마지막으로 수정 된 항목:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="851dc-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="851dc-104">다음 절차를 사용하여 대화형 워크플로를 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="851dc-105">Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="851dc-106">Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나, 다음 URL: <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>을 입력 하 여 웹 브라우저에서 페이지를 직접 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="851dc-107">응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="851dc-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="851dc-108">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="851dc-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="851dc-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="851dc-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="851dc-111">왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **워크플로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="851dc-112">**워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="851dc-113">**서비스 선택** 검색 필드에 만들거나 수정할 워크플로를 호스트 하는 **applicationserver** 서비스의 이름 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="851dc-114">서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-115">응답 그룹 구성 도구가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="851dc-116"><STRONG>Https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="851dc-117">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="851dc-118">**새 워크플로 만들기** 아래에서 **대화형** 옆에 있는 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="851dc-119">**기존 워크플로 관리**에서 변경할 워크플로를 찾은 다음 **동작**에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="851dc-120">사용자가 워크플로 호출을 시작할 수 있도록 준비되지 않은 경우 **워크플로 활성화** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-p105">관리 워크플로를 만들려는 경우 <STRONG>워크플로 활성화</STRONG>를 선택해야 합니다. 활성화된 관리 워크플로를 저장한 후에는 이 워크플로를 수정하고 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="851dc-123">페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="851dc-124">또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-125">전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="851dc-126">Lync Server 제어판을 사용 하거나 <STRONG>get-csexternalaccesspolicy</STRONG> cmdlet을 사용 하 여 Enableout access 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션을 위한 전역 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="851dc-127">전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="851dc-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="851dc-128">따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="851dc-129">정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="851dc-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="851dc-130">페더레이션 설정에 대 한 자세한 내용은 <STRONG>get-csexternalaccesspolicy</STRONG> In Lync Server Management Shell 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="851dc-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-131">Lync Online에서 호스트 되는 사용자는 온-프레미스 배포에서 호스트 되는 응답 그룹에 대 한 호출을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="851dc-132">이는 하이브리드 배포와 온-프레미스 배포가 Lync Online 배포와 연결 된 경우 모두에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="851dc-133">통화하는 동안 에이전트의 ID를 숨기려면 **에이전트 익명성 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-134">통화가 연결된 후 에이전트 또는 발신자가 IM(인스턴트 메시징) 및 비디오를 추가할 수 있지만 IM 또는 비디오로 익명 통화를 시작할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="851dc-135">익명 에이전트는 통화를 보류하고, 전송(무조건 전송 및 협의 전송)하고, 대기시킨 후 재개할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="851dc-136">익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, 화이트보드 및 데이터 공동 작업, 통화 기록을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="851dc-137">Lync VDI 플러그 인을 사용 하는 에이전트는 들어오는 호출을 익명으로 받을 수 있지만 발신 전화를 익명으로 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="851dc-138">**전화를 받을 그룹의 주소를 입력하십시오**에 워크플로 호출에 응답할 그룹의 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="851dc-139">**표시 이름**에 클라이언트에서 워크플로에 대해 표시하도록 할 이름(예: Sales IVR Response Group)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-140">표시 이름에 "&lt;" 또는 "&gt;" 문자를 포함 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="851dc-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="851dc-141">RGS Presence Watcher 또는 알림 서비스는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="851dc-142">**전화 번호**에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="851dc-143">**표시 이름**에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="851dc-144">반드시 **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="851dc-145">이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형**에서 **관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="851dc-146">응답 그룹 관리자를 워크플로에 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="851dc-147">이 워크플로 관리자의 SIP URI를 입력하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="851dc-148">추가 관리자의 SIP URI를 입력하여 워크플로에 추가하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="851dc-p112">응답 그룹의 관리자로 지정된 모든 사용자는 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="851dc-151">**2단계 언어 선택** 아래에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="851dc-152">환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="851dc-153">환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-p113">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="851dc-p114">환영 메시지에 웨이브 또는 Windows Media 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-160">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="851dc-161">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="851dc-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="851dc-162">**4단계 업무 시간 지정** 아래에 있는 **표준 시간대** 상자에서 워크플로의 표준 시간대를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-p116">표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오전 11:00:00시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="851dc-168">다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="851dc-169">미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용**을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-170">이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="851dc-171"><STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet을 사용하여 미리 설정된 일정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="851dc-172">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Lync Server 2013에서 응답 그룹 업무 시간 정의</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="851dc-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="851dc-173">미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 <STRONG>요일</STRONG>, <STRONG>시작</STRONG> 및 <STRONG>종료</STRONG>가 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="851dc-174">이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="851dc-175">이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="851dc-176">사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 **시작** 및 **종료** 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-p118"><STRONG>시작</STRONG> 및 <STRONG>종료</STRONG> 시간은 24시간 형식이어야 합니다. 예를 들어 평일 오전 9시에서 오후 5시까지 근무하고 12시부터 점심 시간 동안 문을 닫는 경우 업무 시간은 <STRONG>시작</STRONG> 9:00, <STRONG>종료</STRONG> 12:00, <STRONG>시작</STRONG> 13:00 및 <STRONG>종료</STRONG> 17:00로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="851dc-179">근무하지 않는 동안 메시지를 재생하려면 **응답 그룹의 업무 시간이 지났을 때 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="851dc-180">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-181">입력하는 텍스트에 HTML 태그를 포함하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="851dc-181">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="851dc-182">HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-182">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="851dc-p120">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-187">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="851dc-188">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="851dc-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="851dc-189">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="851dc-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="851dc-190">통화 연결을 끊으려면 **전화 끊기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="851dc-191">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="851dc-192">음성 메일 \<주소 형식은 사용자 이름\>@\<domainname\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="851dc-193">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="851dc-194">\<사용자 주소 형식은 username\>@\<domainname\>입니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="851dc-195">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="851dc-196">전화 번호 형식은 \<번호\>@\<domainname\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="851dc-197">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="851dc-198">**5단계 휴일 지정** 아래에서 응답 그룹이 근무하지 않는 요일을 정의하는 하나 이상의 휴일 집합에 대한 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-199">워크플로를 구성하기 전에 휴일 및 휴일 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="851dc-200"><STRONG>New-CsRgsHoliday</STRONG> 및 <STRONG>New-CsRgsHolidaySet</STRONG> cmdlet을 사용하여 휴일 및 휴일 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="851dc-201">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Lync Server 2013에서 응답 그룹 휴일 집합 정의</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="851dc-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="851dc-202">휴일에 메시지를 재생하려면 **휴일에 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 재생할 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="851dc-203">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-204">입력하는 텍스트에 HTML 태그를 포함하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="851dc-204">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="851dc-205">HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-205">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="851dc-p127">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-210">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="851dc-211">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="851dc-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="851dc-212">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="851dc-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="851dc-213">통화 연결을 끊으려면 **전화 끊기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="851dc-214">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="851dc-215">음성 메일 \<주소 형식은 사용자 이름\>@\<domainname\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="851dc-216">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="851dc-217">\<사용자 주소 형식은 username\>@\<domainname\>입니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="851dc-218">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="851dc-219">전화 번호 형식은 \<번호\>@\<domainname\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="851dc-220">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="851dc-221">**6단계 대기 음악 구성** 아래에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="851dc-222">기본 대기 음악 녹음을 사용하려면 **기본값 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="851dc-p132">오디오 파일 녹음을 대기 음악에 사용하려면 **음악 파일 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-227">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="851dc-228">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="851dc-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="851dc-229">**7단계 대화형 음성 응답 구성**의 **사용자에게 다음 텍스트 또는 녹음된 메시지가 재생됩니다** 머리글 아래에서 다음과 같이 발신자에게 제공할 질문을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="851dc-230">질문을 텍스트 형식으로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 질문을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-p134">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-233">"#" 기호는 텍스트 음성 변환 엔진에서 "숫자"라는 단어로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="851dc-234"># 키를 참조해야 하는 경우 프롬프트에 기호 대신 키 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="851dc-235">예를 들어 "sales와 대화 하려면 파운드 키를 누릅니다."</span><span class="sxs-lookup"><span data-stu-id="851dc-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="851dc-p136">질문이 포함된 미리 녹음된 오디오 파일을 사용하려면 **녹음 선택**을 클릭한 다음 **녹음** 링크를 클릭하여 파일을 업로드합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 오디오 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 파일을 로드한 다음 필요에 따라 텍스트 상자에 질문을 입력할 수 있습니다. 이렇게 하면 질문과 발신자의 응답이 응답 에이전트로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="851dc-239">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="851dc-240">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="851dc-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="851dc-241">**응답 1** 아래에서 다음을 수행하여 질문에 대한 첫 번째 가능한 응답을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="851dc-p138">음성 응답에 따옴표(")를 사용하지 마십시오. 따옴표를 사용하면 IVR에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-244">발신자가 음성과 영숫자 키패드 입력 중 하나 또는 둘 다를 사용하여 응답하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="851dc-245">발신자가 음성을 사용하여 응답하도록 하려면 **음성 응답 입력** 상자에 응답을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="851dc-246">발신자가 키패드의 키를 눌러 응답하도록 하려면 **숫자** 상자에서 키패드 숫자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="851dc-247">다음과 같이 발신자를 큐로 라우팅할지 또는 다른 질문을 제공할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="851dc-248">발신자를 큐로 라우팅하려면 **큐로 보내기**를 클릭한 다음 **큐 선택**에서 사용할 큐를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="851dc-p139">다른 질문을 제공하려면 **또 다른 질문하기**를 클릭한 다음 **텍스트 음성 변환 사용**을 클릭하고 질문을 입력하거나 **녹음 선택**을 클릭합니다. 이 섹션의 응답 그룹을 사용하여 추가 질문에 가능한 최대 4개의 응답 및 각 응답에 사용할 큐를 지정할 수 있습니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="851dc-p140">28단계와 29단계를 반복하여 원래 질문에 가능한 최대 3개의 응답을 추가로 지정하여 가능한 응답 및 각 응답에 대해 수행할 작업을 지정합니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="851dc-254">**배포**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="851dc-255">Windows PowerShell을 사용 하 여 대화형 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="851dc-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="851dc-256">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="851dc-257">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="851dc-p141">응답 그룹 서비스의 서비스 이름을 검색하여 변수 하나에 할당합니다. 명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="851dc-p142">대화형 워크플로를 만들려면 두 개 이상의 큐와 두 개 이상의 에이전트 그룹이 필요합니다. 먼저 다음을 실행하여 에이전트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="851dc-p143">다음을 실행하여 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="851dc-p144">다음을 실행하여 첫 번째 응답 그룹 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="851dc-p145">그런 다음 프롬프트 후에 수행할 동작을 만듭니다. 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="851dc-p146">다음을 실행하여 첫 번째 응답 그룹 답변을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="851dc-p147">이제 두 번째 프롬프트, 호출 동작 및 답변을 만듭니다. 먼저 다음을 실행하여 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="851dc-p148">다음을 실행하여 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="851dc-p149">다음을 실행하여 두 번째 응답 그룹 답변을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="851dc-p150">다음을 실행하여 최상위 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="851dc-p151">다음을 실행하여 최상위 질문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="851dc-p152">이제 다음을 실행하여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="851dc-p153">응답 그룹의 관리자로 지정된 모든 사용자는 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="851dc-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

