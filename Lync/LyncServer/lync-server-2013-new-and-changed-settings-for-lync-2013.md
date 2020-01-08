---
title: 'Lync Server 2013: Lync 2013의 새로 만들기 및 변경 된 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675997e815dc80ec173e75ca68358ef23c12f380
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="419a2-102">Lync 2013의 새로운 설정 및 변경 됨</span><span class="sxs-lookup"><span data-stu-id="419a2-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="419a2-103">_**마지막으로 수정한 주제:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="419a2-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="419a2-104">이 항목에서는 클라이언트 관리와 직접 관련 된 Lync Server Management Shell cmdlet의 변경 내용에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="419a2-105">Lync Server 2013에는 몇 가지 새로운 매개 변수와 다른 방법을 통해 구성할 수 있는 기능에 대 한 deprecates 매개 변수가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="419a2-106">새 클라이언트 관리 매개 변수</span><span class="sxs-lookup"><span data-stu-id="419a2-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="419a2-107">새로운</span><span class="sxs-lookup"><span data-stu-id="419a2-107">New</span></span></th>
<th><span data-ttu-id="419a2-108">Lync Server 관리 셸 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="419a2-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="419a2-109">설명</span><span class="sxs-lookup"><span data-stu-id="419a2-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="419a2-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="419a2-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="419a2-111">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-112">True로 설정 하면 소프트웨어 추적이 Lync에서 사용 하도록 설정 됩니다. False로 설정 되 면 소프트웨어 추적이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="419a2-113">소프트웨어 추적은 프로그램에서 수행 하는 모든 것에 대 한 자세한 기록 (API 호출 추적 포함)을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="419a2-114">추적은 개발자와 응용 프로그램 지원 담당자에 게 주로 유용 합니다. 이 설정은 통신 서버 2007 R2 그룹 정책 설정 &quot;에 해당 하는 것과 같으며 Communicator 추적을 설정 합니다. &quot; 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="419a2-115">Off = 추적을 사용할 수 없으며 사용자는이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="419a2-116">Light = 최소 추적을 수행 하 고 사용자가이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="419a2-117">On = Verbose 추적을 수행 하 고 사용자가이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="419a2-118">기본적으로 TracingLevel는 null 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-118">By default TracingLevel is set to a null value.</span></span> <span data-ttu-id="419a2-119">즉, 최소한의 추적이 수행 되지만, 사용자는이 최소 추적을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-119">That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="419a2-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="419a2-121">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-122">True ($True)로 설정 된 경우 오디오 및 비디오 스트림을 다른 네트워크 트래픽과 분리할 수 있으므로 클라이언트 장치에서 오디오 및 비디오를 로컬로 인코딩 및 디코딩하는 것을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-122">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally.</span></span> <span data-ttu-id="419a2-123">미디어 리디렉션은 일반적으로 대역폭 사용량을 낮추고, 서버 확장성을 높이 며, 장치 remoting 또는 코덱 압축과 같은 유사한 기술에 비해 최적화 된 사용자 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-123">Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="419a2-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="419a2-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="419a2-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="419a2-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="419a2-126">True로 설정 하면 모든 Lync 모임이 큰 모임으로 &quot;처리 됩니다. &quot; 대용량 모임이 있으면 기본적으로 전송 되는 모임 명단의 크기 외에도 참가자에 게 전송 되는 알림 수에 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="419a2-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="419a2-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="419a2-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="419a2-129">True ($True)로 설정 하면 사용자가 회의에 사용 되는 PowerPoint 슬라이드에 주석을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-129">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference.</span></span> <span data-ttu-id="419a2-130">그러나 AllowAnnotations 속성 값에 따라 사용자는 여전히 다른 whiteboarding 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-130">However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features.</span></span> <span data-ttu-id="419a2-131">기본값은 False로, PowerPoint 주석이 허용 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-131">The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="419a2-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="419a2-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="419a2-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="419a2-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="419a2-134">True (기본값)로 설정 되 면 회의에 연결 된 열려 있는 OneNote 전자 필기장이 자동으로 회의 참가자, 회의 중에 공유 된 콘텐츠에 대 한 세부 정보로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="419a2-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="419a2-136">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="419a2-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="419a2-137">다른 새로운 CsMeetingConfiguration 매개 변수와 함께 사용 하 여 Lync 2013의 온라인 모임 추가 기능에서 생성 된 모임 초대를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="419a2-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="419a2-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="419a2-139">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="419a2-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="419a2-140">Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 로고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="419a2-141">GIF 또는 JPG 이미지의 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-142">도움말 Url</span><span class="sxs-lookup"><span data-stu-id="419a2-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="419a2-143">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="419a2-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="419a2-144">Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 도움말 또는 지원 URL을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="419a2-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="419a2-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="419a2-146">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="419a2-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="419a2-147">Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 법적 고 지 사항 텍스트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="419a2-148">텍스트의 위치에 대 한 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="419a2-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="419a2-150">CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="419a2-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="419a2-151">Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 사용자 지정 바닥글을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="419a2-152">사용자 지정 바닥글 텍스트의 위치에 대 한 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="419a2-153">사용 되지 않는 클라이언트 관리 매개 변수</span><span class="sxs-lookup"><span data-stu-id="419a2-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="419a2-154">매개 변수</span><span class="sxs-lookup"><span data-stu-id="419a2-154">Parameter</span></span></th>
<th><span data-ttu-id="419a2-155">Lync Server 관리 셸 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="419a2-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="419a2-156">설명</span><span class="sxs-lookup"><span data-stu-id="419a2-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="419a2-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="419a2-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="419a2-158">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-159">이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="419a2-160">EnableEnterpriseCustomizedHelp와 함께 사용 하는 경우이 매개 변수는 조직에서 사용자가 Lync의 도움말 메뉴를 클릭할 때 사용자 지정 된 도움말이 표시 되도록 해당 URL을 지정 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="419a2-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="419a2-162">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-163">이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="419a2-164">CustomizedHelpUrl와 함께 사용 하는 경우이 매개 변수는 조직에서 사용자 지정 된 도움말을 표시할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="419a2-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="419a2-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="419a2-166">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-167">Lync Server 2013에서 Set CSClientPolicy cmdlet의 EnableSQMData 매개 변수가 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="419a2-168">대신 SQM (소프트웨어 품질 관리) 데이터에 대 한 공유 그룹 정책 설정을 사용 하 여 Lync 클라이언트 일반 옵션 페이지의 사용자 환경 개선 옵션에 대 한 사용자 인터페이스를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="419a2-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="419a2-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="419a2-170">최대값</span><span class="sxs-lookup"><span data-stu-id="419a2-170">Values:</span></span></p>
<p><span data-ttu-id="419a2-171">1 = 확인란을 표시 하 고 선택 합니다 (사용자가 체크 상자를 지울 수 있음).</span><span class="sxs-lookup"><span data-stu-id="419a2-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="419a2-172">0 = 해제 하 고 확인란을 사용 하지 않도록 설정 합니다 (사용자가 무시할 수 없음).</span><span class="sxs-lookup"><span data-stu-id="419a2-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="419a2-173">Null = 값은 Office 설정에 따라 결정 되며 사용자가 선택 하는 대로 설정할 수 있는 확인란이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="419a2-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="419a2-175">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-176">이 매개 변수는 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-176">This parameter has been removed.</span></span> <span data-ttu-id="419a2-177">대신 Lync Server 2013을 배포 하 고 토폴로지를 게시 하면 모든 사용자에 대해 통합 대화 저장소가 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="419a2-178">즉, 모든 사용자의 연락처가 Exchange에 유지 되 고 Lync, Outlook, Outlook Web Access에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="419a2-179">Set-Csuser서비스 정책 cmdlet을 사용 하 여 통합 된 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="419a2-180">사이트, 테 넌 트 또는 개인 또는 개인 그룹을 기준으로 사용자를 전역적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="419a2-181">자세한 내용은 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013에서 통합 대화 저장소에 사용자 사용</a>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="419a2-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="419a2-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="419a2-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="419a2-183">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-184">이 매개 변수는 Lync 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="419a2-185">이전 릴리스에서이 매개 변수는 클라이언트가 Exchange 공용 폴더에서 MAPI 데이터를 검색 하는 빈도를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="419a2-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="419a2-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="419a2-187">CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="419a2-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="419a2-188">이 매개 변수는 Lync 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="419a2-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

