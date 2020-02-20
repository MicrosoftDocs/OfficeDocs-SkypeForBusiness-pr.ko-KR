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
ms.openlocfilehash: 9ae021735f5fec25cfaba625bd61460e9f58abb4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145417"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="db0e7-102">Lync Server 2013를 사용 하 여 타사 공동 작업 응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="db0e7-102">Integrating a third-party collaboration application with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db0e7-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="db0e7-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="db0e7-104">응용 프로그램에 대 한 정보를 레지스트리에 추가 하 여 Lync 2013을 타사 온라인 공동 작업 응용 프로그램과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-104">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="db0e7-105">Lync 2013을 사용 하 여 내부 서버, 인터넷 기반 서비스 또는 둘 다에 호스트 되는 데이터 회의 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-105">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="db0e7-106">대화 상대 목록 또는 기존의 인스턴트 메시징, 음성 및 화상 세션에서 공동 작업(또는 데이터 회의) 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-106">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="db0e7-107">Lync 2013는 응용 프로그램을 시작 하기 위한 수단 으로만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-107">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="db0e7-108">기존 Lync 2013 대화는 온라인 공동 작업 세션이 시작 된 후에도 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-108">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="db0e7-109">다음 섹션에서는 Lync 2013를 인터넷 기반 및 서버 기반 공동 작업 응용 프로그램과 통합 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-109">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="db0e7-110">Lync 2013에 인터넷 기반 공동 작업 응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="db0e7-110">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="db0e7-111">타사 공동 작업 응용 프로그램을 통합하는 일반적인 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-111">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="db0e7-112">응용 프로그램에 대한 정보를 레지스트리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-112">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="db0e7-113">이끌이는 Lync 2013에 로그인 하 고 데이터 공유 및 공동 작업을 위해 연락처를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-113">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="db0e7-114">또는 이끌이가 대화 중에 데이터 회의를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-114">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="db0e7-115">Lync 2013에서 레지스트리를 읽고 공동 작업 응용 프로그램을 시작한 다음 선택한 참가자에 게 사용자 지정 SIP 메시지 (appINVITE)를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-115">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="db0e7-116">참가자가 초대를 수락하면 각 참가자의 컴퓨터에서 공동 작업 응용 프로그램이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-116">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="db0e7-117">Lync 2013는 레지스트리를 사용 하 여 사용할 공동 작업 응용 프로그램을 확인 한 다음 appINVITE 메시지에 포함 된 매개 변수를 사용 하 여 해당 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-117">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="db0e7-118">다음 표에서는 인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합 하는 데 필요한 레지스트리 항목에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-118">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="db0e7-119">이러한 항목은 레지스트리에 다음 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-119">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="db0e7-120">HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수</span><span class="sxs-lookup"><span data-stu-id="db0e7-120">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="db0e7-121">인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="db0e7-121">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db0e7-122">이름</span><span class="sxs-lookup"><span data-stu-id="db0e7-122">Name</span></span></th>
<th><span data-ttu-id="db0e7-123">형식</span><span class="sxs-lookup"><span data-stu-id="db0e7-123">Type</span></span></th>
<th><span data-ttu-id="db0e7-124">데이터</span><span class="sxs-lookup"><span data-stu-id="db0e7-124">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-125">이름</span><span class="sxs-lookup"><span data-stu-id="db0e7-125">Name</span></span></p></td>
<td><p><span data-ttu-id="db0e7-126">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-126">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-127">Lync 2013 메뉴의 응용 프로그램 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-127">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db0e7-128">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="db0e7-128">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="db0e7-129">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-129">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-130">16 x 16픽셀 아이콘(BMP 또는 PNG)의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-130">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-131">경로</span><span class="sxs-lookup"><span data-stu-id="db0e7-131">Path</span></span></p></td>
<td><p><span data-ttu-id="db0e7-132">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-132">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-133">온라인 공동 작업 응용 프로그램을 시작할 참가자의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-133">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db0e7-134">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="db0e7-134">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="db0e7-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-136">온라인 공동 작업 응용 프로그램을 시작할 이끌이의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-136">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="db0e7-137">이 경로에는 Parameters 하위 키에 정의된 사용자 지정 매개 변수가 하나 이상 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-137">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="db0e7-138">예를 들어<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="db0e7-138">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-139">SessionType</span><span class="sxs-lookup"><span data-stu-id="db0e7-139">SessionType</span></span></p></td>
<td><p><span data-ttu-id="db0e7-140">DWORD</span><span class="sxs-lookup"><span data-stu-id="db0e7-140">DWORD</span></span></p></td>
<td><p><span data-ttu-id="db0e7-p106">0 = 로컬 세션. 응용 프로그램이 로컬 컴퓨터에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="db0e7-143">1 = 두 그룹 세션(기본값).</span><span class="sxs-lookup"><span data-stu-id="db0e7-143">1 = Two-party session (default).</span></span> <span data-ttu-id="db0e7-144">Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-144">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="db0e7-145">다른 사용자는 알림을 클릭하여 지정된 응용 프로그램을 자신의 컴퓨터에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-145">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="db0e7-146">2 = 단체 세션.</span><span class="sxs-lookup"><span data-stu-id="db0e7-146">2 = Multiparty session.</span></span> <span data-ttu-id="db0e7-147">Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 시스템 알림을 보내 자신의 컴퓨터에서 지정 된 응용 프로그램을 시작 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-147">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db0e7-148">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="db0e7-148">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="db0e7-149">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-149">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-p109">이 명령이 표시될 메뉴 목록입니다. 각 메뉴는 세미콜론으로 구분됩니다. 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="db0e7-152">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="db0e7-152">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="db0e7-153">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="db0e7-153">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="db0e7-154">Conversationwindowactions가 기본값으로</span><span class="sxs-lookup"><span data-stu-id="db0e7-154">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="db0e7-155">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="db0e7-155">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="db0e7-156">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="db0e7-156">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="db0e7-157">ExtensibleMenu가 정의되어 있지 않으면 MainWindowRightClick 및 ConversationWindowActions가 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-157">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db0e7-158">다음 표에 매개 변수의 레지스트리 항목에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-158">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="db0e7-159">이러한 항목\_은 HKEY 현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-159">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="db0e7-160">인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="db0e7-160">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db0e7-161">이름</span><span class="sxs-lookup"><span data-stu-id="db0e7-161">Name</span></span></th>
<th><span data-ttu-id="db0e7-162">형식</span><span class="sxs-lookup"><span data-stu-id="db0e7-162">Type</span></span></th>
<th><span data-ttu-id="db0e7-163">데이터</span><span class="sxs-lookup"><span data-stu-id="db0e7-163">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-164">Param1</span><span class="sxs-lookup"><span data-stu-id="db0e7-164">Param1</span></span></p></td>
<td><p><span data-ttu-id="db0e7-165">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-165">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-166">OriginatorPath 레지스트리 키에 사용자<code>%Parm1%</code>관련 값을 추가 하기 위해 토큰화 된 형식 ()으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-166">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db0e7-167">Param2</span><span class="sxs-lookup"><span data-stu-id="db0e7-167">Param2</span></span></p></td>
<td><p><span data-ttu-id="db0e7-168">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-168">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-169">Param1을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="db0e7-169">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-170">Param3</span><span class="sxs-lookup"><span data-stu-id="db0e7-170">Param3</span></span></p></td>
<td><p><span data-ttu-id="db0e7-171">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-171">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-172">Param1을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="db0e7-172">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db0e7-173">다음 예제 레지스트리 설정은 ADatum 공동 작업 클라이언트를 Lync 2013와 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-173">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="db0e7-174">Lync 2013을 사용 하 여 서버 기반 공동 작업 응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="db0e7-174">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="db0e7-175">Lync 2013 내에서 서버 기반 공동 작업 응용 프로그램을 시작 하기 위한 명령을 추가 하는 설정은 이전 섹션에서 설명한 것과 비슷하며, 인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-175">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="db0e7-176">그러나 이번에는 OriginatorPath가 필요하지 않으며 일부 값이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-176">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="db0e7-177">레지스트리 항목은 다음 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-177">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="db0e7-178">HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수</span><span class="sxs-lookup"><span data-stu-id="db0e7-178">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="db0e7-179">서버 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="db0e7-179">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db0e7-180">이름</span><span class="sxs-lookup"><span data-stu-id="db0e7-180">Name</span></span></th>
<th><span data-ttu-id="db0e7-181">형식</span><span class="sxs-lookup"><span data-stu-id="db0e7-181">Type</span></span></th>
<th><span data-ttu-id="db0e7-182">데이터</span><span class="sxs-lookup"><span data-stu-id="db0e7-182">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-183">이름</span><span class="sxs-lookup"><span data-stu-id="db0e7-183">Name</span></span></p></td>
<td><p><span data-ttu-id="db0e7-184">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-184">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-185">메뉴에 표시되는 응용 프로그램 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-185">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db0e7-186">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="db0e7-186">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="db0e7-187">DWORD</span><span class="sxs-lookup"><span data-stu-id="db0e7-187">DWORD</span></span></p></td>
<td><p><span data-ttu-id="db0e7-188">값 = 1.</span><span class="sxs-lookup"><span data-stu-id="db0e7-188">Value = 1.</span></span> <span data-ttu-id="db0e7-189">응용 프로그램 유형을 프로토콜로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-189">Sets the application type to protocol.</span></span> <span data-ttu-id="db0e7-190">이 경우에는 다른 값이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-190">The other possible values do not apply in this case.</span></span> <span data-ttu-id="db0e7-191">이 매개 변수가 없으면 ApplicationType이 0 (실행)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-191">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-192">경로</span><span class="sxs-lookup"><span data-stu-id="db0e7-192">Path</span></span></p></td>
<td><p><span data-ttu-id="db0e7-193">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-193">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-194">공동 작업 응용 프로그램을 시작하는 데 사용되는 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-194">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="db0e7-195">Live Meeting 2007의 경우 경로 값은로 <code>meet:%conf-uri%</code>설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-195">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db0e7-196">SessionType</span><span class="sxs-lookup"><span data-stu-id="db0e7-196">SessionType</span></span></p></td>
<td><p><span data-ttu-id="db0e7-197">DWORD</span><span class="sxs-lookup"><span data-stu-id="db0e7-197">DWORD</span></span></p></td>
<td><p><span data-ttu-id="db0e7-p114">0 = 로컬 세션. 응용 프로그램이 로컬 컴퓨터에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="db0e7-200">1 = 두 그룹 세션(기본값).</span><span class="sxs-lookup"><span data-stu-id="db0e7-200">1 = Two-party session (default).</span></span> <span data-ttu-id="db0e7-201">Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-201">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="db0e7-202">다른 사용자는 알림을 클릭하여 지정된 응용 프로그램을 자신의 컴퓨터에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-202">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="db0e7-203">2 = 단체 세션.</span><span class="sxs-lookup"><span data-stu-id="db0e7-203">2 = Multiparty session.</span></span> <span data-ttu-id="db0e7-204">Lync 2013은 응용 프로그램을 로컬로 시작한 다음 시스템에서 지정한 응용 프로그램을 시작 하 라는 메시지를 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-204">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db0e7-205">M가공선 유형</span><span class="sxs-lookup"><span data-stu-id="db0e7-205">MCUType</span></span></p></td>
<td><p><span data-ttu-id="db0e7-206">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-206">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-207">DATA = 서버 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-207">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db0e7-208">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="db0e7-208">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="db0e7-209">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="db0e7-209">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="db0e7-210">이 명령이 표시 되는 메뉴의 목록이 며 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-210">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="db0e7-211">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-211">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="db0e7-212">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="db0e7-212">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="db0e7-213">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="db0e7-213">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="db0e7-214">Conversationwindowactions가 기본값으로</span><span class="sxs-lookup"><span data-stu-id="db0e7-214">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="db0e7-215">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="db0e7-215">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="db0e7-216">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="db0e7-216">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="db0e7-217">ExtensibleMenu가 정의되어 있지 않으면 MainWindowRightClick 및 ConversationWindowActions가 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-217">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db0e7-218">다음은 Lync 2013 내에서 ADatum 공동 작업 클라이언트를 시작 하기 위한 명령을 추가 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="db0e7-218">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

