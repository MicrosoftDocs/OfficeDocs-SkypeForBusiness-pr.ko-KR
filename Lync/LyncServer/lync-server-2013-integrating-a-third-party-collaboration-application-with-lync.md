---
title: Lync를 사용 하 여 타사 공동 작업 응용 프로그램 통합
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b95f79202cbf96568b98dcb802e97bf4ca2d32
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="8b12f-102">Lync Server 2013을 사용 하 여 타사 공동 작업 응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="8b12f-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b12f-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="8b12f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="8b12f-104">앱에 대 한 정보를 레지스트리에 추가 하 여 Lync 2013을 타사 온라인 공동 작업 응용 프로그램과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="8b12f-105">Lync 2013를 사용 하 여 사내 서버, 인터넷 기반 서비스 또는 둘 다에 호스트 된 데이터 회의 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="8b12f-106">공동 작업 또는 데이터 회의 세션은 연락처 목록 또는 기존 인스턴트 메시징, 음성 또는 비디오 세션에서 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="8b12f-107">Lync 2013는 응용 프로그램을 시작 하는 수단 으로만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="8b12f-108">온라인 공동 작업 세션이 시작 된 후 기존의 모든 Lync 2013 대화가 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="8b12f-109">다음 섹션에서는 Lync 2013를 인터넷 기반 및 서버 기반 공동 작업 응용 프로그램과 통합 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="8b12f-110">인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합</span><span class="sxs-lookup"><span data-stu-id="8b12f-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="8b12f-111">일반적으로 타사 공동 작업 응용 프로그램 통합에 관련 된 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="8b12f-112">응용 프로그램에 대 한 정보가 레지스트리에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="8b12f-113">이끌이는 Lync 2013에 로그인 하 고 데이터 공유 및 공동 작업을 위해 연락처를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="8b12f-114">또는 이끌이는 이미 대화에 있을 수 있으며 데이터 회의 추가를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="8b12f-115">Lync 2013에서 레지스트리를 읽고 공동 작업 응용 프로그램을 시작한 다음 사용자 지정 SIP 메시지 (appINVITE)를 선택 된 참가자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="8b12f-116">참가자가 초대를 수락 하 고 공동 작업 응용 프로그램이 각 사용자의 컴퓨터에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="8b12f-117">Lync 2013는 레지스트리를 사용 하 여 사용할 공동 작업 응용 프로그램을 결정 한 다음 appINVITE 메시지에 포함 된 매개 변수를 사용 하 여 해당 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="8b12f-118">다음 표에서는 인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합 하는 데 필요한 레지스트리 항목에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="8b12f-119">이러한 항목은 다음 위치의 레지스트리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="8b12f-120">HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b12f-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="8b12f-121">인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="8b12f-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b12f-122">이름</span><span class="sxs-lookup"><span data-stu-id="8b12f-122">Name</span></span></th>
<th><span data-ttu-id="8b12f-123">유형</span><span class="sxs-lookup"><span data-stu-id="8b12f-123">Type</span></span></th>
<th><span data-ttu-id="8b12f-124">데이터</span><span class="sxs-lookup"><span data-stu-id="8b12f-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-125">이름</span><span class="sxs-lookup"><span data-stu-id="8b12f-125">Name</span></span></p></td>
<td><p><span data-ttu-id="8b12f-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-127">Lync 2013 메뉴의 응용 프로그램 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b12f-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="8b12f-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="8b12f-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-130">16 픽셀 x 16 픽셀 아이콘, BMP 또는 PNG에 대 한 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-131">패스가</span><span class="sxs-lookup"><span data-stu-id="8b12f-131">Path</span></span></p></td>
<td><p><span data-ttu-id="8b12f-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-133">온라인 공동 작업 응용 프로그램을 시작 하기 위한 참가자 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b12f-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="8b12f-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="8b12f-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-136">온라인 공동 작업 응용 프로그램을 시작 하기 위한 이끌이 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="8b12f-137">이 경로에는 Parameters 하위 키에 정의 된 대로 하나 이상의 사용자 지정 매개 변수가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="8b12f-138">예를 들어<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="8b12f-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="8b12f-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="8b12f-140">DWORD(32</span><span class="sxs-lookup"><span data-stu-id="8b12f-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="8b12f-141">0 = 로컬 세션.</span><span class="sxs-lookup"><span data-stu-id="8b12f-141">0 = Local session.</span></span> <span data-ttu-id="8b12f-142">로컬 컴퓨터에서 응용 프로그램이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-142">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="8b12f-143">1 = 파티 2 세션 (기본값).</span><span class="sxs-lookup"><span data-stu-id="8b12f-143">1 = Two-party session (default).</span></span> <span data-ttu-id="8b12f-144">Lync 2013는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="8b12f-145">다른 사용자가 알림을 클릭 하 고 컴퓨터에서 지정 된 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="8b12f-146">2 = 단체 세션.</span><span class="sxs-lookup"><span data-stu-id="8b12f-146">2 = Multiparty session.</span></span> <span data-ttu-id="8b12f-147">Lync 2013는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 시스템 알림을 보내어 자신의 컴퓨터에서 지정 된 응용 프로그램을 시작 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b12f-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="8b12f-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="8b12f-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-150">이 명령이 표시 되는 메뉴의 목록으로, 세미콜론으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-150">A list of the menus where this command will appear, separated by semi-colons.</span></span> <span data-ttu-id="8b12f-151">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-151">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b12f-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="8b12f-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="8b12f-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="8b12f-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="8b12f-154">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="8b12f-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="8b12f-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="8b12f-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="8b12f-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="8b12f-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="8b12f-157">ExtensibleMenu가 정의 되어 있지 않으면 MainWindowRightClick ConversationWindowActions의 default 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b12f-158">다음 표에서는 매개 변수에 대 한 레지스트리 항목에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="8b12f-159">이러한 항목\_은 HKEY 현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수를 사용 하 여 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="8b12f-160">인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="8b12f-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b12f-161">이름</span><span class="sxs-lookup"><span data-stu-id="8b12f-161">Name</span></span></th>
<th><span data-ttu-id="8b12f-162">유형</span><span class="sxs-lookup"><span data-stu-id="8b12f-162">Type</span></span></th>
<th><span data-ttu-id="8b12f-163">데이터</span><span class="sxs-lookup"><span data-stu-id="8b12f-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-164">Param1</span><span class="sxs-lookup"><span data-stu-id="8b12f-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="8b12f-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-166">OriginatorPath 레지스트리 키에 사용자<code>%Parm1%</code>관련 값을 추가 하기 위해 토큰화 된 형식 ()으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b12f-167">Param2</span><span class="sxs-lookup"><span data-stu-id="8b12f-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="8b12f-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-169">Param1을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b12f-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-170">Param3</span><span class="sxs-lookup"><span data-stu-id="8b12f-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="8b12f-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-172">Param1을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8b12f-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b12f-173">다음 예제 레지스트리 설정은 ADatum 협업 클라이언트를 Lync 2013와 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="8b12f-174">서버 기반 공동 작업 응용 프로그램을 Lync 2013와 통합</span><span class="sxs-lookup"><span data-stu-id="8b12f-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="8b12f-175">Lync 2013에서 서버 기반 공동 작업 응용 프로그램을 시작 하는 데 사용할 수 있는 명령을 추가 하는 설정은 이전 섹션에서 설명한 것과 유사 하며, Lync 2013를 사용 하 여 인터넷 기반 공동 작업 응용 프로그램을 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="8b12f-176">그러나 OriginatorPath는 필요 하지 않으며 일부 값이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="8b12f-177">레지스트리 항목은 다음 위치에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="8b12f-178">HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b12f-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="8b12f-179">서버 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="8b12f-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b12f-180">이름</span><span class="sxs-lookup"><span data-stu-id="8b12f-180">Name</span></span></th>
<th><span data-ttu-id="8b12f-181">유형</span><span class="sxs-lookup"><span data-stu-id="8b12f-181">Type</span></span></th>
<th><span data-ttu-id="8b12f-182">데이터</span><span class="sxs-lookup"><span data-stu-id="8b12f-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-183">이름</span><span class="sxs-lookup"><span data-stu-id="8b12f-183">Name</span></span></p></td>
<td><p><span data-ttu-id="8b12f-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-185">메뉴에 표시 되는 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b12f-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="8b12f-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="8b12f-187">DWORD(32</span><span class="sxs-lookup"><span data-stu-id="8b12f-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="8b12f-188">값 = 1.</span><span class="sxs-lookup"><span data-stu-id="8b12f-188">Value = 1.</span></span> <span data-ttu-id="8b12f-189">응용 프로그램 종류를 protocol으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-189">Sets the application type to protocol.</span></span> <span data-ttu-id="8b12f-190">이 경우에는 다른 가능 값이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="8b12f-191">없을 경우 ApplicationType이 0 (실행)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-192">패스가</span><span class="sxs-lookup"><span data-stu-id="8b12f-192">Path</span></span></p></td>
<td><p><span data-ttu-id="8b12f-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-194">공동 작업 응용 프로그램을 시작 하는 데 사용 되는 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="8b12f-195">Live Meeting 2007의 경우 경로 값이로 <code>meet:%conf-uri%</code>설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b12f-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="8b12f-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="8b12f-197">DWORD(32</span><span class="sxs-lookup"><span data-stu-id="8b12f-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="8b12f-198">0 = 로컬 세션.</span><span class="sxs-lookup"><span data-stu-id="8b12f-198">0 = Local session.</span></span> <span data-ttu-id="8b12f-199">로컬 컴퓨터에서 응용 프로그램이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-199">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="8b12f-200">1 = 파티 2 세션 (기본값).</span><span class="sxs-lookup"><span data-stu-id="8b12f-200">1 = Two-party session (default).</span></span> <span data-ttu-id="8b12f-201">Lync 2013는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="8b12f-202">다른 사용자가 알림을 클릭 하 고 컴퓨터에서 지정 된 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="8b12f-203">2 = 단체 세션.</span><span class="sxs-lookup"><span data-stu-id="8b12f-203">2 = Multiparty session.</span></span> <span data-ttu-id="8b12f-204">Lync 2013는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 시스템 알림을 보내어 컴퓨터에서 지정 된 응용 프로그램을 시작 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b12f-205">M가공선</span><span class="sxs-lookup"><span data-stu-id="8b12f-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="8b12f-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-207">데이터 = 서버의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b12f-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="8b12f-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="8b12f-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="8b12f-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="8b12f-210">이 명령이 표시 되는 메뉴 목록 (세미콜론으로 구분)입니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="8b12f-211">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b12f-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="8b12f-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="8b12f-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="8b12f-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="8b12f-214">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="8b12f-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="8b12f-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="8b12f-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="8b12f-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="8b12f-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="8b12f-217">ExtensibleMenu가 정의 되어 있지 않으면 MainWindowRightClick ConversationWindowActions의 default 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8b12f-218">다음 예에서는 Lync 2013 내에서 ADatum 공동 작업 클라이언트를 시작 하는 명령을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b12f-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

