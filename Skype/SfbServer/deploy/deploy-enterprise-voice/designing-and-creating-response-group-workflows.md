---
title: 비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: 비즈니스용 Skype 서버의 응답 그룹 워크플로를 디자인하고 Enterprise Voice. 헌트 그룹 워크플로와 대화형 워크플로에 모두 설명되어 있습니다.
ms.openlocfilehash: 3ebd5f2705547aa96a9ebfcc6857781ef25854b5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831038"
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business"></a><span data-ttu-id="d2a48-104">비즈니스용 Skype에서 응답 그룹 워크플로 디자인 및 만들기</span><span class="sxs-lookup"><span data-stu-id="d2a48-104">Designing and creating response group workflows in Skype for Business</span></span>

<span data-ttu-id="d2a48-105">비즈니스용 Skype 서버의 응답 그룹 워크플로를 디자인하고 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d2a48-105">Design and create Response Group workflows, in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="d2a48-106">헌트 그룹 워크플로와 대화형 워크플로에 모두 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-106">Both hunt group workflows and interactive workflows are covered.</span></span>

<span data-ttu-id="d2a48-107">워크플로는 전화가 울리는 시간부터 누군가가 전화를 받는 시간까지의 호출 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-107">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call.</span></span> <span data-ttu-id="d2a48-108">워크플로는 통화 대기에 사용할 큐를 지정하고 헌트 그룹 워크플로에 사용할 라우팅 방법이나 대화형 응답 그룹 워크플로에 사용할 질문과 대답을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-108">The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt group workflows or the questions and answers to use for interactive response group workflows.</span></span>

<span data-ttu-id="d2a48-109">또한 워크플로는 시작 메시지, 대기 음악, 업무 시간, 휴일 등의 설정도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-109">A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

> [!NOTE]
> <span data-ttu-id="d2a48-110">에이전트 그룹 및 큐를 먼저 만든 후에 해당 그룹과 큐를 사용하는 워크플로를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>

## <a name="creating-or-modifying-a-hunt-group-workflow"></a><span data-ttu-id="d2a48-111">헌트 그룹 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d2a48-111">Creating or modifying a hunt group workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="d2a48-112">응답 그룹 구성 도구를 사용하여 헌트 그룹 워크플로를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="d2a48-112">To use Response Group Configuration Tool to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="d2a48-113">RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="d2a48-114">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d2a48-115">왼쪽 탐색 모음에서 **응답 그룹** 을 클릭하고 **워크플로** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-115">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="d2a48-116">**워크플로** 페이지에서 **워크플로 만들기 또는 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-116">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="d2a48-117">**서비스 선택** 검색 필드에 만들거나 변경할 워크플로를 호스팅하는 **ApplicationServer** 서비스의 이름 전부 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-117">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or change.</span></span> <span data-ttu-id="d2a48-118">서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-118">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-119">응답 그룹 구성 도구가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-119">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="d2a48-120">/RgsConfig의 URL을 입력하여 웹 브라우저에서 직접 응답 그룹 구성 도구를 https:// \<webPoolFqdn\> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-120">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="d2a48-121">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-121">Do one of the following:</span></span>

   - <span data-ttu-id="d2a48-122">새 **워크플로 만들기 아래에서** 헌트 그룹 **옆의** 만들기를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-122">Under **Create a New Workflow**, next to **Hunt Group**, click **Create**.</span></span>

   - <span data-ttu-id="d2a48-123">**기존 워크플로 관리** 에서 변경할 워크플로를 찾은 다음 **동작** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-123">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="d2a48-124">사용자가 워크플로를 호출할 준비가 되면 **워크플로 활성화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-124">If you are ready for users to start calling the workflow, select **Activate the workflow**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d2a48-125">관리되는 워크플로를 만드는 경우 워크플로 활성화를 **선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-125">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="d2a48-126">활성화된 관리 워크플로를 저장한 후에는 이 워크플로를 수정하고 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-126">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="d2a48-127">페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-127">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="d2a48-128">또한 연결에 대해 구성된 응답 그룹 응용 프로그램에 적용되는 외부 액세스 정책이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-128">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-129">전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-129">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="d2a48-130">비즈니스용 Skype 서버 제어판을 사용하거나 **Set-CsExternalAccessPolicy** cmdlet을 사용하여 EnableOutsideAccess 매개 변수를 True로 설정하여 응답 그룹 페더ation에 대한 글로벌 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-130">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="d2a48-131">전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-131">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="d2a48-132">따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-132">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="d2a48-133">사용자에게 정책이 적용되는 방식에 대한 자세한 내용은 [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-133">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="d2a48-134">페더ation 설정에 대한 자세한 내용은 [Set-CsExternalAccessPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d2a48-134">For details about the federation setting, see [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-135">비즈니스용 Skype Online에서 호스팅된 사용자는온-프레미스 배포에서 호스트된 응답 그룹에 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-135">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="d2a48-136">이는 하이브리드 배포와 비즈니스용 Skype Online 배포와의 페더임이 있는 경우 모두 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-136">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="d2a48-137">통화하는 동안 에이전트의 ID를 숨기려면 **에이전트 익명성 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-137">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-138">통화가 연결된 후 에이전트 또는 발신자가 IM(인스턴트 메시징) 및 비디오를 추가할 수 있지만 IM 또는 비디오로 익명 통화를 시작할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-138">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="d2a48-139">익명 에이전트는 통화를 보류하고, 전송(무조건 전송 및 협의 전송)하고, 대기시킨 후 재개할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-139">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="d2a48-140">익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, 화이트보드 및 데이터 공동 작업, 통화 기록을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-140">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="d2a48-141">Lync VDI 플러그 인을 사용하는 에이전트는 수신 전화를 익명으로 받을 수 있지만 익명으로 발신 전화를 걸 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-141">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="d2a48-142">**전화를 받을 그룹의 주소를 입력하십시오** 에 워크플로 호출에 응답할 그룹의 기본 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-142">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-143">워크플로의 기본 URI는 워크플로가 식별 및 참조되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-143">The primary URI for a workflow is how the workflow is identified and referenced.</span></span> <span data-ttu-id="d2a48-144">입력하는 SIP URI는 Active Directory 도메인 서비스에서 연락처 개체로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-144">The SIP URI that you enter is created as a contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="d2a48-145">URI를 만들 경우 개체는 Active Directory에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-145">To create the URI, the object must be unique in Active Directory.</span></span>

11. <span data-ttu-id="d2a48-146">표시 **이름에** 워크플로에 대해 표시할 이름(예: 영업 응답 그룹)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-146">In **Display name**, type the name that you want to display for the workflow (for example, Sales Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p112">"<" 또는 ">" 문자를 표시 이름에 포함하지 마십시오. **RGS Presence Watcher** 또는 **RGS Presence Watcher** 는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p112">Do not include the "<" or ">" characters in the display name. Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="d2a48-149">**전화 번호** 에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-149">Under **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="d2a48-150">**표시 이름** 에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-150">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="d2a48-151">(선택 사항) **설명에서** 워크플로에 대한 설명을 비즈니스용 Skype의 연락처 카드에 표시하려는 경우 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-151">(Optional) In **Description**, type a description for the workflow as you want it to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="d2a48-152">이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형** 에서 **관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-152">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="d2a48-153">워크플로에 응답 그룹 관리자를 할당하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-153">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="d2a48-154">a.</span><span class="sxs-lookup"><span data-stu-id="d2a48-154">a.</span></span> <span data-ttu-id="d2a48-155">이 워크플로의 관리자 SIP URI를 입력하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-155">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="d2a48-156">b.</span><span class="sxs-lookup"><span data-stu-id="d2a48-156">b.</span></span> <span data-ttu-id="d2a48-157">워크플로에 추가할 다른 관리자의 SIP URI를 입력하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-157">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d2a48-p116">응답 그룹의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p116">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="d2a48-160">**2단계 언어 선택** 에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-160">Under **Step 2 Select a Language**, click the language that you want to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="d2a48-161">환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-161">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="d2a48-162">환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-162">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p117">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p117">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="d2a48-p118">시작 메시지에 웨이브(.wav) 또는 Windows Media 오디오(.wma) 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p118">To use a wave (.wav) or Windows Media audio (.wma) file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-169">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-169">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-170">지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-170">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="d2a48-171">**4단계 업무 시간 지정** 의 **표준 시간대** 에서 워크플로의 표준 시간대를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-171">Under **Step 4 Specify Your Business Hours**, in **Your time zone**, click the time zone for the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p120">표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오후 11시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p120">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 23:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="d2a48-177">다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-177">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-178">미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용** 을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-178">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-179">이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-179">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="d2a48-180">**New-CSRgsHoursOfBusiness** cmdlet을 사용하여 미리 설정된 일정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-180">You define preset schedules by using the **New-CSRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="d2a48-181">자세한 내용은 비즈니스용 Skype에서 응답 그룹 업무 시간 정의(선택 [사항)를 참조하세요.](optional-define-response-group-business-hours.md)</span><span class="sxs-lookup"><span data-stu-id="d2a48-181">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-182">미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 **요일**, **시작** 및 **종료** 가 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-182">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="d2a48-183">이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-183">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="d2a48-184">이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-184">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="d2a48-185">사용자 지정 일정을 만드는 경우  응답  그룹을 사용할 수 있는 각 주에 대한 열기 및 닫기 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-185">If you are creating a custom schedule, type the **Open** and **Close** hours for each day of the week that the response group is available.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p122">**시작** 및 **종료** 시간은 24시간 형식이어야 합니다. 예를 들어 평일 오전 9시에서 오후 5시까지 근무하고 12시부터 점심 시간 동안 문을 닫는 경우 업무 시간은 **시작** 9:00, **종료** 12:00, **시작** 13:00 및 **종료** 17:00로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p122">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="d2a48-188">근무하지 않는 동안 메시지를 재생하려면 **응답 그룹의 업무 시간이 지났을 때 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-188">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-189">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-189">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-p123">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p123">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="d2a48-p124">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p124">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-196">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-196">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-197">지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-197">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="d2a48-198">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="d2a48-198">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="d2a48-199">통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-199">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="d2a48-200">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-200">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="d2a48-201">음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainName\>* 같습니다(예: bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-201">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="d2a48-202">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-202">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="d2a48-203">사용자 주소의 형식은 _\<username\>_ @ _\<domainName\>_ .</span><span class="sxs-lookup"><span data-stu-id="d2a48-203">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="d2a48-204">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-204">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="d2a48-205">전화 번호 형식은 *\<number\>* @ *\<domainName\>* +14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-205">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="d2a48-206">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-206">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="d2a48-207">**5단계 휴일 지정** 아래에서 응답 그룹이 근무하지 않는 요일을 정의하는 하나 이상의 휴일 집합에 대한 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-207">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-208">워크플로를 구성하기 전에 휴일 및 휴일 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-208">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="d2a48-209">**New-CsRgsHoliday** 및 **New-CsRgsHolidaySet** cmdlet을 사용하여 휴일 및 휴일 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-209">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="d2a48-210">자세한 내용은 비즈니스용 Skype에서 응답 그룹 휴일 집합 정의(선택 [사항)를 참조하세요.](optional-define-response-group-holiday-sets.md)</span><span class="sxs-lookup"><span data-stu-id="d2a48-210">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="d2a48-211">휴일에 메시지를 재생하려면 **휴일에 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 재생할 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-211">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-212">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-212">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p130">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p130">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="d2a48-p131">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p131">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-219">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-219">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-220">지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-220">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="d2a48-221">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="d2a48-221">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="d2a48-222">통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-222">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="d2a48-223">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-223">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="d2a48-224">음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainName\>* 같습니다(예: bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-224">The format for the voice mail address is  *\<username\>*@*\<domainName\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="d2a48-225">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-225">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="d2a48-226">사용자 주소의 형식은 _\<username\>_ @ _\<domainName\>_ .</span><span class="sxs-lookup"><span data-stu-id="d2a48-226">The format for the user address is  _\<username\>_@_\<domainName\>_.</span></span>

    - <span data-ttu-id="d2a48-227">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-227">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="d2a48-228">전화 번호 형식은 *\<number\>* @ *\<domainName\>* +14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-228">The format for the telephone number is  *\<number\>*@*\<domainName\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="d2a48-229">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-229">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="d2a48-230">**6단계 큐 구성** 의 **전화를 받을 큐 선택** 에서 에이전트가 사용 가능할 때까지 발신자를 대기 상태로 둘 큐를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-230">Under **Step 6 Configure a Queue**, in **Select the queue that will receive the calls**, select the queue that you want to hold callers until an agent becomes available.</span></span>

28. <span data-ttu-id="d2a48-231">**7단계 대기 음악 구성** 에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-231">Under **Step 7 Configure Music on Hold**, choose the music you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-232">기본 대기 음악 녹음을 사용하려면 **기본값 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-232">To use the default music-on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="d2a48-p136">대기 음악에 오디오 파일 녹음을 사용하려면 **음악 파일 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p136">To use an audio file recording for the music on hold, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-237">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-237">All user provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-238">지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-238">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="d2a48-239">**배포** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-239">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a><span data-ttu-id="d2a48-240">비즈니스용 Skype 서버 관리 셸을 사용하여 헌트 그룹 워크플로를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="d2a48-240">To use Skype for Business Server Management Shell to create or modify a hunt group workflow</span></span>

1. <span data-ttu-id="d2a48-241">RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-241">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="d2a48-242">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-242">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="d2a48-p138">시작 메시지로 재생할 프롬프트를 작성하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p138">Create the prompt to be played for the welcome message, and save it in a variable. At the command line, run:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    <span data-ttu-id="d2a48-245">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-245">For example:</span></span>

   ```powershell
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > <span data-ttu-id="d2a48-246">오디오 파일을 음성 안내에 사용하려면 **Import-CsRgsAudioFile** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-246">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="d2a48-247">자세한 내용은 [Import-CsRgsAudioFile을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d2a48-247">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span>

4. <span data-ttu-id="d2a48-248">통화가 이동될 해당 큐 또는 질문의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-248">Get the identity of the queue or question where the calls will be directed.</span></span> <span data-ttu-id="d2a48-249">명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-249">At the command line, run:</span></span>

   ```powershell
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    <span data-ttu-id="d2a48-250">큐를 만드는 데 대한 자세한 내용은 [New-CsRgsQueue를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d2a48-250">For details about creating the queue, see [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).</span></span>

5. <span data-ttu-id="d2a48-p141">업무 시간 동안 워크플로를 열 때 수행할 기본 동작을 정의하여 변수에 저장합니다. 명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p141">Define the default action to be taken when a workflow is opened during business hours, and save it in a variable. At the command line, run:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > <span data-ttu-id="d2a48-253">헌트 그룹 워크플로의 경우 기본적으로 통화를 큐로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-253">For hunt group workflows, the default action must direct the call to a queue.</span></span> <span data-ttu-id="d2a48-254">이 매개 변수는 활성 워크플로에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-254">This parameter is required for active workflows.</span></span> <span data-ttu-id="d2a48-255">비활성 워크플로에는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-255">It is not required for inactive workflows.</span></span>

    <span data-ttu-id="d2a48-256">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-256">For example:</span></span>

   ```powershell
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. <span data-ttu-id="d2a48-257">업무 시간과 휴일을 정의하려는 경우 워크플로를 만들거나 수정하기 전에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-257">If you want to define business hours and holidays, you need to create them before you create or modify the workflow.</span></span> <span data-ttu-id="d2a48-258">자세한 내용은 [(선택 사항)](optional-define-response-group-business-hours.md) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의 및 (선택 사항) 비즈니스용 Skype에서 응답 그룹 휴일 집합 [정의를 참조하세요.](optional-define-response-group-holiday-sets.md)</span><span class="sxs-lookup"><span data-stu-id="d2a48-258">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md) and [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

7. <span data-ttu-id="d2a48-259">업무 시간 외나 휴일에 받는 통화에 대한 프롬프트를 만들려면 **New-CsRgsPrompt** cmdlet을 사용하여 프롬프트를 정의하고 **New-CsRgsCallAction** 를 사용하여 프롬프트 후에 수행될 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-259">If you want to have prompts for calls that are received out of business hours or on holidays, use the **New-CsRgsPrompt** cmdlet to define the prompt, and use the **New-CsRgsCallAction** to define the action to be taken after the prompt.</span></span> <span data-ttu-id="d2a48-260">자세한 내용은 [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) 및 [New-CsRgsCallAction을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d2a48-260">For details, see [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) and [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span>

8. <span data-ttu-id="d2a48-261">Lync Server 응답 그룹 서비스의 서비스 이름을 검색하여 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-261">Retrieve the service name for the Lync Server Response Group service and assign it to a variable.</span></span> <span data-ttu-id="d2a48-262">명령줄에 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-262">At the command, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. <span data-ttu-id="d2a48-263">워크플로를 만들거나 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-263">Create or modify the workflow.</span></span> <span data-ttu-id="d2a48-264">워크플로를 만들 경우 **New-CsRgsWorkflow를 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-264">To create a workflow, use **New-CsRgsWorkflow**.</span></span> <span data-ttu-id="d2a48-265">워크플로를 수정하려면 **Set-CsRgsWorkflow를 사용하세요.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-265">To modify a workflow, use **Set-CsRgsWorkflow**.</span></span> <span data-ttu-id="d2a48-266">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-266">At the command line, type:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-ManagersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    <span data-ttu-id="d2a48-267">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-267">For example:</span></span>

   ```powershell
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > <span data-ttu-id="d2a48-268">워크플로의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-268">All users who are designated managers for workflows must be assigned the CsResponseGroupManager role.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d2a48-269">추가 선택적 매개 변수에 대한 자세한 내용은 [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) 또는 [Set-CsRgsWorkflow를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d2a48-269">For details about additional optional parameters, see [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) or [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)</span></span>

## <a name="designing-an-interactive-workflow"></a><span data-ttu-id="d2a48-270">대화형 워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="d2a48-270">Designing an interactive workflow</span></span>

<span data-ttu-id="d2a48-271">IVR(대화형 음성 응답)을 사용하여 발신자로부터 정보를 획득하고 통화를 적절한 큐로 안내할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-271">You can use interactive voice response (IVR) to obtain information from callers and direct the call to the appropriate queue.</span></span> <span data-ttu-id="d2a48-272">질문 및 응답 쌍은 사용할 큐를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-272">Question-and-answer pairs determine which queue to use.</span></span> <span data-ttu-id="d2a48-273">발신자 응답에 따라 발신자에 대한 후속 질문을 듣거나 적절한 큐로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-273">Depending on the caller's response, the caller either hears a follow-up question, or is routed to the appropriate queue.</span></span> <span data-ttu-id="d2a48-274">IVR 질문과 발신자 응답은 통화를 수락하는 응답 에이전트에게 제공함으로써 에이전트에게 중요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-274">The IVR questions and the caller's responses are provided to the responding agent who accepts the call, providing valuable information to the agent.</span></span>

### <a name="overview-of-ivr-features"></a><span data-ttu-id="d2a48-275">IVR 기능 개요</span><span class="sxs-lookup"><span data-stu-id="d2a48-275">Overview of IVR Features</span></span>

<span data-ttu-id="d2a48-276">응답 그룹 응용 프로그램은 26개 언어로 음성 인식 및 텍스트 음성 음성 입력 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-276">The Response Group application offers speech recognition and text-to-speech capabilities in 26 languages.</span></span> <span data-ttu-id="d2a48-277">텍스트 음성 또는 웨이브(.wav) 또는 Windows Media 오디오(.wma) 파일을 사용하여 IVR 질문을 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-277">You can enter IVR questions using text-to-speech or a wave (.wav) or Windows Media audio (.wma) file.</span></span> <span data-ttu-id="d2a48-278">발신자는 음성 또는 DTMF(Dual-Tone Multifrequency) 응답을 사용하여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-278">Callers can respond by using voice or dual-tone multifrequency (DTMF) responses.</span></span>

<span data-ttu-id="d2a48-279">대화형 워크플로는 최대 두 가지 수준의 질문을 지원하며, 각 질문에는 최대 4개의 가능한 응답이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-279">Interactive workflows support up to two levels of questions, with each question having up to four possible answers.</span></span> <span data-ttu-id="d2a48-280">IVR은 발신자에게 질문을 한 다음 발신자 응답에 따라 발신자 통화를 큐로 라우팅하거나 두 번째 질문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-280">The IVR asks the caller a question, and depending on the caller's response, routes the caller to a queue or asks a second question.</span></span> <span data-ttu-id="d2a48-281">두 번째 질문 역시 가능한 응답은 4개입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-281">The second question can also have four possible answers.</span></span> <span data-ttu-id="d2a48-282">두 번째 수준의 질문에 대한 응답에 따라 적합한 큐로 발신자가 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-282">Depending on the answer to the second-level question, the caller is routed to the appropriate queue.</span></span>

> [!NOTE]
> <span data-ttu-id="d2a48-283">비즈니스용 Skype 서버 관리 셸을 사용하여 통화 흐름을 디자인할 때 IVR 질문 수준과 답변 수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-283">When you design call flows by using Skype for Business Server Management Shell, you can define any number of levels of IVR questions and any number of answers.</span></span> <span data-ttu-id="d2a48-284">그러나 발신자 사용성을 위해 질문 수준이 3개 이상인 경우 각각 5개 이상의 답변을 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-284">However, for caller usability, we recommend that you not use more than three levels of questions, with not more than five answers each.</span></span> <span data-ttu-id="d2a48-285">또한 각각 4개 이상의 응답이 있는 두 개 이상의 질문 수준이 있는 통화 흐름을 디자인하는 경우 비즈니스용 Skype 서버 제어판을 사용하여 통화 흐름을 편집할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-285">In addition, if you design a call flow that has more than two levels of questions with more than four answers each, you cannot edit the call flow by using Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="d2a48-286">IVR 질문과 발신자 응답은 통화를 수락하는 응답 에이전트에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-286">The IVR questions and the caller's responses are provided to the responding agent who accepts the call.</span></span>

### <a name="working-with-speech-technologies"></a><span data-ttu-id="d2a48-287">음성 기술 작업</span><span class="sxs-lookup"><span data-stu-id="d2a48-287">Working with Speech Technologies</span></span>

<span data-ttu-id="d2a48-288">음성 인식 및 텍스트 음성 음성과 같은 음성 기술은 고객 환경을 향상하고 사람들이 정보에 보다 자연스럽고 효과적으로 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-288">Speech technologies, such as speech recognition and text-to-speech, can enhance customer experience and let people access information more naturally and effectively.</span></span> <span data-ttu-id="d2a48-289">그러나 음성 엔진에서 지정한 텍스트 또는 사용자 음성 응답이 올바르게 인식되지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-289">However, there can be cases where the specified text or the user voice response is not recognized correctly by the speech engine.</span></span> <span data-ttu-id="d2a48-290">예를 들어 "#" 기호는 텍스트 음성 변환 엔진에서 단어 "number"로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-290">For example, the "#" symbol is translated by the text-to-speech engine as the word "number."</span></span> <span data-ttu-id="d2a48-291">이 문제는 다음을 통해 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-291">This issue can be mitigated by the following:</span></span>

- <span data-ttu-id="d2a48-292">음성 엔진은 발신자에 대한 5회의 질문에 응답할 수 있는 시도를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-292">The speech engine gives the caller five attempts to answer the question.</span></span> <span data-ttu-id="d2a48-293">발신자에서 질문에 잘못 응답하거나(즉, 응답이 지정된 응답 중 하나에 해당되지 않은 경우) 답변을 제공하지 않으면 발신자도 질문에 응답할 수 있는 기회를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-293">If the caller answers the question incorrectly (that is, the answer is not one of the specified responses) or does not provide an answer at all, the caller gets another chance to answer the question.</span></span> <span data-ttu-id="d2a48-294">발신자 연결이 끊어지기 전에 다섯 번의 시도로 질문에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-294">The caller has five attempts to answer the question before being disconnected.</span></span> <span data-ttu-id="d2a48-295">각 발신자 오류 후 사용자 지정된 메시지를 재생하도록 IVR을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-295">You can configure the IVR to play a customized message after each caller error.</span></span> <span data-ttu-id="d2a48-296">질문은 매번 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-296">The question is repeated each time.</span></span>

- <span data-ttu-id="d2a48-297">음성 엔진이 주변 잡음이 응답으로 해석될 가능성을 최소화하기 위해 더 긴 응답을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-297">To minimize the potential for ambient noise to be interpreted by the speech engine as a response, use longer responses.</span></span> <span data-ttu-id="d2a48-298">예를 들어 응답에는 음소가 두 개 이상 있으며 서로 크게 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-298">For example, responses should have more than one syllable and should sound significantly different from each other.</span></span>

- <span data-ttu-id="d2a48-299">질문에 음성 응답과 DTMF 응답이 모두 있는 경우 DTMF 응답이 아닌 개념을 나타내는 단어로 음성 응답을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-299">If your questions have both speech and DTMF responses, configure the speech responses with words that represent the concept rather than the DTMF response.</span></span> <span data-ttu-id="d2a48-300">예를 들어 "누르거나 말하기"를 사용하는 대신 "1을 누르거나 대금 청구를 말하세요."를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-300">For example, instead of using "Press or say one" use "Press 1 or say billing."</span></span>

- <span data-ttu-id="d2a48-301">IVR을 디자인한 후 워크플로를 호출하고, 음성을 듣고, 음성을 사용하여 각 프롬프트에 응답하고, IVR 소리가 예상대로 실행되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-301">After you design your IVR, call the workflow, listen to the prompts, respond to each of the prompts using voice, and verify that the IVR sounds and behaves as expected.</span></span> <span data-ttu-id="d2a48-302">그런 다음 IVR을 수정하여 해석 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-302">You can then modify the IVR to fix any interpretation issues.</span></span> <span data-ttu-id="d2a48-303">이전 예제에 따라 # 키를 참조해야 하는 경우 # 기호 대신 키 이름을 사용하여 IVR 프롬프트를 다시 덮어 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-303">Following the previous example, if you need to refer to the # key, you can rewrite your IVR prompt to use the key name, rather than the # symbol.</span></span> <span data-ttu-id="d2a48-304">예를 들어 "영업과 대화를 하다가 파운드 키를 누르고 있습니다."를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-304">For example, "To talk to sales, press the pound key."</span></span>

### <a name="ivr-design-examples"></a><span data-ttu-id="d2a48-305">IVR 디자인 예제</span><span class="sxs-lookup"><span data-stu-id="d2a48-305">IVR Design Examples</span></span>

<span data-ttu-id="d2a48-306">다음 섹션에는 서로 다른 IVR 시나리오와 질문 및 응답 쌍의 예가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-306">The following sections contain examples of different IVR scenarios and question-and-answer pairs.</span></span>

#### <a name="ivr-with-one-level-of-questions"></a><span data-ttu-id="d2a48-307">한 가지 수준의 질문이 있는 IVR</span><span class="sxs-lookup"><span data-stu-id="d2a48-307">IVR with One Level of Questions</span></span>

<span data-ttu-id="d2a48-308">다음 예제에서는 한 가지 수준의 질문을 사용하는 IVR을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-308">The following example shows an IVR that uses one level of questions.</span></span> <span data-ttu-id="d2a48-309">음성 인식을 사용하여 발신자 응답을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-309">It uses speech recognition to detect the caller's response.</span></span>

 <span data-ttu-id="d2a48-310">**질문:** "인사부에 문의해 주셔서 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-310">**Question:** "Thank you for calling Human Resources.</span></span> <span data-ttu-id="d2a48-311">급여에 대해 말하고자 하는 경우 급여라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-311">If you would like to speak to payroll, say payroll.</span></span> <span data-ttu-id="d2a48-312">그렇지 않으면 HR라고 말하면 됩니다."</span><span class="sxs-lookup"><span data-stu-id="d2a48-312">Otherwise, say HR."</span></span>

- <span data-ttu-id="d2a48-313">**옵션 1이 선택되어 있습니다.** 발신이 급여 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-313">**Option 1 is selected:** The caller is routed to the payroll team.</span></span>

- <span data-ttu-id="d2a48-314">**옵션 2가 선택되어 있습니다.** 발신이 인사 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-314">**Option 2 is selected:** The caller is routed to the human resources team.</span></span>

<span data-ttu-id="d2a48-315">다음 그림에서는 통화 흐름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-315">The following figure shows the call flow.</span></span>

 <span data-ttu-id="d2a48-316">**1 수준 대화형 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="d2a48-316">**One-level interactive call flow**</span></span>

![대화형 음성 리포지티브를 사용하여 통화 흐름 디자인](../../media/Ops_OCS_RGS_IVRLevel1.jpg)

#### <a name="ivr-with-two-levels-of-questions"></a><span data-ttu-id="d2a48-318">두 가지 수준의 질문이 있는 IVR</span><span class="sxs-lookup"><span data-stu-id="d2a48-318">IVR with Two Levels of Questions</span></span>

<span data-ttu-id="d2a48-319">다음 예에서는 두 가지 수준의 질문을 사용하는 IVR을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-319">The following example shows an IVR that uses two levels of questions.</span></span> <span data-ttu-id="d2a48-320">발신자는 음성 또는 DTMF 키패드 입력을 사용하여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-320">It allows callers to respond using either speech or DTMF keypad input.</span></span>

 <span data-ttu-id="d2a48-321">**질문:** "IT 지원 센터에 문의해 주셔서 감사합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-321">**Question:** "Thank you for calling the IT Help Desk.</span></span> <span data-ttu-id="d2a48-322">네트워크 액세스 문제가 있는 경우 1을 누르거나 네트워크를 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-322">If you have a network access problem, press 1 or say network.</span></span> <span data-ttu-id="d2a48-323">소프트웨어 문제가 있는 경우 2를 누르거나 소프트웨어를 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-323">If you have a software problem, press 2 or say software.</span></span> <span data-ttu-id="d2a48-324">하드웨어 문제가 있는 경우 3을 누르거나 하드웨어라고 말하십시오."</span><span class="sxs-lookup"><span data-stu-id="d2a48-324">If you have a hardware problem, press 3 or say hardware."</span></span>

- <span data-ttu-id="d2a48-325">**옵션 1이 선택되어 있습니다.** 발신자 경로가 네트워크 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-325">**Option 1 is selected:** The caller is routed to the network support team.</span></span>

- <span data-ttu-id="d2a48-326">**옵션 2가 선택되어 있습니다.** 발신자에 후속 질문을 묻는 질문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-326">**Option 2 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="d2a48-327">**질문:** "운영 체제 문제인 경우 1을 누르거나 운영 체제를 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-327">**Question:** "If this is an operating system problem, press 1 or say operating system.</span></span> <span data-ttu-id="d2a48-328">내부 응용 프로그램에 문제가 있는 경우 2를 누르거나 내부 응용 프로그램을 말하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-328">If this is a problem with an internal application, press 2 or say internal application.</span></span> <span data-ttu-id="d2a48-329">그렇지 않으면 3을 누르거나 다른 말로 말해야 합니다."</span><span class="sxs-lookup"><span data-stu-id="d2a48-329">Otherwise, press 3 or say other."</span></span>

  - <span data-ttu-id="d2a48-330">**옵션 1이 선택되어 있습니다.** 발신이 운영 체제 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-330">**Option 1 is selected:** The caller is routed to the operating systems support team.</span></span>

  - <span data-ttu-id="d2a48-331">**옵션 2가 선택되어 있습니다.** 발신자 라우팅은 내부 응용 프로그램 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-331">**Option 2 is selected:** The caller is routed to the internal applications support team.</span></span>

  - <span data-ttu-id="d2a48-332">**옵션 3이 선택되어 있습니다.** 발신자 경로가 소프트웨어 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-332">**Option 3 is selected:** The caller is routed to the software support team.</span></span>

- <span data-ttu-id="d2a48-333">**옵션 3이 선택되어 있습니다.** 발신자에 후속 질문을 묻는 질문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-333">**Option 3 is selected:** The caller is asked a follow-up question:</span></span>

    <span data-ttu-id="d2a48-334">**질문:** "프린터 문제인 경우 1을 누르십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-334">**Question:** "If this is a printer problem press 1.</span></span> <span data-ttu-id="d2a48-335">그렇지 않으면 2를 누르고 있습니다."</span><span class="sxs-lookup"><span data-stu-id="d2a48-335">Otherwise, press 2."</span></span>

  - <span data-ttu-id="d2a48-336">**옵션 1이 선택되어 있습니다.** 발신자 경로가 프린터 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-336">**Option 1 is selected:** The caller is routed to the printer support team.</span></span>

  - <span data-ttu-id="d2a48-337">**옵션 2가 선택되어 있습니다.** 발신자 경로는 하드웨어 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-337">**Option 2 is selected:** The caller is routed to the hardware support team.</span></span>

<span data-ttu-id="d2a48-338">다음 그림에서는 통화 흐름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-338">The following figure shows the call flow.</span></span>

 <span data-ttu-id="d2a48-339">**두 수준 대화형 통화 흐름**</span><span class="sxs-lookup"><span data-stu-id="d2a48-339">**Two-level interactive call flow**</span></span>

![대화형 음성 리포지티브를 사용하여 통화 흐름 디자인](../../media/Ops_OCS_RGS_IVRLevel2.jpg)

### <a name="best-practices"></a><span data-ttu-id="d2a48-341">모범 사례</span><span class="sxs-lookup"><span data-stu-id="d2a48-341">Best Practices</span></span>

<span data-ttu-id="d2a48-342">다음 목록에서는 IVR을 디자인하기 위한 몇 가지 모범 사례를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-342">The following list describes some best practices for designing your IVR:</span></span>

- <span data-ttu-id="d2a48-343">발신자에 대한 작업을 빠르게 할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-343">Let the caller get to the task quickly.</span></span> <span data-ttu-id="d2a48-344">IVR에 너무 많은 정보나 긴 마케팅 메시지를 제공하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-344">Avoid providing too much information or lengthy marketing messages in your IVR.</span></span>

- <span data-ttu-id="d2a48-345">긴 메시지를 포함하려는 경우 환영 메시지 대신 첫 번째 질문에 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-345">If you want to include a lengthy message, consider appending it to the first question instead of to the welcome message.</span></span> <span data-ttu-id="d2a48-346">첫 번째 질문의 일부인 경우 발신자는 질문에 응답하여 메시지를 무시할 수 있지만 환영 메시지를 무시할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-346">Callers can bypass the message if it is part of the first question by answering the question, but they cannot bypass the welcome message.</span></span>

- <span data-ttu-id="d2a48-347">발신자 언어로 말하기</span><span class="sxs-lookup"><span data-stu-id="d2a48-347">Speak in the caller's language.</span></span> <span data-ttu-id="d2a48-348">정체된 언어를 피합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-348">Avoid stilted language.</span></span> <span data-ttu-id="d2a48-349">자연스럽게 말하기</span><span class="sxs-lookup"><span data-stu-id="d2a48-349">Speak naturally.</span></span>

- <span data-ttu-id="d2a48-350">효율적이고 효과적인 프롬프트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-350">Write efficient and effective prompts.</span></span> <span data-ttu-id="d2a48-351">불필요한 옵션을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-351">Remove any unnecessary options.</span></span> <span data-ttu-id="d2a48-352">발신자 예상 응답이 문장의 끝에 오게 정보를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-352">Structure the information so that the caller's expected response is at the end of the sentence.</span></span> <span data-ttu-id="d2a48-353">예를 들어 "영업 팀에 말하기 위해 1을 누르고 있습니다."를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-353">For example, "To speak to the sales team, press 1."</span></span>

- <span data-ttu-id="d2a48-354">음성 응답을 사용자에게 친숙하게 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-354">Make voice responses user friendly.</span></span> <span data-ttu-id="d2a48-355">예를 들어 DTMF와 음성 응답을 모두 지정하는 경우 "영업 팀에 말하기 위해 1을 누르거나 판매를 말하기"를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-355">For example, if you specify both DTMF and voice responses, use something like: "To speak to the sales team, press 1 or say sales."</span></span>

- <span data-ttu-id="d2a48-356">조직에 배포하기 전에 사용자 그룹에서 IVR을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-356">Test the IVR on a group of users before you deploy it across your organization.</span></span>

## <a name="creating-or-modifying-an-interactive-workflow"></a><span data-ttu-id="d2a48-357">대화형 워크플로 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d2a48-357">Creating or modifying an interactive workflow</span></span>

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="d2a48-358">응답 그룹 구성 도구를 사용하여 대화형 워크플로를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="d2a48-358">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1. <span data-ttu-id="d2a48-359">RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-359">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="d2a48-360">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-360">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d2a48-361">왼쪽 탐색 모음에서 **응답 그룹** 을 클릭하고 **워크플로** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-361">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4. <span data-ttu-id="d2a48-362">**워크플로** 페이지에서 **워크플로 만들기 또는 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-362">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5. <span data-ttu-id="d2a48-363">서비스 **선택** 검색 필드에 만들거나 수정할 워크플로를 호스팅하는 **ApplicationServer** 서비스의 이름 전체 또는 일부를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-363">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="d2a48-364">서비스 결과 목록에서 원하는 서비스를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-364">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-365">응답 그룹 구성 도구가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-365">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="d2a48-366">/RgsConfig의 URL을 입력하여 웹 브라우저에서 직접 응답 그룹 구성 도구를 https:// \<webPoolFqdn\> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-366">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: https://\<webPoolFqdn\>/RgsConfig.</span></span>

6. <span data-ttu-id="d2a48-367">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-367">Do one of the following:</span></span>

   - <span data-ttu-id="d2a48-368">**새 워크플로 만들기** 아래에서 **대화형** 옆에 있는 **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-368">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>

   - <span data-ttu-id="d2a48-369">**기존 워크플로 관리** 에서 변경할 워크플로를 찾은 다음 **동작** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-369">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7. <span data-ttu-id="d2a48-370">사용자가 워크플로 호출을 시작할 수 있도록 준비되지 않은 경우 **워크플로 활성화** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-370">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d2a48-371">관리되는 워크플로를 만드는 경우 워크플로 활성화를 **선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-371">If you are creating a managed workflow, you need to select **Activate the workflow**.</span></span> <span data-ttu-id="d2a48-372">활성화된 관리 워크플로를 저장한 후에는 이 워크플로를 수정하고 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-372">After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

8. <span data-ttu-id="d2a48-373">페더레이션 사용자가 그룹을 호출할 수 있도록 허용하려면 **페더레이션 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-373">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="d2a48-374">또한 연결에 대해 구성된 응답 그룹 응용 프로그램에 적용되는 외부 액세스 정책이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-374">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-375">전역 외부 액세스 정책은 응답 그룹 응용 프로그램에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-375">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="d2a48-376">비즈니스용 Skype 서버 제어판을 사용하거나 **Set-CsExternalAccessPolicy** cmdlet을 사용하여 EnableOutsideAccess 매개 변수를 True로 설정하여 응답 그룹 페더ation에 대한 글로벌 정책을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-376">You can configure the global policy for response group federation by using Skype for Business Server Control Panel or by using the **Set-CsExternalAccessPolicy** cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="d2a48-377">전역 정책 설정은 사이트 또는 사용자 정책이 할당되지 않은 모든 사용자에게 적용된다는 점에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-377">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="d2a48-378">따라서 응답 그룹에 대한 이 설정을 변경하기 전에 페더레이션 설정이 조직의 요구 사항을 충족하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-378">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="d2a48-379">사용자에게 정책이 적용되는 방식에 대한 자세한 내용은 [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-379">For details about how policies apply to users, see [Manage External Access Policy for Your Organization](https://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx).</span></span> <span data-ttu-id="d2a48-380">페더ation 설정에 대한 자세한 내용은 **설명서에서 Set-CsExternalAccessPolicy를** 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-380">For details about the federation setting, see **Set-CsExternalAccessPolicy** in documentation..</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-381">비즈니스용 Skype Online에서 호스팅된 사용자는온-프레미스 배포에서 호스트된 응답 그룹에 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-381">Users who are hosted in Skype for Business Online can't place calls to response groups that are hosted in an on-premises deployment.</span></span> <span data-ttu-id="d2a48-382">이는 하이브리드 배포와 비즈니스용 Skype Online 배포와의 페더임이 있는 경우 모두 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-382">This is true in both hybrid deployments and in cases where an on-premises deployment is federated with a Skype for Business Online deployment.</span></span>

9. <span data-ttu-id="d2a48-383">통화하는 동안 에이전트의 ID를 숨기려면 **에이전트 익명성 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-383">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-384">통화가 연결된 후 에이전트 또는 발신자가 IM(인스턴트 메시징) 및 비디오를 추가할 수 있지만 IM 또는 비디오로 익명 통화를 시작할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-384">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="d2a48-385">익명 에이전트는 통화를 보류하고, 전송(무조건 전송 및 협의 전송)하고, 대기시킨 후 재개할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-385">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="d2a48-386">익명 통화는 회의, 응용 프로그램 공유 및 데스크톱 공유, 파일 전송, 화이트보드 및 데이터 공동 작업, 통화 기록을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-386">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="d2a48-387">Lync VDI 플러그 인을 사용하는 에이전트는 수신 전화를 익명으로 받을 수 있지만 익명으로 발신 전화를 걸 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-387">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

10. <span data-ttu-id="d2a48-388">**전화를 받을 그룹의 주소를 입력하십시오** 에 워크플로 호출에 응답할 그룹의 SIP URI(Uniform Resource Identifier) 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-388">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="d2a48-389">**표시 이름** 에 클라이언트에서 워크플로에 대해 표시하도록 할 이름(예: Sales IVR Response Group)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-389">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-390">표시 이름에 \<" or "\> " " 문자를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-390">Do not include the "\<" or "\>" characters in the display name.</span></span> <span data-ttu-id="d2a48-391">**RGS Presence Watcher** 또는 **RGS Presence Watcher** 는 예약되어 있으므로 표시 이름으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-391">Do not use the following display names because they are reserved: **RGS Presence Watcher** or **Announcement Service**.</span></span>

12. <span data-ttu-id="d2a48-392">**전화 번호** 에 응답 그룹의 줄 URI(예: +14255550165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-392">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="d2a48-393">**표시 이름** 에 응답 그룹에 대해 표시할 번호(예: +1 (425) 555-0165)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-393">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="d2a48-394">(선택 사항) **설명에서** 비즈니스용 Skype의 연락처 카드에 표시하려는 워크플로에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-394">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in Skype for Business.</span></span>

15. <span data-ttu-id="d2a48-395">이 워크플로를 응답 그룹 관리자를 통해 관리하려는 경우 **워크플로 유형** 에서 **관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-395">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="d2a48-396">워크플로에 응답 그룹 관리자를 할당하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-396">Do the following to assign Response Group Managers to the workflow:</span></span>

    <span data-ttu-id="d2a48-397">a.</span><span class="sxs-lookup"><span data-stu-id="d2a48-397">a.</span></span> <span data-ttu-id="d2a48-398">이 워크플로의 관리자 SIP URI를 입력하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-398">Type the SIP URI of a manager for this workflow, and click **Add**.</span></span>

    <span data-ttu-id="d2a48-399">b.</span><span class="sxs-lookup"><span data-stu-id="d2a48-399">b.</span></span> <span data-ttu-id="d2a48-400">워크플로에 추가할 다른 관리자의 SIP URI를 입력하고 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-400">Type the SIP URI of additional managers to add to the workflow, and click **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d2a48-p178">응답 그룹의 관리자로 지정된 모든 사용자는 CsResponseGroupManager 역할이 할당되어야 합니다. 이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p178">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

16. <span data-ttu-id="d2a48-403">**2단계 언어 선택** 아래에서 음성 인식 및 텍스트 음성 변환에 사용할 언어를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-403">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="d2a48-404">환영 메시지를 구성하려면 **3단계 환영 메시지 구성** 아래에서 **환영 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-404">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>

    - <span data-ttu-id="d2a48-405">환영 메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 환영 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-405">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p179">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p179">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="d2a48-p180">환영 메시지에 웨이브 또는 Windows Media 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 오디오 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p180">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-412">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-412">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-413">지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-413">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

18. <span data-ttu-id="d2a48-414">**4단계 업무 시간 지정** 아래에 있는 **표준 시간대** 상자에서 워크플로의 표준 시간대를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-414">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p182">표준 시간대는 워크플로의 발신자 및 에이전트가 거주하는 지역의 표준 시간대로서, 시작 및 종료 시간을 계산하는 데 사용됩니다. 예를 들어 북미 동부 표준 시간대를 사용하도록 워크플로가 구성되어 있고 오전 7시에 시작하여 오전 11:00:00시에 끝나도록 워크플로를 예약한 경우 시작 및 종료 시간은 각각 동부 표준시 7시와 동부 표준시 23시로 설정됩니다. 시간은 24시간 형식으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p182">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

19. <span data-ttu-id="d2a48-420">다음 중 하나를 수행하여 사용할 업무 시간 일정의 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-420">Select the type of business hours schedule you want to use by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-421">미리 정의된 업무 시간 일정을 사용하려면 **미리 설정된 일정 사용** 을 클릭한 다음 드롭다운 메뉴에서 사용할 일정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-421">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-422">이 옵션을 선택하려면 이전에 미리 설정된 일정이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-422">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="d2a48-423">**New-CsRgsHoursOfBusiness** cmdlet을 사용하여 미리 설정한 일정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-423">You define preset schedules by using the **New-CsRgsHoursOfBusiness** cmdlet.</span></span> <span data-ttu-id="d2a48-424">자세한 내용은 비즈니스용 Skype에서 응답 그룹 업무 시간 정의(선택 [사항)를 참조하세요.](optional-define-response-group-business-hours.md)</span><span class="sxs-lookup"><span data-stu-id="d2a48-424">For details, see [(Optional) Define Response Group business hours in Skype for Business](optional-define-response-group-business-hours.md).</span></span> <span data-ttu-id="d2a48-425">미리 설정된 일정을 선택한 경우 응답 그룹을 사용할 수 있는 요일 및 시간으로 **요일**, **시작** 및 **종료** 가 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-425">When you select a preset schedule, **Day**, **Open**, and **Close** are automatically filled with the days and hours that the response group is available.</span></span>

    - <span data-ttu-id="d2a48-426">이 워크플로에만 적용되는 사용자 지정 일정을 사용하려면 **사용자 지정 일정 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-426">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="d2a48-427">이 워크플로에 대한 사용자 지정 일정을 만들려면 응답 그룹을 사용할 수 있는 요일 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-427">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="d2a48-428">사용자 지정 일정을 만드는 경우 응답  그룹을 **사용할** 수 있는 열기 및 닫기 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-428">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group will be available.</span></span>

     > [!NOTE]
     > <span data-ttu-id="d2a48-p184">**시작** 및 **종료** 시간은 24시간 형식이어야 합니다. 예를 들어 평일 오전 9시에서 오후 5시까지 근무하고 12시부터 점심 시간 동안 문을 닫는 경우 업무 시간은 **시작** 9:00, **종료** 12:00, **시작** 13:00 및 **종료** 17:00로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p184">The **Open** and **Close** hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as **Open** 9:00, **Close** 12:00, **Open** 13:00, and **Close** 17:00.</span></span>

22. <span data-ttu-id="d2a48-431">근무하지 않는 동안 메시지를 재생하려면 **응답 그룹의 업무 시간이 지났을 때 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-431">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-432">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-432">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-p185">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p185">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="d2a48-p186">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p186">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-439">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-439">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-440">지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-440">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

23. <span data-ttu-id="d2a48-441">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="d2a48-441">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="d2a48-442">통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-442">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="d2a48-443">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-443">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="d2a48-444">음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainname\>* 같습니다(예: bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-444">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="d2a48-445">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-445">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="d2a48-446">사용자 주소의 형식은 _\<username\>_ @ _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="d2a48-446">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="d2a48-447">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-447">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="d2a48-448">전화 번호 형식은 *\<number\>* @ *\<domainname\>* +14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-448">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="d2a48-449">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-449">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="d2a48-450">**5단계 휴일 지정** 아래에서 응답 그룹이 근무하지 않는 요일을 정의하는 하나 이상의 휴일 집합에 대한 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-450">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-451">워크플로를 구성하기 전에 휴일 및 휴일 집합을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-451">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="d2a48-452">**New-CsRgsHoliday** 및 **New-CsRgsHolidaySet** cmdlet을 사용하여 휴일 및 휴일 집합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-452">Use the **New-CsRgsHoliday** and **New-CsRgsHolidaySet** cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="d2a48-453">자세한 내용은 비즈니스용 Skype에서 응답 그룹 휴일 집합 정의(선택 [사항)를 참조하세요.](optional-define-response-group-holiday-sets.md)</span><span class="sxs-lookup"><span data-stu-id="d2a48-453">For details, see [(Optional) Define Response Group holiday sets in Skype for Business](optional-define-response-group-holiday-sets.md).</span></span>

25. <span data-ttu-id="d2a48-454">휴일에 메시지를 재생하려면 **휴일에 메시지를 재생합니다** 확인란을 선택하고 다음 중 하나를 수행하여 재생할 메시지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-454">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-455">메시지를 발신자에게 음성으로 변환되는 텍스트로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-455">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-p192">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p192">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    - <span data-ttu-id="d2a48-p193">메시지에 대한 오디오 파일 녹음을 사용하려면 **녹음 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **녹음** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p193">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-462">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-462">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-463">지원되는 오디오 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-463">For details about supported audio file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

26. <span data-ttu-id="d2a48-464">메시지가 재생된 후에 발신자를 처리할 방법을 지정합니다(메시지가 구성된 경우).</span><span class="sxs-lookup"><span data-stu-id="d2a48-464">Specify how to handle calls after the message is played (if a message is configured):</span></span>

    - <span data-ttu-id="d2a48-465">통화 연결을 끊으려면 **전화 끊기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-465">To disconnect the call, click **Disconnect Call**.</span></span>

    - <span data-ttu-id="d2a48-466">통화를 음성 메일로 착신 전환하려면 **음성 메일로 착신 전환** 을 클릭하고 음성 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-466">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="d2a48-467">음성 메일 주소의 형식은 다음과 *\<username\>* @ *\<domainname\>* 같습니다(예: bob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-467">The format for the voice mail address is  *\<username\>*@*\<domainname\>* (for example, bob@contoso.com).</span></span>

    - <span data-ttu-id="d2a48-468">통화를 다른 사용자에게 착신 전환하려면 **SIP URI로 착신 전환** 을 클릭하고 사용자 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-468">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="d2a48-469">사용자 주소의 형식은 _\<username\>_ @ _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="d2a48-469">The format for the user address is  _\<username\>_@_\<domainname\>_.</span></span>

    - <span data-ttu-id="d2a48-470">통화를 다른 전화 번호로 착신 전환하려면 **전화 번호로 착신 전환** 을 클릭하고 전화 번호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-470">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="d2a48-471">전화 번호 형식은 *\<number\>* @ *\<domainname\>* +14255550121@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d2a48-471">The format for the telephone number is  *\<number\>*@*\<domainname\>* (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="d2a48-472">도메인 이름은 발신자를 올바른 대상으로 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-472">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="d2a48-473">**6단계 대기 음악 구성** 아래에서 다음 중 하나를 수행하여 에이전트를 기다리는 동안 발신자에게 들려줄 음악을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-473">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>

    - <span data-ttu-id="d2a48-474">기본 대기 음악 녹음을 사용하려면 **기본값 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-474">To use the default music on-hold recording, click **Use default**.</span></span>

    - <span data-ttu-id="d2a48-p198">오디오 파일 녹음을 대기 음악에 사용하려면 **음악 파일 선택** 을 클릭합니다. 새 오디오 파일을 업로드하려면 **음악 파일** 링크를 클릭합니다. 새 브라우저 창에서 **찾아보기** 를 클릭하고 사용할 파일을 선택한 다음 **열기** 를 클릭합니다. **업로드** 를 클릭하여 오디오 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p198">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-479">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-479">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-480">지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-480">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

28. <span data-ttu-id="d2a48-481">**7단계 대화형 음성 응답 구성** 의 **사용자에게 다음 텍스트 또는 녹음된 메시지가 재생됩니다** 머리글 아래에서 다음과 같이 발신자에게 제공할 질문을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-481">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>

    - <span data-ttu-id="d2a48-482">질문을 텍스트 형식으로 입력하려면 **텍스트 음성 변환 사용** 을 클릭한 다음 텍스트 상자에 질문을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-482">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-p200">입력하는 텍스트에 HTML 태그를 포함하지 마십시오. HTML 태그를 포함하면 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p200">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-485">"#" 기호는 텍스트 음성 변환 엔진에서 "숫자"라는 단어로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-485">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="d2a48-486"># 키를 참조해야 하는 경우 프롬프트에 기호 대신 키 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-486">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="d2a48-487">예를 들어 "영업과 대화를 하다가 파운드 키를 누르고 있습니다."를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-487">For example, "To talk to sales, press the pound key."</span></span>

    - <span data-ttu-id="d2a48-488">질문이 포함된 미리 녹음된 오디오 파일을 사용하려면 녹음 선택을 클릭한  다음 녹음 링크를 클릭하여 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-488">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file.</span></span> <span data-ttu-id="d2a48-489">새 브라우저 창에서 찾아보기를 **클릭하고** 오디오 파일을 선택한 다음 열기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-489">In the new browser window, click **Browse**, select the audio file, and then click **Open**.</span></span> <span data-ttu-id="d2a48-490">**업로드를** 클릭하여 파일을 로드한 다음 선택적으로 텍스트 상자에 질문을 입력할 수 있습니다(이 경우 질문 및 발신자 응답이 응답 에이전트로 전달될 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="d2a48-490">Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller's response, to be forwarded to the responding agent).</span></span>

      > [!NOTE]
      > <span data-ttu-id="d2a48-491">모든 사용자 제공 오디오 파일은 특정 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-491">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="d2a48-492">지원되는 파일 형식에 대한 자세한 내용은 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d2a48-492">For details about supported file formats, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>

29. <span data-ttu-id="d2a48-493">**응답 1** 아래에서 다음을 수행하여 질문에 대한 첫 번째 가능한 응답을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-493">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d2a48-p204">음성 응답에 따옴표(")를 사용하지 마십시오. 따옴표를 사용하면 IVR에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p204">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2a48-496">발신자가 음성과 영숫자 키패드 입력 중 하나 또는 둘 다를 사용하여 응답하도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-496">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    - <span data-ttu-id="d2a48-497">발신자가 음성을 사용하여 응답하도록 하려면 **음성 응답 입력** 상자에 응답을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-497">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>

    - <span data-ttu-id="d2a48-498">발신자가 키패드의 키를 눌러 응답하도록 하려면 **숫자** 상자에서 키패드 숫자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-498">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="d2a48-499">다음과 같이 발신자를 큐로 라우팅할지 또는 다른 질문을 제공할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-499">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>

    - <span data-ttu-id="d2a48-500">발신자를 큐로 라우팅하려면 **큐로 보내기** 를 클릭한 다음 **큐 선택** 에서 사용할 큐를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-500">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>

    - <span data-ttu-id="d2a48-p205">다른 질문을 제공하려면 **또 다른 질문하기** 를 클릭한 다음 **텍스트 음성 변환 사용** 을 클릭하고 질문을 입력하거나 **녹음 선택** 을 클릭합니다. 이 섹션의 응답 그룹을 사용하여 추가 질문에 가능한 최대 4개의 응답 및 각 응답에 사용할 큐를 지정할 수 있습니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p205">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="d2a48-p206">28단계와 29단계를 반복하여 원래 질문에 가능한 최대 3개의 응답을 추가로 지정하여 가능한 응답 및 각 응답에 대해 수행할 작업을 지정합니다. 세 번째 또는 네 번째 가능한 응답을 지정하려면 **응답 3** 확인란 또는 **응답 4** 확인란을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p206">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="d2a48-506">**배포** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-506">Click **Deploy**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="d2a48-507">비즈니스용 Skype 서버 관리 셸을 사용하여 대화형 워크플로를 만들거나 수정하려면</span><span class="sxs-lookup"><span data-stu-id="d2a48-507">To use Skype for Business Server Management Shell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="d2a48-508">RTCUniversalServerAdmins 그룹의 구성원으로 로그온하거나 응답 그룹을 지원하는 미리 정의한 관리 역할 중 하나의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-508">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2. <span data-ttu-id="d2a48-509">비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d2a48-509">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="d2a48-p207">응답 그룹 서비스의 서비스 이름을 검색하여 변수 하나에 할당합니다. 명령줄에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p207">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>

   ```powershell
   $serviceId = "service:" + (Get-CsService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

4. <span data-ttu-id="d2a48-p208">대화형 워크플로를 만들려면 두 개 이상의 큐와 두 개 이상의 에이전트 그룹이 필요합니다. 먼저 다음을 실행하여 에이전트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p208">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>

   ```powershell
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. <span data-ttu-id="d2a48-p209">다음을 실행하여 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p209">Create the queues. Run:</span></span>

   ```powershell
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. <span data-ttu-id="d2a48-p210">다음을 실행하여 첫 번째 응답 그룹 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p210">Create the first response group prompt. Run:</span></span>

   ```powershell
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. <span data-ttu-id="d2a48-p211">그런 다음 프롬프트 후에 수행할 동작을 만듭니다. 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p211">Then create the action to be performed after the prompt. Run:</span></span>

   ```powershell
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. <span data-ttu-id="d2a48-p212">다음을 실행하여 첫 번째 응답 그룹 답변을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p212">Create the first response group answer. Run:</span></span>

   ```powershell
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. <span data-ttu-id="d2a48-p213">이제 두 번째 프롬프트, 호출 동작 및 답변을 만듭니다. 먼저 다음을 실행하여 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p213">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>

   ```powershell
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. <span data-ttu-id="d2a48-p214">다음을 실행하여 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p214">Create the second call action. Run:</span></span>

    ```powershell
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. <span data-ttu-id="d2a48-p215">다음을 실행하여 두 번째 응답 그룹 답변을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p215">Create the second response group answer. Run:</span></span>

    ```powershell
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. <span data-ttu-id="d2a48-p216">다음을 실행하여 최상위 프롬프트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p216">Create the top-level prompt. Run:</span></span>

    ```powershell
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. <span data-ttu-id="d2a48-p217">다음을 실행하여 최상위 질문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p217">Create the top-level question. Run:</span></span>

    ```powershell
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. <span data-ttu-id="d2a48-p218">이제 다음을 실행하여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-p218">Now create the workflow. Run:</span></span>

    ```powershell
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > <span data-ttu-id="d2a48-536">응답 그룹의 관리자로 지정된 모든 사용자에게 CsResponseGroupManager 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-536">All users who have been designated as manager of a response group must be assigned the CsResponseGroupManager role.</span></span> <span data-ttu-id="d2a48-537">이 역할이 할당되지 않은 사용자는 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a48-537">If users are not assigned this role, they cannot manage response groups.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2a48-538">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2a48-538">See also</span></span>

[<span data-ttu-id="d2a48-539">(선택 사항) 비즈니스용 Skype에서 응답 그룹 휴일 집합 정의</span><span class="sxs-lookup"><span data-stu-id="d2a48-539">(Optional) Define Response Group holiday sets in Skype for Business</span></span>](optional-define-response-group-holiday-sets.md)

[<span data-ttu-id="d2a48-540">(선택 사항) 비즈니스용 Skype에서 응답 그룹 업무 시간 정의</span><span class="sxs-lookup"><span data-stu-id="d2a48-540">(Optional) Define Response Group business hours in Skype for Business</span></span>](optional-define-response-group-business-hours.md)

[<span data-ttu-id="d2a48-541">New-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="d2a48-541">New-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="d2a48-542">Set-CsRgsWorkflow</span><span class="sxs-lookup"><span data-stu-id="d2a48-542">Set-CsRgsWorkflow</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)

[<span data-ttu-id="d2a48-543">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="d2a48-543">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)

[<span data-ttu-id="d2a48-544">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="d2a48-544">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

