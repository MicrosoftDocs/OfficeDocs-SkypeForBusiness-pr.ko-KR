---
title: 'Lync Server 2013: 대화형 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede826df74d63270afe2ea3f4e992cdcddbbe412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="83fd7-102">Lync Server 2013에서 대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="83fd7-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83fd7-103">_**마지막으로 수정한 주제:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="83fd7-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="83fd7-104">다음 절차 중 하나를 사용 하 여 대화형 워크플로를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="83fd7-105">Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="83fd7-106">Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나 다음 URL을 입력 하 여 웹 브라우저에서 직접 웹 페이지를 열 수 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="83fd7-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="83fd7-107">응답 그룹 구성 도구를 사용 하 여 대화형 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="83fd7-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="83fd7-108">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="83fd7-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="83fd7-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="83fd7-111">왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="83fd7-112">**워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="83fd7-113">서비스 검색 **선택** 필드에 만들거나 수정할 워크플로를 호스트 하는 **applicationserver** 서비스 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="83fd7-114">서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-115">응답 그룹 구성 도구가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="83fd7-116">다음 URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="83fd7-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="83fd7-117">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="83fd7-118">**새 워크플로 만들기**에서 **대화형**옆에 있는 **만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="83fd7-119">**기존 워크플로 관리**에서 변경 하려는 워크플로를 찾은 다음, **실행**에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="83fd7-120">사용자가 워크플로 호출을 시작할 준비가 되지 않은 경우 **워크플로 활성화** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-121">관리 되는 워크플로를 만들려면 <STRONG>워크플로 활성화</STRONG>를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-121">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="83fd7-122">관리 되는 활성 워크플로를 저장 한 후에는 수정 하 고 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-122">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="83fd7-123">페더레이션 사용자가 그룹에 전화를 걸 수 있도록 허용 하려면 **페더레이션 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="83fd7-124">또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-125">글로벌 외부 액세스 정책이 응답 그룹 응용 프로그램에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="83fd7-126">Lync Server 제어판을 사용 하거나 <STRONG>set-CsExternalAccessPolicy</STRONG> cmdlet을 사용 하 여 Enableout 액세스 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션에 대 한 전역 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="83fd7-127">전역 정책 설정은 사이트 또는 사용자 정책을 할당 하지 않는 한 모든 사용자에 게 적용 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="83fd7-128">따라서 응답 그룹에 대해이 설정을 변경 하기 전에 페더레이션 설정이 조직의 요구 사항에 맞는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="83fd7-129">정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="83fd7-130">페더레이션 설정에 대 한 자세한 내용은 Lync Server 관리 셸 설명서의 <STRONG>CsExternalAccessPolicy</STRONG> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-131">Lync Online에서 호스팅되는 사용자는 온-프레미스 배포에 호스팅된 응답 그룹에 대 한 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="83fd7-132">이는 온-프레미스 배포와 Lync Online 배포에 연결 된 경우에 모두 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="83fd7-133">통화 중 에이전트의 id를 숨기려면 **에이전트 익명 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-134">관리자나 발신자는 전화를 설정한 후에 IM 및 비디오를 추가할 수 있지만, 익명 호출은 메신저 또는 비디오로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="83fd7-135">익명 에이전트는 통화 대기, 통화 전환 (블라인드 및 consultative 전송 모두)을 할 수 있으며 통화를 전환 하 고 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="83fd7-136">익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, whiteboarding, 데이터 공동 작업, 통화 기록을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="83fd7-137">Lync VDI 플러그 인을 사용 하는 상담원은 들어오는 호출을 익명으로 받을 수 있지만, 나가는 호출을 익명으로 할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="83fd7-138">에서 **전화를 받을 그룹의 주소 입력**에 워크플로 호출에 응답할 그룹의 기본 SIP uri (uniform resource identifier) 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="83fd7-139">**표시 이름**에 워크플로에 대해 표시할 이름 (예: 영업권 IVR 응답 그룹)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-140">표시 이름에 "&lt;" 또는 "&gt;" 문자를 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="83fd7-141">다음 표시 이름은 예약 됨: RGS 현재 감시자 또는 알림 서비스 이므로 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="83fd7-142">**전화 번호**에서 응답 그룹에 대 한 줄 URI를 입력 합니다 (예: + 14255550165).</span><span class="sxs-lookup"><span data-stu-id="83fd7-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="83fd7-143">**표시 번호**에서 응답 그룹에 대해 표시할 숫자를 입력 합니다 (예: + 1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="83fd7-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="83fd7-144">) **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="83fd7-145">**워크플로 유형에**서이 워크플로를 응답 그룹 관리자가 관리 하는 경우 **관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="83fd7-146">응답 그룹 관리자를 워크플로에 할당 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="83fd7-147">이 워크플로에 대 한 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="83fd7-148">워크플로에 추가할 추가 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="83fd7-149">응답 그룹의 관리자로 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-149">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="83fd7-150">사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-150">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="83fd7-151">**2 단계에서 언어를 선택**하 고 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="83fd7-152">환영 메시지를 구성 하려면 **3 단계에서 환영 메시지 구성**확인란을 선택 하 고 다음 중 하나를 **수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="83fd7-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="83fd7-153">환영 메시지를 발신자를 위해 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 환영 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-154">입력 한 텍스트에 HTML 태그를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-154">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="83fd7-155">HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-155">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="83fd7-156">환영 메시지에 웨이브 또는 Windows Media 오디오 파일 기록을 사용 하려면 **기록 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-156">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="83fd7-157">새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-157">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="83fd7-158">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용 하려는 오디오 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-158">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="83fd7-159">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-159">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-160">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="83fd7-161">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="83fd7-162">**4 단계에서 업무 시간을 지정**하 고 **표준 시간대** 상자에서 워크플로의 표준 시간대를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-163">표준 시간대는 워크플로의 호출자와 에이전트가 상주 하는 표준 시간대입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-163">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="83fd7-164">이 메서드는 시작 시간과 종료 시간을 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-164">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="83fd7-165">예를 들어 워크플로가 북미 동부 표준 시간대를 사용 하도록 구성 되 고 워크플로가 오전 7:00 시에 열리도록 예약 된 경우</span><span class="sxs-lookup"><span data-stu-id="83fd7-165">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="83fd7-166">11:00 P.M.에서 시작 하 여 닫은 시간은 각각 7:00 동부 표준시와 11:00 동부 시간으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-166">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively.</span></span> <span data-ttu-id="83fd7-167">(24 시간 표시법으로 시간을 입력 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="83fd7-167">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="83fd7-168">다음 중 하나를 실행 하 여 사용 하려는 업무 시간 일정의 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="83fd7-169">미리 정의 된 업무 시간 일정을 사용 하려면 **미리 설정 된 일정 사용**을 클릭 한 다음 드롭다운 목록에서 사용할 일정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-170">이 옵션을 선택할 수 있으려면 이전에 미리 설정 된 일정이 하나 이상 정의 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="83fd7-171"><STRONG>새 CSRgsHoursOfBusiness</STRONG> cmdlet을 사용 하 여 미리 설정 된 일정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="83fd7-172">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(선택 사항) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="83fd7-173">미리 설정 된 일정을 선택 하면 <STRONG>일</STRONG>, <STRONG>열기</STRONG>및 <STRONG>닫기</STRONG> 가 자동으로 응답 그룹을 사용할 수 있는 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="83fd7-174">이 워크플로에만 적용 되는 사용자 지정 일정을 사용 하려면 **사용자 지정 일정 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="83fd7-175">이 워크플로에 대 한 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 요일의 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="83fd7-176">사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있게 되 면 **열기** 및 **닫기** 시간을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-177"><STRONG>열기</STRONG> 시간과 <STRONG>종료</STRONG> 시간은 24 시간 표기 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-177">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation.</span></span> <span data-ttu-id="83fd7-178">예를 들어, office가 9 ~ 5 개의 작업일로 근무 하 고 점심 시간에 종료 되는 경우 업무 시간은 <STRONG>열린</STRONG> 9:00, <STRONG>종료</STRONG> 12:00, <STRONG>열기</STRONG> 13:00 및 <STRONG>닫기</STRONG> 17:00로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-178">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="83fd7-179">Office가 열려 있지 않은 경우 메시지를 재생 하려면 **응답 그룹이 업무 시간을 초과 하면 메시지 재생** 확인란을 선택 하 고 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="83fd7-180">메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-181">입력 한 텍스트에 HTML 태그를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-181">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="83fd7-182">HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-182">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="83fd7-183">메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-183">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="83fd7-184">새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-184">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="83fd7-185">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-185">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="83fd7-186">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-186">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-187">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="83fd7-188">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="83fd7-189">메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):</span><span class="sxs-lookup"><span data-stu-id="83fd7-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="83fd7-190">통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="83fd7-191">전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="83fd7-192">음성 메일 주소의 형식은 사용자 \<이름\>@\<domainname\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="83fd7-193">다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="83fd7-194">사용자 주소의 형식은 \<username\>@\<domainname\>입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="83fd7-195">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="83fd7-196">전화 \<번호의 형식은 번호\>@\<의 이름\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="83fd7-197">도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="83fd7-198">**5 단계에서 공휴일을 지정**하 고 응답 그룹을 비즈니스용으로 닫은 날을 정의 하는 하나 이상의 공휴일 집합에 해당 하는 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-199">워크플로를 구성 하기 전에 휴일 및 휴일 집합을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="83fd7-200"><STRONG>CsRgsHoliday</STRONG> 및 <STRONG>new-CsRgsHolidaySet</STRONG> cmdlet을 사용 하 여 휴일 및 휴일 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="83fd7-201">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(선택 사항) Lync Server 2013에서 응답 그룹 휴일 집합 정의</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="83fd7-202">휴일에서 메시지를 재생 하려면 **공휴일 중 메시지 재생** 확인란을 선택한 후 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="83fd7-203">메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-204">입력 한 텍스트에 HTML 태그를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-204">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="83fd7-205">HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-205">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="83fd7-206">메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-206">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="83fd7-207">새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-207">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="83fd7-208">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-208">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="83fd7-209">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-209">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-210">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="83fd7-211">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="83fd7-212">메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):</span><span class="sxs-lookup"><span data-stu-id="83fd7-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="83fd7-213">통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="83fd7-214">전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="83fd7-215">음성 메일 주소의 형식은 사용자 \<이름\>@\<domainname\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="83fd7-216">다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="83fd7-217">사용자 주소의 형식은 \<username\>@\<domainname\>입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="83fd7-218">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="83fd7-219">전화 \<번호의 형식은 번호\>@\<의 이름\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="83fd7-220">도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="83fd7-221">**6 단계에서 음악 구성**에서 다음 중 하나를 수행 하 여 에이전트를 기다리는 동안 호출자가 수신할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="83fd7-222">기본 음악 보관 기록 기능을 사용 하려면 **기본값 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="83fd7-223">대기 중인 음악에 오디오 파일 녹음/녹화를 사용 하려면 **음악 파일 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-223">To use an audio file recording for the on-hold music, click **Select a music file**.</span></span> <span data-ttu-id="83fd7-224">새 오디오 파일을 업로드 하려면 **음악 파일** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-224">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="83fd7-225">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-225">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="83fd7-226">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-226">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-227">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="83fd7-228">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="83fd7-229">**7 단계 대화형 음성 응답 구성**아래에 있는 **사용자는 다음 텍스트 또는 녹음 된 메시지 제목을 들** 을 수 있습니다. 라는 질문을 지정 하 여 다음과 같이 발신자를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="83fd7-230">질문을 텍스트 형식으로 입력 하려면 **텍스트 읽어주기 사용**을 클릭 하 고 텍스트 상자에 질문을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-231">입력 한 텍스트에 HTML 태그를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-231">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="83fd7-232">HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-232">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-233">"#" 기호는 텍스트 음성 변환 엔진에 의해 "number" 라는 단어로 번역 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="83fd7-234"># Key를 참조 해야 하는 경우에는 프롬프트에 기호 대신 키 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="83fd7-235">예를 들어 "영업부와 대화 하려면 우물 정자" 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="83fd7-236">질문을 포함 하는 미리 녹음 된 오디오 파일을 사용 하려면 **기록 선택**을 클릭 한 다음 **기록** 링크를 클릭 하 여 파일을 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-236">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="83fd7-237">새 브라우저 창에서 **찾아보기를**클릭 하 고 오디오 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-237">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="83fd7-238">**업로드** 를 클릭 하 여 파일을 로드 한 다음 선택적으로 텍스트 상자에 질문을 입력할 수 있습니다 (질문 및 호출자의 응답을 응답 하는 에이전트로 착신 전환 가능).</span><span class="sxs-lookup"><span data-stu-id="83fd7-238">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="83fd7-239">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="83fd7-240">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="83fd7-241">**응답 1**아래에서 다음을 수행 하 여 질문에 대 한 첫 번째 응답을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="83fd7-242">음성 응답에 따옴표 (")를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="83fd7-242">Do not use quotation marks (") in any voice responses.</span></span> <span data-ttu-id="83fd7-243">큰따옴표는 IVR을 실패 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-243">Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-244">전화 건 사람이 음성, 영숫자 키패드 입력 또는 둘 다를 사용 하 여 응답 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="83fd7-245">발신자가 음성을 사용 하 여 응답할 수 있도록 허용 하려면 **음성 응답 입력**에 대답을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="83fd7-246">키패드에서 키를 눌러 발신자가 응답할 수 있도록 허용 하려면 키패드 **숫자를 클릭**합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="83fd7-247">호출자를 큐로 보낼지 아니면 다음과 같이 다른 질문을 요청할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="83fd7-248">호출자를 큐로 라우팅하려면 큐 **에 보내기를**클릭 하 고 **큐에 선택**에서 사용할 큐를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="83fd7-249">다른 질문을 요청 하려면 **다른 질문**하기를 클릭 한 다음 **텍스트 읽어주기 사용** 을 클릭 하 여 질문을 입력 하거나 **기록 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-249">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**.</span></span> <span data-ttu-id="83fd7-250">이 섹션의 응답 그룹을 사용 하 여 추가 질문 및 각 응답에 대해 사용할 큐에 대해 최대 4 개의 응답을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-250">Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response.</span></span> <span data-ttu-id="83fd7-251">세 번째 또는 네 번째 가능 응답을 지정 하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-251">To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="83fd7-252">28 ~ 29 단계를 반복 하 여 가능 응답과 각 응답에 대해 수행할 작업을 지정 하 여 원래 질문에 대 한 답변을 최대 3 개까지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-252">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response.</span></span> <span data-ttu-id="83fd7-253">세 번째 또는 네 번째로 발생할 수 있는 답변을 지정 하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-253">To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="83fd7-254">**배포**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="83fd7-255">Windows PowerShell을 사용 하 여 대화형 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="83fd7-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="83fd7-256">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="83fd7-257">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="83fd7-258">응답 그룹 서비스의 서비스 이름을 검색 하 고 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-258">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="83fd7-259">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-259">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="83fd7-260">대화형 워크플로에는 두 개 이상의 큐와 두 개 이상의 에이전트 그룹이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-260">An interactive workflow requires two or more queues and two or more agent groups.</span></span> <span data-ttu-id="83fd7-261">먼저 에이전트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-261">First, create the agent groups.</span></span> <span data-ttu-id="83fd7-262">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-262">Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="83fd7-263">큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-263">Create the queues.</span></span> <span data-ttu-id="83fd7-264">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-264">Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="83fd7-265">첫 번째 응답 그룹 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-265">Create the first response group prompt.</span></span> <span data-ttu-id="83fd7-266">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-266">Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="83fd7-267">그런 다음 프롬프트 후에 수행할 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-267">Then create the action to be performed after the prompt.</span></span> <span data-ttu-id="83fd7-268">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-268">Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="83fd7-269">첫 번째 응답 그룹 응답을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-269">Create the first response group answer.</span></span> <span data-ttu-id="83fd7-270">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-270">Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="83fd7-271">이제 두 번째 프롬프트를 만들고, 착신 동작을 수행 하 고, 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-271">Now create the second prompt, call action, and answer.</span></span> <span data-ttu-id="83fd7-272">먼저 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-272">First create the prompt.</span></span> <span data-ttu-id="83fd7-273">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-273">Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="83fd7-274">두 번째 호출 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-274">Create the second call action.</span></span> <span data-ttu-id="83fd7-275">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-275">Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="83fd7-276">두 번째 응답 그룹 응답을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-276">Create the second response group answer.</span></span> <span data-ttu-id="83fd7-277">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-277">Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="83fd7-278">최상위 수준의 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-278">Create the top-level prompt.</span></span> <span data-ttu-id="83fd7-279">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-279">Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="83fd7-280">최상위 수준의 질문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-280">Create the top-level question.</span></span> <span data-ttu-id="83fd7-281">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-281">Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="83fd7-282">이제 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-282">Now create the workflow.</span></span> <span data-ttu-id="83fd7-283">런</span><span class="sxs-lookup"><span data-stu-id="83fd7-283">Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83fd7-284">응답 그룹 관리자로 지정 된 모든 사용자에 게는 CsResponseGroupManager 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-284">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role.</span></span> <span data-ttu-id="83fd7-285">사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83fd7-285">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

