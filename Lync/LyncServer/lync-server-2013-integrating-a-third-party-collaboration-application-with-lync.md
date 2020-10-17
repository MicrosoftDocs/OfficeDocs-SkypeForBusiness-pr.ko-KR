---
title: Lync를 사용 하 여 타사 공동 작업 응용 프로그램 통합
description: Lync를 사용 하 여 타사 공동 작업 응용 프로그램 통합
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
ms.openlocfilehash: 7adbe1abab83a569f581af034fc46abfef4cf819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552654"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a><span data-ttu-id="3cef8-103">Lync Server 2013를 사용 하 여 타사 공동 작업 응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="3cef8-103">Integrating a third-party collaboration application with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cef8-104">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3cef8-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3cef8-105">응용 프로그램에 대 한 정보를 레지스트리에 추가 하 여 Lync 2013을 타사 온라인 공동 작업 응용 프로그램과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-105">You can integrate Lync 2013 with any third-party online collaboration application by adding information about the application to the registry.</span></span> <span data-ttu-id="3cef8-106">Lync 2013을 사용 하 여 내부 서버, 인터넷 기반 서비스 또는 둘 다에 호스트 되는 데이터 회의 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-106">You can use Lync 2013 to start data conferencing sessions hosted on an in-house server, an Internet-based service, or both.</span></span> <span data-ttu-id="3cef8-107">대화 상대 목록 또는 기존의 인스턴트 메시징, 음성 및 화상 세션에서 공동 작업(또는 데이터 회의) 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-107">The collaboration or data conferencing session can be started from the Contacts list or from an existing instant messaging, voice, or video session.</span></span> <span data-ttu-id="3cef8-108">Lync 2013는 응용 프로그램을 시작 하기 위한 수단 으로만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-108">Lync 2013 acts only as the vehicle for starting the application.</span></span> <span data-ttu-id="3cef8-109">기존 Lync 2013 대화는 온라인 공동 작업 세션이 시작 된 후에도 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-109">Any existing Lync 2013 conversations remain active after the online collaboration session has begun.</span></span>

<span data-ttu-id="3cef8-110">다음 섹션에서는 Lync 2013를 인터넷 기반 및 서버 기반 공동 작업 응용 프로그램과 통합 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-110">The following sections describe how to integrate Lync 2013 with Internet-based and server-based collaboration applications.</span></span>

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="3cef8-111">Lync 2013을 사용 하 여 Internet-Based 공동 작업 응용 프로그램 통합</span><span class="sxs-lookup"><span data-stu-id="3cef8-111">Integrating an Internet-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="3cef8-112">타사 공동 작업 응용 프로그램을 통합하는 일반적인 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-112">Generally, the steps involved in integrating a third-party collaboration application are as follows:</span></span>

1.  <span data-ttu-id="3cef8-113">응용 프로그램에 대한 정보를 레지스트리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-113">Information about the application is added to the registry.</span></span>

2.  <span data-ttu-id="3cef8-114">이끌이는 Lync 2013에 로그인 하 고 데이터 공유 및 공동 작업을 위해 연락처를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-114">The organizer signs in to Lync 2013 and selects contacts for data sharing and collaboration.</span></span> <span data-ttu-id="3cef8-115">또는 이끌이가 대화 중에 데이터 회의를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-115">Or, the organizer may already be in a conversation and decide to add data conferencing.</span></span>

3.  <span data-ttu-id="3cef8-116">Lync 2013에서 레지스트리를 읽고 공동 작업 응용 프로그램을 시작한 다음 선택한 참가자에 게 사용자 지정 SIP 메시지 (appINVITE)를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-116">Lync 2013 reads the registry, starts the collaboration application, and then sends a custom SIP message—an appINVITE—to the selected participants.</span></span>

4.  <span data-ttu-id="3cef8-117">참가자가 초대를 수락하면 각 참가자의 컴퓨터에서 공동 작업 응용 프로그램이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-117">Participants accept the invitation, and the collaboration application is started on each person’s computer.</span></span> <span data-ttu-id="3cef8-118">Lync 2013는 레지스트리를 사용 하 여 사용할 공동 작업 응용 프로그램을 확인 한 다음 appINVITE 메시지에 포함 된 매개 변수를 사용 하 여 해당 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-118">Lync 2013 uses the registry to determine which collaboration application to use, and then starts that application by using the parameters included in the appINVITE message.</span></span>

<span data-ttu-id="3cef8-119">다음 표에서는 인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합 하는 데 필요한 레지스트리 항목에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-119">The following table describes the registry entries required to integrate an Internet-based collaboration application with Lync 2013.</span></span> <span data-ttu-id="3cef8-120">이러한 항목은 레지스트리에 다음 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-120">These entries are placed in the registry in the following location:</span></span>

  - <span data-ttu-id="3cef8-121">HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3cef8-121">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="3cef8-122">인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="3cef8-122">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cef8-123">이름</span><span class="sxs-lookup"><span data-stu-id="3cef8-123">Name</span></span></th>
<th><span data-ttu-id="3cef8-124">형식</span><span class="sxs-lookup"><span data-stu-id="3cef8-124">Type</span></span></th>
<th><span data-ttu-id="3cef8-125">데이터</span><span class="sxs-lookup"><span data-stu-id="3cef8-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-126">이름</span><span class="sxs-lookup"><span data-stu-id="3cef8-126">Name</span></span></p></td>
<td><p><span data-ttu-id="3cef8-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-128">Lync 2013 메뉴의 응용 프로그램 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-128">The application name for Lync 2013 menus.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cef8-129">SmallIcon</span><span class="sxs-lookup"><span data-stu-id="3cef8-129">SmallIcon</span></span></p></td>
<td><p><span data-ttu-id="3cef8-130">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-130">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-131">16 x 16픽셀 아이콘(BMP 또는 PNG)의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-131">Path to 16-pixel x 16-pixel icon, BMP or PNG.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-132">경로</span><span class="sxs-lookup"><span data-stu-id="3cef8-132">Path</span></span></p></td>
<td><p><span data-ttu-id="3cef8-133">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-133">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-134">온라인 공동 작업 응용 프로그램을 시작할 참가자의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-134">Participant path for starting the online collaboration application.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cef8-135">OriginatorPath</span><span class="sxs-lookup"><span data-stu-id="3cef8-135">OriginatorPath</span></span></p></td>
<td><p><span data-ttu-id="3cef8-136">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-136">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-137">온라인 공동 작업 응용 프로그램을 시작할 이끌이의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-137">Organizer path for starting the online collaboration application.</span></span> <span data-ttu-id="3cef8-138">이 경로에는 Parameters 하위 키에 정의된 사용자 지정 매개 변수가 하나 이상 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-138">This path can contain one or more custom parameters as defined in the Parameters subkey.</span></span> <span data-ttu-id="3cef8-139">예를 들어 <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span><span class="sxs-lookup"><span data-stu-id="3cef8-139">For example, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-140">SessionType</span><span class="sxs-lookup"><span data-stu-id="3cef8-140">SessionType</span></span></p></td>
<td><p><span data-ttu-id="3cef8-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="3cef8-141">DWORD</span></span></p></td>
<td><p><span data-ttu-id="3cef8-p106">0 = 로컬 세션. 응용 프로그램이 로컬 컴퓨터에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-p106">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="3cef8-144">1 = 두 그룹 세션(기본값).</span><span class="sxs-lookup"><span data-stu-id="3cef8-144">1 = Two-party session (default).</span></span> <span data-ttu-id="3cef8-145">Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-145">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="3cef8-146">다른 사용자는 알림을 클릭하여 지정된 응용 프로그램을 자신의 컴퓨터에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-146">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="3cef8-147">2 = 단체 세션.</span><span class="sxs-lookup"><span data-stu-id="3cef8-147">2 = Multiparty session.</span></span> <span data-ttu-id="3cef8-148">Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 시스템 알림을 보내 자신의 컴퓨터에서 지정 된 응용 프로그램을 시작 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-148">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their own computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cef8-149">ExensibleMenu</span><span class="sxs-lookup"><span data-stu-id="3cef8-149">ExensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="3cef8-150">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-150">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-p109">이 명령이 표시될 메뉴 목록입니다. 각 메뉴는 세미콜론으로 구분됩니다. 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-p109">A list of the menus where this command will appear, separated by semi-colons. Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3cef8-153">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="3cef8-153">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="3cef8-154">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="3cef8-154">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="3cef8-155">Conversationwindowactions가 기본값으로</span><span class="sxs-lookup"><span data-stu-id="3cef8-155">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="3cef8-156">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="3cef8-156">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="3cef8-157">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="3cef8-157">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="3cef8-158">ExtensibleMenu가 정의되어 있지 않으면 MainWindowRightClick 및 ConversationWindowActions가 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-158">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3cef8-159">다음 표에 매개 변수의 레지스트리 항목에 대한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-159">The following table describes the registry entries for parameters.</span></span> <span data-ttu-id="3cef8-160">이러한 항목은 HKEY \_ 현재 \_ 사용자 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ 매개 변수에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-160">These entries are place at HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.</span></span>

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a><span data-ttu-id="3cef8-161">인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="3cef8-161">Registry Entries for an Internet-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cef8-162">이름</span><span class="sxs-lookup"><span data-stu-id="3cef8-162">Name</span></span></th>
<th><span data-ttu-id="3cef8-163">형식</span><span class="sxs-lookup"><span data-stu-id="3cef8-163">Type</span></span></th>
<th><span data-ttu-id="3cef8-164">데이터</span><span class="sxs-lookup"><span data-stu-id="3cef8-164">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-165">Param1</span><span class="sxs-lookup"><span data-stu-id="3cef8-165">Param1</span></span></p></td>
<td><p><span data-ttu-id="3cef8-166">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-166">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-167"><code>%Parm1%</code>OriginatorPath 레지스트리 키에 사용자 관련 값을 추가 하기 위해 토큰화 된 형식 ()으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-167">Used in tokenized format (<code>%Parm1%</code>) to add user-specific values to the OriginatorPath registry key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cef8-168">Param2</span><span class="sxs-lookup"><span data-stu-id="3cef8-168">Param2</span></span></p></td>
<td><p><span data-ttu-id="3cef8-169">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-169">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-170">Param1을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3cef8-170">See Param1.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-171">Param3</span><span class="sxs-lookup"><span data-stu-id="3cef8-171">Param3</span></span></p></td>
<td><p><span data-ttu-id="3cef8-172">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-172">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-173">Param1을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3cef8-173">See Param1.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3cef8-174">다음 예제 레지스트리 설정은 ADatum 공동 작업 클라이언트를 Lync 2013와 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-174">The following example registry settings integrate ADatum Collaboration Client with Lync 2013:</span></span>

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a><span data-ttu-id="3cef8-175">Server-Based 공동 작업 응용 프로그램을 Lync 2013에 통합</span><span class="sxs-lookup"><span data-stu-id="3cef8-175">Integrating a Server-Based Collaboration Application with Lync 2013</span></span>

<span data-ttu-id="3cef8-176">Lync 2013 내에서 서버 기반 공동 작업 응용 프로그램을 시작 하기 위한 명령을 추가 하는 설정은 이전 섹션에서 설명한 것과 유사 하며 Internet-Based 공동 작업 응용 프로그램을 Lync 2013에 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-176">The settings to add commands for starting a server-based collaboration application from within Lync 2013 are similar to those described in the previous section, Integrating an Internet-Based Collaboration Application with Lync 2013.</span></span> <span data-ttu-id="3cef8-177">그러나 이번에는 OriginatorPath가 필요하지 않으며 일부 값이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-177">However, the OriginatorPath is not required, and some values are changed.</span></span> <span data-ttu-id="3cef8-178">레지스트리 항목은 다음 위치에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-178">Registry entries are placed in the following location:</span></span>

  - <span data-ttu-id="3cef8-179">HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3cef8-179">HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters</span></span>

### <a name="registry-entries-for-a-server-based-collaboration-application"></a><span data-ttu-id="3cef8-180">서버 기반 공동 작업 응용 프로그램의 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="3cef8-180">Registry Entries for a Server-based Collaboration Application</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cef8-181">이름</span><span class="sxs-lookup"><span data-stu-id="3cef8-181">Name</span></span></th>
<th><span data-ttu-id="3cef8-182">형식</span><span class="sxs-lookup"><span data-stu-id="3cef8-182">Type</span></span></th>
<th><span data-ttu-id="3cef8-183">데이터</span><span class="sxs-lookup"><span data-stu-id="3cef8-183">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-184">이름</span><span class="sxs-lookup"><span data-stu-id="3cef8-184">Name</span></span></p></td>
<td><p><span data-ttu-id="3cef8-185">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-185">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-186">메뉴에 표시되는 응용 프로그램 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-186">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cef8-187">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="3cef8-187">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="3cef8-188">DWORD</span><span class="sxs-lookup"><span data-stu-id="3cef8-188">DWORD</span></span></p></td>
<td><p><span data-ttu-id="3cef8-189">값 = 1.</span><span class="sxs-lookup"><span data-stu-id="3cef8-189">Value = 1.</span></span> <span data-ttu-id="3cef8-190">응용 프로그램 유형을 프로토콜로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-190">Sets the application type to protocol.</span></span> <span data-ttu-id="3cef8-191">이 경우에는 다른 값이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-191">The other possible values do not apply in this case.</span></span> <span data-ttu-id="3cef8-192">이 매개 변수가 없으면 ApplicationType이 0 (실행)으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-192">If not present, ApplicationType is set to 0 (executable).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-193">경로</span><span class="sxs-lookup"><span data-stu-id="3cef8-193">Path</span></span></p></td>
<td><p><span data-ttu-id="3cef8-194">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-194">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-195">공동 작업 응용 프로그램을 시작하는 데 사용되는 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-195">Protocol used to start the collaboration application.</span></span> <span data-ttu-id="3cef8-196">Live Meeting 2007의 경우 경로 값은로 설정 됩니다 <code>meet:%conf-uri%</code> .</span><span class="sxs-lookup"><span data-stu-id="3cef8-196">For Live Meeting 2007, the value of Path is set to <code>meet:%conf-uri%</code>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cef8-197">SessionType</span><span class="sxs-lookup"><span data-stu-id="3cef8-197">SessionType</span></span></p></td>
<td><p><span data-ttu-id="3cef8-198">DWORD</span><span class="sxs-lookup"><span data-stu-id="3cef8-198">DWORD</span></span></p></td>
<td><p><span data-ttu-id="3cef8-p114">0 = 로컬 세션. 응용 프로그램이 로컬 컴퓨터에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-p114">0 = Local session. The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="3cef8-201">1 = 두 그룹 세션(기본값).</span><span class="sxs-lookup"><span data-stu-id="3cef8-201">1 = Two-party session (default).</span></span> <span data-ttu-id="3cef8-202">Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-202">Lync 2013 starts the application locally, and then sends a system notification to the other user.</span></span> <span data-ttu-id="3cef8-203">다른 사용자는 알림을 클릭하여 지정된 응용 프로그램을 자신의 컴퓨터에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-203">The other user clicks the notification and starts the specified application on their computer.</span></span></p>
<p><span data-ttu-id="3cef8-204">2 = 단체 세션.</span><span class="sxs-lookup"><span data-stu-id="3cef8-204">2 = Multiparty session.</span></span> <span data-ttu-id="3cef8-205">Lync 2013은 응용 프로그램을 로컬로 시작한 다음 시스템에서 지정한 응용 프로그램을 시작 하 라는 메시지를 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-205">Lync 2013 starts the application locally, and then sends system notifications to the other users, prompting them to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cef8-206">M가공선 유형</span><span class="sxs-lookup"><span data-stu-id="3cef8-206">MCUType</span></span></p></td>
<td><p><span data-ttu-id="3cef8-207">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-207">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-208">DATA = 서버 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-208">DATA = The type of server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cef8-209">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="3cef8-209">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="3cef8-210">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="3cef8-210">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="3cef8-211">이 명령이 표시 되는 메뉴의 목록이 며 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-211">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="3cef8-212">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-212">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3cef8-213">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="3cef8-213">MainWindowActions</span></span></p></li>
<li><p><span data-ttu-id="3cef8-214">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="3cef8-214">MainWindowRightClick</span></span></p></li>
<li><p><span data-ttu-id="3cef8-215">Conversationwindowactions가 기본값으로</span><span class="sxs-lookup"><span data-stu-id="3cef8-215">ConversationWindowActions</span></span></p></li>
<li><p><span data-ttu-id="3cef8-216">ConversationWindowButton</span><span class="sxs-lookup"><span data-stu-id="3cef8-216">ConversationWindowButton</span></span></p></li>
<li><p><span data-ttu-id="3cef8-217">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="3cef8-217">ConversationWindowRightClick</span></span></p></li>
</ul>
<p><span data-ttu-id="3cef8-218">ExtensibleMenu가 정의되어 있지 않으면 MainWindowRightClick 및 ConversationWindowActions가 기본값으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-218">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3cef8-219">다음은 Lync 2013 내에서 ADatum 공동 작업 클라이언트를 시작 하기 위한 명령을 추가 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="3cef8-219">The following example adds commands to start ADatum Collaboration Client from within Lync 2013:</span></span>

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

