---
title: 'Lync Server 2013: 헌트 그룹 워크플로 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b4c7c07718faf93237dfe11357dc103bf77e9a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501685"
---
# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a><span data-ttu-id="1298b-102">Lync Server 2013에서 헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="1298b-102">Create or modify a hunt group workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1298b-103">_**마지막으로 수정 된 항목:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="1298b-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="1298b-104">다음 방법 중 하나를 사용하여 헌트 그룹 워크플로를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-104">Use one of the following procedures to create or modify a hunt group workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1298b-105">Lync Server 관리 셸 또는 응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify hunt group workflows.</span></span> <span data-ttu-id="1298b-106">Lync Server 제어판에서 응답 그룹 구성 도구에 액세스 하거나, 다음 URL: <STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>을 입력 하 여 웹 브라우저에서 페이지를 직접 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="1298b-107">응답 그룹 구성 도구를 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="1298b-107">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="1298b-108">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="1298b-109">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1298b-110">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1298b-111">왼쪽 탐색 모음에서 **응답 그룹**을 클릭하고 **워크플로**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="1298b-112">**워크플로** 페이지에서 **워크플로 만들기 또는 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="1298b-113">**서비스 선택** 검색 필드에 만들거나 변경할 워크플로를 호스팅하는 **ApplicationServer** 서비스의 이름 전부 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="1298b-114">서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-115">응답 그룹 구성 도구가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="1298b-116"><STRONG>Https://</STRONG> &lt; webpoolfqdn &gt; <STRONG>/RgsConfig</STRONG>URL을 입력 하 여 웹 브라우저에서 직접 응답 그룹 구성 도구를 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="1298b-117">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="1298b-118">**새 워크플로 만들기**의 헌트 그룹 옆에 있는 **만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-118">Under **Create a New Workflow**, next to **Hunt Group, click Create**.</span></span>
    
      - <span data-ttu-id="1298b-119">**기존 워크플로 관리**에서 변경할 워크플로를 찾은 다음 **동작**에서 **편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="1298b-120">사용자가 워크플로를 호출할 준비가 되면 **워크플로 활성화**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-120">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-p105">관리되는 워크플로를 만들어야 하는 경우 <STRONG>워크플로 활성화</STRONG>를 선택해야 합니다. 관리되는 활성 워크플로를 저장한 후에는 해당 워크플로를 수정하고 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="1298b-123">페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="1298b-124">또한 페더레이션에 대해 구성 된 응답 그룹 응용 프로그램에 적용 되는 외부 액세스 정책도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-125">전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="1298b-126">Lync Server 제어판을 사용 하거나 <STRONG>get-csexternalaccesspolicy</STRONG> cmdlet을 사용 하 여 Enableout access 매개 변수를 True로 설정 하 여 응답 그룹 페더레이션을 위한 전역 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="1298b-127">전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="1298b-128">따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="1298b-129">정책이 사용자에 게 적용 되는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Lync Server 2013에서 외부 액세스 정책 관리</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1298b-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="1298b-130">페더레이션 설정에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">get-csexternalaccesspolicy</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-130">For details about the federation setting, see <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-131">Lync Online에서 호스트 되는 사용자는 온-프레미스 배포에서 호스트 되는 응답 그룹에 대 한 호출을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="1298b-132">이는 하이브리드 배포와 온-프레미스 배포가 Lync Online 배포와 연결 된 경우 모두에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="1298b-133">통화하는 동안 에이전트의 ID를 숨기려면 **에이전트 익명성 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-134">통화가 연결된 후 에이전트 또는 발신자가 IM(인스턴트 메시징) 및 비디오를 추가할 수 있지만 IM 또는 비디오로 익명 통화를 시작할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-134">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="1298b-135">익명 에이전트는 통화를 보류하고, 전송(무조건 전송 및 협의 전송)하고, 대기시킨 후 재개할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-135">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="1298b-136">익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, 화이트보드 및 데이터 공동 작업, 통화 기록을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-136">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="1298b-137">Lync VDI 플러그 인을 사용 하는 에이전트는 들어오는 호출을 익명으로 받을 수 있지만 발신 전화를 익명으로 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-137">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="1298b-138">**전화를 받을 그룹의 주소를 입력하십시오**에 워크플로 호출에 응답할 그룹의 기본 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-139">워크플로의 기본 URI는 워크플로가 식별 및 참조되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-139">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="1298b-140">입력 한 SIP URI는 Active Directory 도메인 서비스에서 연락처 개체로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-140">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="1298b-141">URI를 만들려면 개체가 Active Directory에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-141">To create the URI, the object must be unique in Active Directory.</span></span>

    
    </div>

11. <span data-ttu-id="1298b-142">**표시 이름**에 워크플로에 대해 표시할 이름을 입력 합니다 (예: Sales Response 그룹).</span><span class="sxs-lookup"><span data-stu-id="1298b-142">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-143">&lt;표시 이름에 "" 또는 "" 문자를 포함 하지 마십시오 &gt; .</span><span class="sxs-lookup"><span data-stu-id="1298b-143">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="1298b-144"><STRONG>RGS Presence Watcher </STRONG> 또는 <STRONG>RGS Presence Watcher</STRONG>는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-144">Do not use the following display names because they are reserved: <STRONG>RGS Presence Watcher</STRONG> or <STRONG>Announcement Service</STRONG>.</span></span>

    
    </div>

12. <span data-ttu-id="1298b-145">**전화 번호**에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-145">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="1298b-146">**표시 이름**에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-146">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="1298b-147">반드시 **설명**에 Lync 클라이언트의 대화 상대 카드에 표시할 워크플로에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-147">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Lync client.</span></span>

15. <span data-ttu-id="1298b-148">이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형**에서 **관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-148">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="1298b-149">응답 그룹 관리자를 워크플로에 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-149">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="1298b-150">이 워크플로의 관리자 SIP URI를 입력하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-150">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>
    
    2.  <span data-ttu-id="1298b-151">워크플로에 추가할 다른 관리자의 SIP URI를 입력하고 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-151">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1298b-p113">응답 그룹의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p113">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="1298b-154">**2단계 언어 선택**에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-154">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="1298b-155">환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-155">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="1298b-156">환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-156">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-p114">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p114">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="1298b-p115">시작 메시지에 웨이브(.wav) 또는 Windows Media 오디오(.wma) 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p115">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-163">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-163">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="1298b-164">지원 되는 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1298b-164">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="1298b-165">**4단계 업무 시간 지정**의 **표준 시간대**에서 워크플로의 표준 시간대를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-165">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-p117">표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오후 11시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p117">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="1298b-171">다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-171">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="1298b-172">미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용**을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-172">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-173">이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-173">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="1298b-174"><STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet을 사용하여 미리 설정된 일정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-174">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="1298b-175">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Lync Server 2013에서 응답 그룹 업무 시간 정의</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1298b-175">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-176">미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 <STRONG>요일</STRONG>, <STRONG>시작</STRONG> 및 <STRONG>종료</STRONG>가 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-176">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="1298b-177">이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-177">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="1298b-178">이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-178">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="1298b-179">사용자 지정 일정을 만드는 경우 응답 그룹을 사용할 수 있는 주의 각 요일에 대해 **시작** 및 **종료** 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-179">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-p119"><STRONG>시작</STRONG> 및 <STRONG>종료</STRONG> 시간은 24시간 형식이어야 합니다. 예를 들어 평일 오전 9시에서 오후 5시까지 근무하고 12시부터 점심 시간 동안 문을 닫는 경우 업무 시간은 <STRONG>시작</STRONG> 9:00, <STRONG>종료</STRONG> 12:00, <STRONG>시작</STRONG> 13:00 및 <STRONG>종료</STRONG> 17:00로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p119">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="1298b-182">근무하지 않는 동안 메시지를 재생하려면 **응답 그룹의 업무 시간이 지났을 때 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-182">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="1298b-183">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-183">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-p120">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p120">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="1298b-p121">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p121">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-190">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-190">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="1298b-191">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1298b-191">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="1298b-192">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="1298b-192">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="1298b-193">통화 연결을 끊으려면 **전화 끊기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-193">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="1298b-194">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-194">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="1298b-195">음성 메일 주소 형식은 \<username\> @ \<domainName\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-195">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="1298b-196">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-196">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="1298b-197">사용자 주소 형식은 \<username\> @ \<domainName\> 입니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-197">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="1298b-198">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-198">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="1298b-199">전화 번호 형식은 \<number\> @ \<domainName\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-199">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="1298b-200">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-200">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="1298b-201">**5단계 휴일 지정** 아래에서 응답 그룹이 근무하지 않는 요일을 정의하는 하나 이상의 휴일 집합에 대한 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-201">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-202">워크플로를 구성하기 전에 휴일 및 휴일 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-202">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="1298b-203"><STRONG>New-CsRgsHoliday</STRONG> 및 <STRONG>New-CsRgsHolidaySet</STRONG> cmdlet을 사용하여 휴일 및 휴일 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-203">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="1298b-204">자세한 내용은 <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Lync Server 2013에서 응답 그룹 휴일 집합 정의</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-204">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="1298b-205">휴일에 메시지를 재생하려면 **휴일에 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 재생할 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-205">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="1298b-206">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용**을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-206">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-p127">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p127">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="1298b-p128">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p128">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-213">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-213">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="1298b-214">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1298b-214">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="1298b-215">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="1298b-215">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="1298b-216">통화 연결을 끊으려면 **전화 끊기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-216">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="1298b-217">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환**을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-217">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="1298b-218">음성 메일 주소 형식은 \<username\> @ \<domainName\> (예: bob@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-218">The format for the voice mail address is \<username\>@\<domainName\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="1298b-219">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환**을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-219">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="1298b-220">사용자 주소 형식은 \<username\> @ \<domainName\> 입니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-220">The format for the user address is \<username\>@\<domainName\>.</span></span>
    
      - <span data-ttu-id="1298b-221">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환**을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-221">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="1298b-222">전화 번호 형식은 \<number\> @ \<domainName\> (예: + 14255550121@contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-222">The format for the telephone number is \<number\>@\<domainName\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="1298b-223">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-223">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="1298b-224">**6단계 큐 구성**의 **전화를 받을 큐 선택**에서 에이전트가 사용 가능할 때까지 발신자를 대기 상태로 둘 큐를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-224">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="1298b-225">**7단계 대기 음악 구성**에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-225">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="1298b-226">기본 대기 음악 녹음을 사용하려면 **기본값 사용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-226">To use the default music-on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="1298b-p133">대기 음악에 오디오 파일 녹음을 사용하려면 **음악 파일 선택**을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기**를 클릭하고 사용할 파일을 선택한 다음 **열기**를 클릭합니다. **업로드**를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p133">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1298b-231">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-231">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="1298b-232">지원 되는 오디오 파일 형식에 대 한 자세한 내용은 <A href="lync-server-2013-technical-requirements-for-response-group.md">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1298b-232">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="1298b-233">**배포**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-233">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="1298b-234">Windows PowerShell을 사용 하 여 헌트 그룹 워크플로를 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="1298b-234">To use Windows PowerShell to create or modify a hunt group workflow</span></span>

1.  <span data-ttu-id="1298b-235">RTCUniversalServerAdmins 그룹의 구성원이 나 응답 그룹을 지 원하는 미리 정의 된 관리 역할 중 하나의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-235">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="1298b-236">**시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-236">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1298b-p135">시작 메시지로 재생할 프롬프트를 작성하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p135">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="1298b-239">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-239">For example:</span></span>
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-240">오디오 파일을 음성 안내에 사용하려면 <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-240">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="1298b-241">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">import-csrgsaudiofile</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-241">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="1298b-242">통화가 이동될 해당 큐 또는 질문의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-242">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="1298b-243">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-243">At the command line, run:</span></span>
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    <span data-ttu-id="1298b-244">큐를 만드는 방법에 대 한 자세한 내용은 [get-csrgsqueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-244">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).</span></span>

5.  <span data-ttu-id="1298b-p138">업무 시간 동안 워크플로를 열 때 수행할 기본 동작을 정의하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p138">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-p139">헌트 그룹 워크플로의 경우 기본적으로 통화를 큐로 이동해야 합니다. 이 매개 변수는 활성 워크플로에 필요합니다. 비활성 워크플로에는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-p139">For hunt group workflows, the default action must direct the call to a queue. This is parameter is required for active workflows. It is not required for inactive workflows.</span></span>

    
    </div>
    
    <span data-ttu-id="1298b-250">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-250">For example:</span></span>
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  <span data-ttu-id="1298b-251">업무 시간과 휴일을 정의하려는 경우 워크플로를 만들거나 수정하기 전에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-251">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="1298b-252">자세한 내용은 [(optional) lync server 2013에서 응답 그룹 업무 시간 정의](lync-server-2013-optional-define-response-group-business-hours.md) 및 [(선택 사항) lync Server 2013에서 응답 그룹 휴일 집합 정의](lync-server-2013-optional-define-response-group-holiday-sets.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-252">For details, see [(Optional) Define Response Group business hours in Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).</span></span>

7.  <span data-ttu-id="1298b-253">업무 시간 외나 휴일에 받는 통화에 대한 프롬프트를 만들려면 **New-CsRgsPrompt** cmdlet을 사용하여 프롬프트를 정의하고 **New-CsRgsCallAction**를 사용하여 프롬프트 후에 수행될 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-253">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="1298b-254">자세한 내용은 [new-csrgsprompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) 및 [new-csrgscallaction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-254">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).</span></span>

8.  <span data-ttu-id="1298b-255">Lync Server 응답 그룹 서비스에 대 한 서비스 이름을 검색 하 여 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-255">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="1298b-256">명령줄에 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-256">At the command, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  <span data-ttu-id="1298b-257">워크플로를 만들거나 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-257">Create or modify the workflow.</span></span> <span data-ttu-id="1298b-258">워크플로를 만들려면 **get-csrgsworkflow**을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-258">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="1298b-259">워크플로를 수정 하려면 **get-csrgsworkflow**를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-259">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="1298b-260">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-260">At the command line, type:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    <span data-ttu-id="1298b-261">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-261">For example:</span></span>
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1298b-262">워크플로의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1298b-262">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1298b-263">추가 선택적 매개 변수에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">get-csrgsworkflow</A> 또는 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">get-csrgsworkflow</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1298b-263">For details about additional optional parameters, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> or <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A></span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1298b-264">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1298b-264">See Also</span></span>


[<span data-ttu-id="1298b-265">반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="1298b-265">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[<span data-ttu-id="1298b-266">반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="1298b-266">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)  


[<span data-ttu-id="1298b-267">Get-csrgsworkflow</span><span class="sxs-lookup"><span data-stu-id="1298b-267">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[<span data-ttu-id="1298b-268">Get-csrgsworkflow</span><span class="sxs-lookup"><span data-stu-id="1298b-268">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[<span data-ttu-id="1298b-269">New-csrgsprompt</span><span class="sxs-lookup"><span data-stu-id="1298b-269">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="1298b-270">New-csrgscallaction</span><span class="sxs-lookup"><span data-stu-id="1298b-270">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

