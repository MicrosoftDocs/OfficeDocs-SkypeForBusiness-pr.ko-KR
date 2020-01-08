---
title: 'Lync Server 2013: 헌트 그룹 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c927b10107626c1d40c33290b30f331f660e45e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="c8759-102">Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="c8759-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8759-103">_**마지막으로 수정한 주제:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="c8759-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="c8759-104">다음 절차 중 하나를 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8759-105">Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="c8759-106">Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나 다음 URL을 입력 하 여 웹 브라우저에서 직접 웹 페이지를 열 수 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c8759-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="c8759-107">응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="c8759-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="c8759-108">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c8759-109">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c8759-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c8759-111">왼쪽 탐색 모음에서 **응답 그룹**을 클릭 한 다음 **워크플로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="c8759-112">**워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="c8759-113">서비스 검색 **선택** 필드에 만들거나 변경할 워크플로를 호스트 하는 **applicationserver** 서비스 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="c8759-114">서비스 결과 목록에서 원하는 서비스를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-115">응답 그룹 구성 도구가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="c8759-116">다음 URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다. <STRONG>https://</STRONG>&lt;webpoolfqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c8759-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="c8759-117">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="c8759-118">**새 워크플로 만들기**에서 **헌트 그룹**옆에 있는 만들기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="c8759-119">**기존 워크플로 관리**에서 변경 하려는 워크플로를 찾은 다음, **실행**에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="c8759-120">사용자가 워크플로 호출을 시작할 준비가 되었으면 **워크플로 활성화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-121">관리 되는 워크플로를 만들려면 <STRONG>워크플로 활성화</STRONG>를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-121">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>.</span></span> <span data-ttu-id="c8759-122">관리 되는 활성 워크플로를 저장 한 후에는 수정 하 고 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-122">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="c8759-123">페더레이션 사용자가 그룹에 전화를 걸 수 있도록 허용 하려면 **페더레이션 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="c8759-124">또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-125">글로벌 외부 액세스 정책이 응답 그룹 응용 프로그램에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="c8759-126">Lync Server 제어판을 사용 하거나 <STRONG>set-CsExternalAccessPolicy</STRONG> cmdlet을 사용 하 여 Enableout 액세스 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션에 대 한 전역 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="c8759-127">전역 정책 설정은 사이트 또는 사용자 정책을 할당 하지 않는 한 모든 사용자에 게 적용 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="c8759-128">따라서 응답 그룹에 대해이 설정을 변경 하기 전에 페더레이션 설정이 조직의 요구 사항에 맞는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="c8759-129">정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="c8759-130">페더레이션 설정에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-131">Lync Online에서 호스팅되는 사용자는 온-프레미스 배포에 호스팅된 응답 그룹에 대 한 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="c8759-132">이는 온-프레미스 배포와 Lync Online 배포에 연결 된 경우에 모두 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="c8759-133">통화 중 에이전트의 id를 숨기려면 **에이전트 익명 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-134">관리자나 발신자는 전화를 설정한 후에 IM 및 비디오를 추가할 수 있지만, 익명 호출은 메신저 또는 비디오로 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="c8759-135">익명 에이전트는 통화 대기, 통화 전환 (블라인드 및 consultative 전송 모두)을 할 수 있으며 통화를 전환 하 고 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="c8759-136">익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, whiteboarding, 데이터 공동 작업, 통화 기록을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="c8759-137">Lync VDI 플러그 인을 사용 하는 상담원은 들어오는 호출을 익명으로 받을 수 있지만, 나가는 호출을 익명으로 할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="c8759-138">에서 **전화를 받을 그룹의 주소 입력**에 워크플로 호출에 응답할 그룹의 기본 SIP uri (uniform resource identifier) 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-139">워크플로의 기본 URI는 워크플로를 식별 하 고 참조 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="c8759-140">입력 하는 SIP URI는 Active Directory 도메인 서비스의 contact 개체로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="c8759-141">URI를 만들려면 개체가 Active Directory에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="c8759-142">**표시 이름**에 워크플로에 대해 표시할 이름 (예: 영업 응답 그룹)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-143">표시 이름에 "&lt;" 또는 "&gt;" 문자를 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="c8759-144">다음 표시 이름은 예약 됨: <STRONG>RGS 현재 감시자</STRONG> 또는 <STRONG>알림 서비스</STRONG>이므로 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="c8759-145">**전화 번호**에서 응답 그룹의 줄 URI를 입력 합니다 (예: + 14255550165).</span><span class="sxs-lookup"><span data-stu-id="c8759-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="c8759-146">**표시 번호**에서 응답 그룹에 대해 표시할 숫자를 입력 합니다 (예: + 1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="c8759-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="c8759-147">) **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="c8759-148">**워크플로 유형에**서이 워크플로를 응답 그룹 관리자가 관리 하는 경우 **관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="c8759-149">응답 그룹 관리자를 워크플로에 할당 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="c8759-150">이 워크플로에 대 한 관리자의 SIP URI를 입력 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="c8759-151">추가 관리자의 SIP URI를 입력 하 여 워크플로에 추가 하 고 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c8759-152">응답 그룹의 관리자로 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-152">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="c8759-153">사용자에 게이 역할이 할당 되지 않은 경우 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-153">If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="c8759-154">**2 단계에서 언어를 선택**하 고 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="c8759-155">환영 메시지를 구성 하려면 **3 단계에서 환영 메시지 구성**확인란을 선택 하 고 다음 중 하나를 **수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c8759-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="c8759-156">환영 메시지를 발신자를 위해 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 환영 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-157">입력 한 텍스트에 HTML 태그를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-157">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="c8759-158">HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-158">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="c8759-159">환영 메시지에 웨이브 (.wav) 또는 Windows Media 오디오 (.wma) 파일 기록을 사용 하려면 **기록 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-159">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**.</span></span> <span data-ttu-id="c8759-160">새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-160">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="c8759-161">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용 하려는 오디오 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-161">In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="c8759-162">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-162">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-163">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="c8759-164">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="c8759-165">**4 단계에서 업무 시간을 지정**하 고 **표준 시간대**에서 워크플로의 표준 시간대를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-166">표준 시간대는 워크플로의 호출자와 에이전트가 상주 하는 표준 시간대입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-166">The time zone is the time zone where the callers and agents of the workflow reside.</span></span> <span data-ttu-id="c8759-167">이 메서드는 시작 시간과 종료 시간을 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-167">It is used to calculate the open and close hours.</span></span> <span data-ttu-id="c8759-168">예를 들어 워크플로가 북미 동부 표준 시간대를 사용 하도록 구성 되 고 워크플로가 오전 7:00 시에 열리도록 예약 된 경우</span><span class="sxs-lookup"><span data-stu-id="c8759-168">For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M.</span></span> <span data-ttu-id="c8759-169">11:00 P.M.에서 시작 하 여 닫은 시간은 각각 7:00 동부 표준시와 23:00 동부 시간으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-169">and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively.</span></span> <span data-ttu-id="c8759-170">(24 시간 표시법으로 시간을 입력 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="c8759-170">(You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="c8759-171">다음 중 하나를 실행 하 여 사용 하려는 업무 시간 일정의 유형을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="c8759-172">미리 정의 된 업무 시간 일정을 사용 하려면 **미리 설정 된 일정 사용**을 클릭 한 다음 드롭다운 목록에서 사용할 일정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-173">이 옵션을 선택할 수 있으려면 이전에 미리 설정 된 일정이 하나 이상 정의 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="c8759-174"><STRONG>새 CSRgsHoursOfBusiness</STRONG> cmdlet을 사용 하 여 미리 설정 된 일정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="c8759-175">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(선택 사항) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-176">미리 설정 된 일정을 선택 하면 <STRONG>일</STRONG>, <STRONG>열기</STRONG>및 <STRONG>닫기</STRONG> 가 자동으로 응답 그룹을 사용할 수 있는 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="c8759-177">이 워크플로에만 적용 되는 사용자 지정 일정을 사용 하려면 **사용자 지정 일정 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="c8759-178">이 워크플로에 대 한 사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 요일의 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="c8759-179">사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 각 요일에 대해 **열기** 및 **닫기** 시간을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-180"><STRONG>열기</STRONG> 시간과 <STRONG>종료</STRONG> 시간은 24 시간 표기 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-180">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation.</span></span> <span data-ttu-id="c8759-181">예를 들어, office가 9 ~ 5 개의 작업일로 근무 하 고 점심 시간에 종료 되는 경우 업무 시간은 <STRONG>열린</STRONG> 9:00, <STRONG>종료</STRONG> 12:00, <STRONG>열기</STRONG> 13:00 및 <STRONG>닫기</STRONG> 17:00로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-181">For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="c8759-182">Office가 열려 있지 않은 경우 메시지를 재생 하려면 **응답 그룹이 업무 시간을 초과 하면 메시지 재생** 확인란을 선택 하 고 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="c8759-183">메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-184">입력 한 텍스트에 HTML 태그를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-184">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="c8759-185">HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-185">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="c8759-186">메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-186">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="c8759-187">새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-187">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="c8759-188">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-188">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="c8759-189">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-189">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-190">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="c8759-191">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="c8759-192">메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):</span><span class="sxs-lookup"><span data-stu-id="c8759-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="c8759-193">통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="c8759-194">전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="c8759-195">음성 메일 주소의 형식은 사용자 \<이름\>@\<domainName\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="c8759-196">다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="c8759-197">사용자 주소의 형식은 \<username\>@\<domainName\>입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="c8759-198">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="c8759-199">전화 \<번호의 형식은 번호\>@\<의 이름\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="c8759-200">도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="c8759-201">**5 단계에서 공휴일을 지정**하 고 응답 그룹을 비즈니스용으로 닫은 날을 정의 하는 하나 이상의 공휴일 집합에 해당 하는 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-202">워크플로를 구성 하기 전에 휴일 및 휴일 집합을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="c8759-203"><STRONG>CsRgsHoliday</STRONG> 및 <STRONG>new-CsRgsHolidaySet</STRONG> cmdlet을 사용 하 여 휴일 및 휴일 집합을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="c8759-204">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(선택 사항) Lync Server 2013에서 응답 그룹 휴일 집합 정의</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="c8759-205">휴일에서 메시지를 재생 하려면 **공휴일 중 메시지 재생** 확인란을 선택한 후 다음 중 하나를 실행 하 여 재생할 메시지를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="c8759-206">메시지를 호출자의 음성으로 변환 되는 텍스트로 입력 하려면 **텍스트 음성 변환 사용**을 클릭 한 다음 텍스트 상자에 메시지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-207">입력 한 텍스트에 HTML 태그를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-207">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="c8759-208">HTML 태그를 포함 하면 오류 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-208">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="c8759-209">메시지에 오디오 파일 녹음/녹화를 사용 하려면 **기록 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-209">To use an audio file recording for the message, click **Select a recording**.</span></span> <span data-ttu-id="c8759-210">새 오디오 파일을 업로드 하려면 **기록** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-210">If you want to upload a new audio file, click the **a recording** link.</span></span> <span data-ttu-id="c8759-211">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-211">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="c8759-212">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-212">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-213">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="c8759-214">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="c8759-215">메시지가 재생 된 후 호출을 처리 하는 방법 지정 (메시지가 구성 된 경우):</span><span class="sxs-lookup"><span data-stu-id="c8759-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="c8759-216">통화 연결을 끊으려면 **통화 연결 끊기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="c8759-217">전화를 음성 메일로 착신 전환 하려면 **음성 메일로 전달을**클릭 한 다음 음성 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="c8759-218">음성 메일 주소의 형식은 사용자 \<이름\>@\<domainName\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="c8759-219">다른 사용자에 게 통화를 착신 전환 하려면 **SIP URI로 전달을**클릭 한 다음 사용자 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="c8759-220">사용자 주소의 형식은 \<username\>@\<domainName\>입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="c8759-221">통화를 다른 전화 번호로 착신 전환 하려면 **전화 번호로 전달을**클릭 한 다음 전화 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="c8759-222">전화 \<번호의 형식은 번호\>@\<의 이름\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="c8759-223">도메인 이름은 호출자를 올바른 대상으로 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="c8759-224">**6 단계에서 큐 구성**에서 전화를 **받을 큐를 선택**하 고 에이전트를 사용할 수 있게 될 때까지 호출자를 보관할 큐를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="c8759-225">**7 단계에서 음악을 보류할**때 다음 중 하나를 수행 하 여 에이전트를 기다리는 동안 호출자가 수신할 음악을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="c8759-226">기본 음악 보관 기록을 사용 하려면 **기본값 사용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="c8759-227">대기 중인 음악에 오디오 파일 녹음/녹화를 사용 하려면 **음악 파일 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-227">To use an audio file recording for the music on hold, click **Select a music file**.</span></span> <span data-ttu-id="c8759-228">새 오디오 파일을 업로드 하려면 **음악 파일** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-228">If you want to upload a new audio file, click the **a music file** link.</span></span> <span data-ttu-id="c8759-229">새 브라우저 창에서 **찾아보기를**클릭 하 고 사용할 파일을 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-229">In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**.</span></span> <span data-ttu-id="c8759-230">**업로드** 를 클릭 하 여 오디오 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-230">Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c8759-231">모든 사용자가 제공 하는 오디오 파일은 특정 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="c8759-232">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="c8759-233">**배포**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="c8759-234">Windows PowerShell을 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="c8759-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="c8759-235">RTCUniversalServerAdmins 그룹의 구성원 또는 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c8759-236">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c8759-237">환영 메시지에 대해 재생할 프롬프트를 만들고 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-237">Create the prompt to be played for the welcome message, and save it in a variable.</span></span> <span data-ttu-id="c8759-238">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-238">At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="c8759-239">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-240">프롬프트에 오디오 파일을 사용 하려면 <STRONG>CsRgsAudioFile</STRONG> cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="c8759-241">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">가져오기-CsRgsAudioFile</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="c8759-242">호출이 리디렉션되는 큐 또는 질문의 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="c8759-243">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="c8759-244">큐 만들기에 대 한 자세한 내용은 [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="c8759-245">업무 시간 동안 워크플로가 열려 있을 때 수행할 기본 작업을 정의 하 고 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-245">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable.</span></span> <span data-ttu-id="c8759-246">명령줄에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-246">At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-247">헌트 그룹 워크플로의 경우 기본 동작은 큐로 호출을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-247">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="c8759-248">이 매개 변수는 활성 워크플로에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-248">This is parameter is required for active workflows.</span></span> <span data-ttu-id="c8759-249">비활성 워크플로에는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-249">It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="c8759-250">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="c8759-251">비즈니스 시간 및 휴일을 정의 하려는 경우 워크플로를 만들거나 수정 하기 전에 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="c8759-252">자세한 내용은 [(선택 사항) Lync server 2013에서 응답 그룹 비즈니스 시간 정의](lync-server-2013-optional-define-response-group-business-hours.md) 및 [(선택 사항) lync Server 2013의 응답 그룹 휴일 집합을 정의](lync-server-2013-optional-define-response-group-holiday-sets.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="c8759-253">업무 시간 또는 휴일을 통해 받은 통화에 대 한 메시지를 표시 하려면 **CsRgsPrompt** cmdlet을 사용 하 여 프롬프트를 정의 하 고 **new-CsRgsCallAction** 를 사용 하 여 프롬프트 후 수행할 작업을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="c8759-254">자세한 내용은 [new-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 및 [new-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="c8759-255">Lync Server 응답 그룹 서비스의 서비스 이름을 검색 하 여 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="c8759-256">명령에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="c8759-257">워크플로를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-257">Create or modify the workflow.</span></span> <span data-ttu-id="c8759-258">워크플로를 만들려면 **New-CsRgsWorkflow**을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="c8759-259">워크플로를 수정 하려면 **Set-CsRgsWorkflow**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="c8759-260">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="c8759-261">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c8759-262">워크플로에 대해 지정 된 모든 사용자에 게 CsResponseGroupManager 역할을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8759-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8759-263">추가 선택적 매개 변수에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> 또는 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8759-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c8759-264">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8759-264">See Also</span></span>


[<span data-ttu-id="c8759-265">) Lync Server 2013에서 응답 그룹의 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="c8759-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="c8759-266">) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의</span><span class="sxs-lookup"><span data-stu-id="c8759-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="c8759-267">새로운 CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="c8759-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="c8759-268">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="c8759-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="c8759-269">새로운 CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="c8759-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="c8759-270">새로운 CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="c8759-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

