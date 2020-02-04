---
title: 'Lync Server 2013: Lync 메뉴에 명령 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1cbce99116159d119eaa604b7000764913b3cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a><span data-ttu-id="62ee4-102">Lync Server 2013에서 Lync 메뉴에 명령 추가</span><span class="sxs-lookup"><span data-stu-id="62ee4-102">Adding commands to Lync menus in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62ee4-103">_**마지막으로 수정한 주제:** 2016-04-11_</span><span class="sxs-lookup"><span data-stu-id="62ee4-103">_**Topic Last Modified:** 2016-04-11_</span></span>

<span data-ttu-id="62ee4-104">Lync 2013 메뉴에 사용자 지정 명령을 추가 하 고 현재 사용자의 SIP URI (Uniform Resource Identifier) 및 선택한 연락처를 사용자 지정 명령이 시작 되는 응용 프로그램에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-104">You can add custom commands to Lync 2013 menus and pass the SIP Uniform Resource Identifier (URI) of the current user and selected contacts to the application that the custom command starts.</span></span>

<span data-ttu-id="62ee4-105">추가 하는 사용자 지정 명령은 다음 메뉴 중 하나 이상에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-105">The custom commands that you add can appear on one or more of the following menus:</span></span>

  - <span data-ttu-id="62ee4-106">Lync 주 창의 메뉴 모음에 있는 도구 메뉴</span><span class="sxs-lookup"><span data-stu-id="62ee4-106">The Tools menu, on the menu bar in the Lync main window</span></span>

  - <span data-ttu-id="62ee4-107">연락처 목록의 연락처에 대 한 바로 가기 메뉴</span><span class="sxs-lookup"><span data-stu-id="62ee4-107">The shortcut menu for contacts in the Contacts list</span></span>

  - <span data-ttu-id="62ee4-108">대화 창에 있는 기타 옵션 메뉴</span><span class="sxs-lookup"><span data-stu-id="62ee4-108">The More Options menu, in the Conversation window</span></span>

  - <span data-ttu-id="62ee4-109">대화 창 참가자 목록에 나열 된 사용자의 바로 가기 메뉴</span><span class="sxs-lookup"><span data-stu-id="62ee4-109">The shortcut menu for people listed in the Conversation window participant list</span></span>

  - <span data-ttu-id="62ee4-110">대화 상대 카드의 옵션 메뉴</span><span class="sxs-lookup"><span data-stu-id="62ee4-110">The options menu in a contact card</span></span>

<span data-ttu-id="62ee4-111">다음 중 하나를 수행 하는 응용 프로그램 이라는 두 가지 유형의 응용 프로그램에 대해 사용자 지정 명령을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-111">You can define custom commands for two types of applications—applications that do either of the following:</span></span>

  - <span data-ttu-id="62ee4-112">현재 사용자 에게만 적용 되 고 로컬 컴퓨터에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-112">Apply only to the current user and are started on the local computer.</span></span>

  - <span data-ttu-id="62ee4-113">온라인 공동 작업 프로그램과 같은 추가 사용자를 포함 하 고 각 사용자의 컴퓨터에서 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-113">Involve additional users, such as an online collaboration program, and must be started on each user's computer.</span></span>

<span data-ttu-id="62ee4-114">사용자 지정 명령은 다음과 같은 방식으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-114">The custom command can be invoked in the following ways:</span></span>

  - <span data-ttu-id="62ee4-115">하나 이상의 사용자를 선택한 다음 사용자 지정 명령을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-115">Select one or more users, and then choose the custom command.</span></span>

  - <span data-ttu-id="62ee4-116">2-파티 또는 단체 대화를 시작한 다음 사용자 지정 명령을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-116">Start a two-party or multiparty conversation, and then choose the custom command.</span></span>

<div>

## <a name="to-add-a-custom-command"></a><span data-ttu-id="62ee4-117">사용자 지정 명령을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="62ee4-117">To add a custom command</span></span>

<span data-ttu-id="62ee4-118">다음 표의 레지스트리 설정을 사용 하 여 메뉴에 명령을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-118">Use the registry settings in the following table to add a command to the menus.</span></span> <span data-ttu-id="62ee4-119">이러한 항목은 다음 위치 중 하나에 있는 레지스트리에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-119">These entries are placed in the registry at one of the following locations:</span></span>

  - <span data-ttu-id="62ee4-120">32 비트 OS: HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span><span class="sxs-lookup"><span data-stu-id="62ee4-120">For 32bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

  - <span data-ttu-id="62ee4-121">64 비트 OS: HKEY\_로컬\_컴퓨터\\소프트웨어\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\앱</span><span class="sxs-lookup"><span data-stu-id="62ee4-121">For 64bit OS: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps</span></span>

### <a name="custom-command-registry-entries"></a><span data-ttu-id="62ee4-122">사용자 지정 명령 레지스트리 항목</span><span class="sxs-lookup"><span data-stu-id="62ee4-122">Custom Command Registry Entries</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62ee4-123">이름</span><span class="sxs-lookup"><span data-stu-id="62ee4-123">Name</span></span></th>
<th><span data-ttu-id="62ee4-124">유형</span><span class="sxs-lookup"><span data-stu-id="62ee4-124">Type</span></span></th>
<th><span data-ttu-id="62ee4-125">데이터</span><span class="sxs-lookup"><span data-stu-id="62ee4-125">Data</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62ee4-126">이름</span><span class="sxs-lookup"><span data-stu-id="62ee4-126">Name</span></span></p></td>
<td><p><span data-ttu-id="62ee4-127">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62ee4-127">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="62ee4-128">메뉴에 표시 되는 응용 프로그램의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-128">Name of the application as it appears on the menu.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62ee4-129">ApplicationType</span><span class="sxs-lookup"><span data-stu-id="62ee4-129">ApplicationType</span></span></p></td>
<td><p><span data-ttu-id="62ee4-130">DWORD(32</span><span class="sxs-lookup"><span data-stu-id="62ee4-130">DWORD</span></span></p></td>
<td><p><span data-ttu-id="62ee4-131">0 = 실행 파일 (기본값)</span><span class="sxs-lookup"><span data-stu-id="62ee4-131">0 = Executable (default)</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="62ee4-132">ApplicationInstallPath 필요</span><span class="sxs-lookup"><span data-stu-id="62ee4-132">Requires ApplicationInstallPath.</span></span>


</div>
<p><span data-ttu-id="62ee4-133">1 = 프로토콜</span><span class="sxs-lookup"><span data-stu-id="62ee4-133">1 = Protocol</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62ee4-134">ApplicationInstallPath</span><span class="sxs-lookup"><span data-stu-id="62ee4-134">ApplicationInstallPath</span></span></p></td>
<td><p><span data-ttu-id="62ee4-135">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62ee4-135">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="62ee4-136">실행 파일의 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-136">Full path of the executable.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="62ee4-137">ApplicationType이 0 (실행) 인 경우에는 반드시 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-137">Must be specified if ApplicationType is 0 (Executable).</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62ee4-138">패스가</span><span class="sxs-lookup"><span data-stu-id="62ee4-138">Path</span></span></p></td>
<td><p><span data-ttu-id="62ee4-139">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62ee4-139">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="62ee4-140">기본 매개 변수 <em>% user-id%</em> 및 <em>% contact-id%</em>를 포함 하 여 모든 매개 변수와 함께 시작 되는 전체 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-140">Full path to be started along with any parameters, including the default parameters <em>%user-id%</em> and <em>%contact-id%</em>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62ee4-141">SessionType</span><span class="sxs-lookup"><span data-stu-id="62ee4-141">SessionType</span></span></p></td>
<td><p><span data-ttu-id="62ee4-142">DWORD(32</span><span class="sxs-lookup"><span data-stu-id="62ee4-142">DWORD</span></span></p></td>
<td><p><span data-ttu-id="62ee4-143">0 = 로컬 세션.</span><span class="sxs-lookup"><span data-stu-id="62ee4-143">0 = Local session.</span></span> <span data-ttu-id="62ee4-144">로컬 컴퓨터에서 응용 프로그램이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-144">The application is started on the local computer.</span></span></p>
<p><span data-ttu-id="62ee4-145">1 = 파티 2 세션 (기본값).</span><span class="sxs-lookup"><span data-stu-id="62ee4-145">1 = Two-party session (default).</span></span> <span data-ttu-id="62ee4-146">Lync 2013에서 로컬로 응용 프로그램이 시작 된 다음 바탕 화면 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-146">Lync 2013 starts the application locally and then sends a desktop notification to the other user.</span></span> <span data-ttu-id="62ee4-147">다른 사용자가 컴퓨터에서 알림을 클릭 하 여 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-147">The other user clicks the notification to start the application on their computer.</span></span></p>
<p><span data-ttu-id="62ee4-148">2 = 단체 세션.</span><span class="sxs-lookup"><span data-stu-id="62ee4-148">2 = Multiparty session.</span></span> <span data-ttu-id="62ee4-149">Lync 2013에서 로컬로 응용 프로그램이 시작 된 다음 데스크톱 알림을 다른 사용자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-149">Lync 2013 starts the application locally and then sends desktop notifications to the other users.</span></span> <span data-ttu-id="62ee4-150">다른 사용자가 알림을 클릭 하 여 컴퓨터에서 지정 된 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-150">The other user clicks the notification to start the specified application on their computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62ee4-151">ExtensibleMenu</span><span class="sxs-lookup"><span data-stu-id="62ee4-151">ExtensibleMenu</span></span></p></td>
<td><p><span data-ttu-id="62ee4-152">REG_SZ</span><span class="sxs-lookup"><span data-stu-id="62ee4-152">REG_SZ</span></span></p></td>
<td><p><span data-ttu-id="62ee4-153">이 명령이 표시 되는 메뉴 목록 (세미콜론으로 구분)입니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-153">A list of the menus where this command will appear, separated by semicolons.</span></span> <span data-ttu-id="62ee4-154">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-154">Possible values are:</span></span></p>
<p><span data-ttu-id="62ee4-155">MainWindowActions</span><span class="sxs-lookup"><span data-stu-id="62ee4-155">MainWindowActions</span></span></p>
<p><span data-ttu-id="62ee4-156">MainWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="62ee4-156">MainWindowRightClick</span></span></p>
<p><span data-ttu-id="62ee4-157">ConversationWindowActions</span><span class="sxs-lookup"><span data-stu-id="62ee4-157">ConversationWindowActions</span></span></p>
<p><span data-ttu-id="62ee4-158">ConversationWindowRightClick</span><span class="sxs-lookup"><span data-stu-id="62ee4-158">ConversationWindowRightClick</span></span></p>
<p><span data-ttu-id="62ee4-159">연락처 메뉴</span><span class="sxs-lookup"><span data-stu-id="62ee4-159">ContactCardMenu</span></span></p>
<p><span data-ttu-id="62ee4-160">ExtensibleMenu가 정의 되어 있지 않으면 MainWindowRightClick ConversationWindowActions의 default 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-160">If ExtensibleMenu is not defined, the default values of MainWindowRightClick and ConversationWindowActions are used.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="62ee4-161">예를 들어 다음 레지스트리 편집기 (. REG) 파일은 Contoso Sales Contact Manager 메뉴 항목을 대화 창의 동작 메뉴에 추가한 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-161">For example, the following Registry Editor (.REG) file shows the results of adding a Contoso Sales Contact Manager menu item to Actions menu in the Conversation window:</span></span>

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a><span data-ttu-id="62ee4-162">사용자 지정 명령에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="62ee4-162">To access a custom command</span></span>

<span data-ttu-id="62ee4-163">추가 된 사용자 지정 명령에 액세스 하려면 정의한 ExtensibleMenu 값에 따라 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-163">To access a custom command after it is added, do one of the following, depending on the ExtensibleMenu values that you define:</span></span>

  - <span data-ttu-id="62ee4-164">**Mainwindowactions**   Lync 주 창에서 **도구**를 클릭 한 다음 사용자 지정 명령을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-164">**MainWindowActions**   In the Lync main window, click **Tools**, and then click your custom command.</span></span>

  - <span data-ttu-id="62ee4-165">**Mainwindowrightclick**   Lync 주 창에서 대화 상대를 마우스 오른쪽 단추로 클릭 한 다음 사용자 지정 명령을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-165">**MainWindowRightClick**   In the Lync main window, right-click a contact, and then click your custom command.</span></span>

  - <span data-ttu-id="62ee4-166">**ConversationWindowActions**   대화 창에서 **기타 옵션** 아이콘을 클릭 한 다음 사용자 지정 명령을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-166">**ConversationWindowActions**   In the Conversation window, click the **More Options** icon, and then click your custom command.</span></span>

  - <span data-ttu-id="62ee4-167">**ConversationWindowRightClick**   대화 창에서 대화 상대의 이름을 마우스 오른쪽 단추로 클릭 한 다음 사용자 지정 명령을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="62ee4-167">**ConversationWindowRightClick**   In the Conversation window, right-click a contact name, and then click your custom command.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

