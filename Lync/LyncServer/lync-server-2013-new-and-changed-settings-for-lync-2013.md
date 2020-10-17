---
title: 'Lync Server 2013: Lync 2013의 새로 만들기 및 변경 된 설정'
description: 'Lync Server 2013: Lync 2013의 새로 만들기 및 변경 된 설정입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf744e1bae774904733390ec624be523ad32bc1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561394"
---
# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="6d229-103">Lync 2013의 새로 만들기 및 변경 된 설정</span><span class="sxs-lookup"><span data-stu-id="6d229-103">New and changed settings for Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d229-104">_**마지막으로 수정 된 항목:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="6d229-104">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="6d229-105">이 항목에서는 클라이언트 관리와 직접 관련 된 Lync Server 관리 셸 cmdlet의 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-105">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="6d229-106">Lync Server 2013에는 몇 가지 새로운 매개 변수와 다른 방법을 통해 구성할 수 있는 기능에 대 한 deprecates 매개 변수가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-106">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="6d229-107">새로운 클라이언트 관리 매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d229-107">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d229-108">신규</span><span class="sxs-lookup"><span data-stu-id="6d229-108">New</span></span></th>
<th><span data-ttu-id="6d229-109">Lync Server 관리 셸 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6d229-109">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="6d229-110">설명</span><span class="sxs-lookup"><span data-stu-id="6d229-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d229-111">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="6d229-111">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="6d229-112">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-112">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-113">True로 설정 하면 소프트웨어 추적이 Lync에서 사용 됩니다. False로 설정 하면 소프트웨어 추적이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-113">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="6d229-114">소프트웨어 추적은 API 통화 추적을 비롯하여 프로그램이 수행하는 모든 작업에 대한 자세한 기록을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-114">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="6d229-115">추적은 개발자와 응용 프로그램 지원 담당자에 게 대부분 유용 합니다. 이 설정은 Communications Server 2007 R2 그룹 정책 설정과 &quot; Communicator에 대 한 추적을 설정 하는 것과 동일 합니다. &quot; 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-115">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d229-116">Off = 추적을 사용할 수 없고 사용자가 이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-116">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="6d229-117">Light = 최소한의 추적이 수행되고 사용자가 이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-117">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="6d229-118">On = 자세한 추적이 수행되고 사용자가 이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-118">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="6d229-p103">기본적으로 TracingLevel은 null 값으로 설정됩니다. 즉, 최소한의 추적이 수행되지만 사용자가 이 최소한의 추적을 사용하거나 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-121">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="6d229-121">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="6d229-122">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-122">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-p104">True($True)로 설정하면 오디오 및 비디오 스트림을 다른 네트워크 트래픽과 분리할 수 있습니다. 따라서 클라이언트 장치에서 로컬로 오디오 및 비디오의 인코딩과 디코딩을 수행할 수 있습니다. 일반적으로 미디어 리디렉션은 장치 원격 사용 또는 코덱 압축과 같은 유사한 방법에 비해 대역폭 사용 감소, 서버 확장성 향상, 사용자 환경 최적화 측면에서 더욱 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d229-125">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="6d229-125">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="6d229-126">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="6d229-126">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="6d229-127">True로 설정 하면 모든 Lync 모임이 대규모 모임으로 취급 됩니다 &quot; . &quot; 모임이 많은 경우에는 기본적으로 전송 되는 모임 명단의 크기 외에도 참석자에 게 전송 되는 알림 수에 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-127">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-128">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="6d229-128">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="6d229-129">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="6d229-129">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="6d229-p105">True($True)로 설정하면 사용자가 전화 회의에 사용되는 PowerPoint 슬라이드에 주석을 추가할 수 없습니다. 그러나 AllowAnnotations 속성의 값에 따라 사용자가 다른 화이트보드 기능에 여전히 액세스할 수 있습니다. 기본값은 False입니다. 즉, PowerPoint 주석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d229-133">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="6d229-133">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="6d229-134">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="6d229-134">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="6d229-135">True(기본값)로 설정하면 전화 회의에 연결된 열려 있는 모든 OneNote 전자 필기장이 전화 회의 참가자 및 전화 회의 중 공유되는 콘텐츠 정보와 같은 정보를 포함하여 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-135">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-136">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="6d229-136">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="6d229-137">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="6d229-137">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6d229-138">다른 새 Get-csmeetingconfiguration 매개 변수와 함께 사용 되어 Lync 2013에 대 한 온라인 모임 추가 기능에서 생성 된 모임 초대를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-138">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d229-139">LogoURL</span><span class="sxs-lookup"><span data-stu-id="6d229-139">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="6d229-140">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="6d229-140">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6d229-141">Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 로고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-141">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="6d229-142">GIF 또는 JPG 이미지의 URL을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-142">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-143">도움말 Url</span><span class="sxs-lookup"><span data-stu-id="6d229-143">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="6d229-144">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="6d229-144">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6d229-145">Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 도움말 또는 지원 URL을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-145">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d229-146">LegalURL</span><span class="sxs-lookup"><span data-stu-id="6d229-146">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="6d229-147">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="6d229-147">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6d229-148">Lync 2013에 대 한 온라인 모임 추가 기능에서 생성 한 모든 초대에 법적 텍스트 또는 고 지 사항을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-148">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="6d229-149">텍스트 위치의 URL을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-149">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-150">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="6d229-150">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="6d229-151">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="6d229-151">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="6d229-152">Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 사용자 지정 바닥글을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-152">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="6d229-153">사용자 지정 바닥글 텍스트 위치의 URL을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-153">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="6d229-154">더 이상 사용되지 않는 클라이언트 관리 매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d229-154">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d229-155">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d229-155">Parameter</span></span></th>
<th><span data-ttu-id="6d229-156">Lync Server 관리 셸 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6d229-156">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="6d229-157">설명</span><span class="sxs-lookup"><span data-stu-id="6d229-157">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d229-158">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="6d229-158">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="6d229-159">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-159">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-160">이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-160">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="6d229-161">EnableEnterpriseCustomizedHelp와 함께 사용 하는 경우이 매개 변수를 사용 하도록 설정 하면 조직에서 Lync의 도움말 메뉴를 클릭할 때 사용자 지정 된 도움말이 표시 되도록 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-161">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-162">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="6d229-162">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="6d229-163">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-163">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-164">이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-164">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="6d229-165">이 매개 변수를 CustomizedHelpUrl와 함께 사용 하면 조직에서 사용자 지정 도움말을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-165">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d229-166">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="6d229-166">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="6d229-167">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-167">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-168">Set-CSClientPolicy cmdlet의 EnableSQMData 매개 변수는 Lync Server 2013에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-168">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="6d229-169">대신 SQM(Software Quality Management) 데이터에 대한 공유 그룹 정책 설정을 사용하여 Lync 클라이언트 일반 옵션 페이지에 있는 사용자 환경 개선 옵션의 사용자 인터페이스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-169">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="6d229-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="6d229-170">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="6d229-171">값</span><span class="sxs-lookup"><span data-stu-id="6d229-171">Values:</span></span></p>
<p><span data-ttu-id="6d229-172">1 = 확인란을 선택하고 표시합니다(사용자가 확인란을 선택 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="6d229-172">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="6d229-173">0 = 확인란을 선택 취소하고 비활성화합니다(사용자가 이를 무시할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="6d229-173">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="6d229-174">Null = 값이 Office 설치 프로그램에서 결정되며 사용자가 원할 경우 선택할 수 있도록 확인란이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-174">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-175">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="6d229-175">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="6d229-176">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-176">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-177">이 매개 변수는 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-177">This parameter has been removed.</span></span> <span data-ttu-id="6d229-178">대신 Lync Server 2013을 배포 하 고 토폴로지를 게시 하면 기본적으로 모든 사용자에 대해 통합 연락처 저장소가 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-178">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="6d229-179">이를 통해 Exchange에 유지되는 사용자의 모든 대화 상대를 Lync, Outlook 및 Outlook Web Access에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-179">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="6d229-180">Set-CsUserServicesPolicy cmdlet을 통해 통합 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-180">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="6d229-181">전역적으로, 사이트별로, 테넌트별로 또는 개인 및 개인 그룹별로 사용자가 통합 연락처 저장소를 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-181">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="6d229-182">자세한 내용은 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013에서 통합 연락처 저장소에 사용자 사용</a>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6d229-182">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d229-183">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="6d229-183">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="6d229-184">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-184">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-185">이 매개 변수는 Lync 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-185">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="6d229-186">이전 릴리즈에서 이 매개 변수는 클라이언트가 Exchange 공용 폴더에서 MAPI 데이터를 검색한 빈도를 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-186">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d229-187">DisableICE</span><span class="sxs-lookup"><span data-stu-id="6d229-187">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="6d229-188">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="6d229-188">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="6d229-189">이 매개 변수는 Lync 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d229-189">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

