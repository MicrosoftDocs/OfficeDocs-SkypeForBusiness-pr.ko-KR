---
title: 'Lync Server 2013: Lync 2013의 새로 만들기 및 변경 된 설정'
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
ms.openlocfilehash: de4a1a82dbefb5a7f55a4c5872a6702933af08c7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a><span data-ttu-id="043de-102">Lync 2013의 새로 만들기 및 변경 된 설정</span><span class="sxs-lookup"><span data-stu-id="043de-102">New and changed settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="043de-103">_**마지막으로 수정 된 항목:** 2014-12-05_</span><span class="sxs-lookup"><span data-stu-id="043de-103">_**Topic Last Modified:** 2014-12-05_</span></span>

<span data-ttu-id="043de-104">이 항목에서는 클라이언트 관리와 직접 관련 된 Lync Server 관리 셸 cmdlet의 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="043de-104">This topic discusses changes to Lync Server Management Shell cmdlets that relate directly to client management.</span></span> <span data-ttu-id="043de-105">Lync Server 2013에는 몇 가지 새로운 매개 변수와 다른 방법을 통해 구성할 수 있는 기능에 대 한 deprecates 매개 변수가 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-105">Lync Server 2013 introduces several new parameters, and deprecates parameters for features that can be configured through other means.</span></span>

<div>

## <a name="new-client-management-parameters"></a><span data-ttu-id="043de-106">새로운 클라이언트 관리 매개 변수</span><span class="sxs-lookup"><span data-stu-id="043de-106">New Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="043de-107">New</span><span class="sxs-lookup"><span data-stu-id="043de-107">New</span></span></th>
<th><span data-ttu-id="043de-108">Lync Server 관리 셸 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="043de-108">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="043de-109">설명</span><span class="sxs-lookup"><span data-stu-id="043de-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="043de-110">TracingLevel</span><span class="sxs-lookup"><span data-stu-id="043de-110">TracingLevel</span></span></p></td>
<td><p><span data-ttu-id="043de-111">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-111">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-112">True로 설정 하면 소프트웨어 추적이 Lync에서 사용 됩니다. False로 설정 하면 소프트웨어 추적이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-112">When set to True, software tracing will be enabled in Lync; when set to False, software tracing will be disabled.</span></span> <span data-ttu-id="043de-113">소프트웨어 추적은 API 통화 추적을 비롯하여 프로그램이 수행하는 모든 작업에 대한 자세한 기록을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="043de-113">Software tracing involves keeping a detailed record of everything that a program does (including tracking API calls).</span></span> <span data-ttu-id="043de-114">추적은 개발자와 응용 프로그램 지원 담당자에 게 대부분 유용 합니다. 이 설정은 Communications Server 2007 R2 그룹 정책 설정과 &quot;Communicator에 대 한 추적을 설정 하는 것과 동일 합니다. &quot; 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-114">Tracing is mostly useful to developers and to application support personnel.This setting is equivalent to the Communications Server 2007 R2 Group Policy setting &quot;Turn on tracing for Communicator.&quot; The settings are as follows:</span></span></p>
<ul>
<li><p><span data-ttu-id="043de-115">Off = 추적을 사용할 수 없고 사용자가 이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-115">Off = Tracing is disabled and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="043de-116">Light = 최소한의 추적이 수행되고 사용자가 이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-116">Light = Minimal tracing is performed, and the user cannot change this setting.</span></span></p></li>
<li><p><span data-ttu-id="043de-117">On = 자세한 추적이 수행되고 사용자가 이 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-117">On = Verbose tracing is performed, and the user cannot change this setting.</span></span></p></li>
</ul>
<p><span data-ttu-id="043de-p103">기본적으로 TracingLevel은 null 값으로 설정됩니다. 즉, 최소한의 추적이 수행되지만 사용자가 이 최소한의 추적을 사용하거나 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-p103">By default TracingLevel is set to a null value. That means that minimal tracing is performed, but the user can enable or disable this minimal tracing.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-120">EnableMediaRedirection</span><span class="sxs-lookup"><span data-stu-id="043de-120">EnableMediaRedirection</span></span></p></td>
<td><p><span data-ttu-id="043de-121">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-121">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-p104">True($True)로 설정하면 오디오 및 비디오 스트림을 다른 네트워크 트래픽과 분리할 수 있습니다. 따라서 클라이언트 장치에서 로컬로 오디오 및 비디오의 인코딩과 디코딩을 수행할 수 있습니다. 일반적으로 미디어 리디렉션은 장치 원격 사용 또는 코덱 압축과 같은 유사한 방법에 비해 대역폭 사용 감소, 서버 확장성 향상, 사용자 환경 최적화 측면에서 더욱 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="043de-p104">When set to True ($True) allows audio and video streams to be separated from other network traffic, In turn, this allows client devices to do encoding and decoding of audio and video locally. Media redirection typically results in lower bandwidth usage, higher server scalability, and a more-optimal user experience compared to similar techniques such as device remoting or codec compression.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043de-124">AllowLargeMeetings</span><span class="sxs-lookup"><span data-stu-id="043de-124">AllowLargeMeetings</span></span></p></td>
<td><p><span data-ttu-id="043de-125">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="043de-125">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="043de-126">True로 설정 하면 모든 Lync 모임이 대규모 모임으로 &quot;취급 됩니다. &quot; 모임이 많은 경우에는 기본적으로 전송 되는 모임 명단의 크기 외에도 참석자에 게 전송 되는 알림 수에 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="043de-126">When set to True, all Lync Meetings are treated as &quot;large meetings.&quot; With a large meeting, restrictions are placed on the number of notifications that are sent to participants, in addition to the size of the meeting roster that is transmitted by default.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-127">DisablePowerPointAnnotations</span><span class="sxs-lookup"><span data-stu-id="043de-127">DisablePowerPointAnnotations</span></span></p></td>
<td><p><span data-ttu-id="043de-128">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="043de-128">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="043de-p105">True($True)로 설정하면 사용자가 전화 회의에 사용되는 PowerPoint 슬라이드에 주석을 추가할 수 없습니다. 그러나 AllowAnnotations 속성의 값에 따라 사용자가 다른 화이트보드 기능에 여전히 액세스할 수 있습니다. 기본값은 False입니다. 즉, PowerPoint 주석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-p105">When set to True ($True) users won’t be able to add annotations to PowerPoint slides used in a conference. However (depending on the value of the AllowAnnotations property), users will still have access to other whiteboarding features. The default value is False, meaning that PowerPoint annotations are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043de-132">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="043de-132">AllowSharedNotes</span></span></p></td>
<td><p><span data-ttu-id="043de-133">CsConferencing</span><span class="sxs-lookup"><span data-stu-id="043de-133">CsConferencing</span></span></p></td>
<td><p><span data-ttu-id="043de-134">True(기본값)로 설정하면 전화 회의에 연결된 열려 있는 모든 OneNote 전자 필기장이 전화 회의 참가자 및 전화 회의 중 공유되는 콘텐츠 정보와 같은 정보를 포함하여 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="043de-134">When set to True (the default value) any open OneNote notebooks linked to the conference will automatically be updated with information such as conference participants and details about content shared during the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-135">EnableInviteCustomization</span><span class="sxs-lookup"><span data-stu-id="043de-135">EnableInviteCustomization</span></span></p></td>
<td><p><span data-ttu-id="043de-136">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="043de-136">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="043de-137">다른 새 Get-csmeetingconfiguration 매개 변수와 함께 사용 되어 Lync 2013에 대 한 온라인 모임 추가 기능에서 생성 된 모임 초대를 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="043de-137">Used along with the other new CsMeetingConfiguration parameters to customize the meeting invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043de-138">LogoURL</span><span class="sxs-lookup"><span data-stu-id="043de-138">LogoURL</span></span></p></td>
<td><p><span data-ttu-id="043de-139">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="043de-139">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="043de-140">Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 로고를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="043de-140">Adds your organization’s logo to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="043de-141">GIF 또는 JPG 이미지의 URL을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="043de-141">You specify the URL of a GIF or JPG image.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-142">도움말 Url</span><span class="sxs-lookup"><span data-stu-id="043de-142">HelpURL</span></span></p></td>
<td><p><span data-ttu-id="043de-143">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="043de-143">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="043de-144">Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 도움말 또는 지원 URL을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="043de-144">Adds your organization’s help or support URL to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043de-145">LegalURL</span><span class="sxs-lookup"><span data-stu-id="043de-145">LegalURL</span></span></p></td>
<td><p><span data-ttu-id="043de-146">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="043de-146">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="043de-147">Lync 2013에 대 한 온라인 모임 추가 기능에서 생성 한 모든 초대에 법적 텍스트 또는 고 지 사항을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="043de-147">Adds legal text or disclaimer text to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="043de-148">텍스트 위치의 URL을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="043de-148">You specify the URL for the location of the text.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-149">CustomFooterText</span><span class="sxs-lookup"><span data-stu-id="043de-149">CustomFooterText</span></span></p></td>
<td><p><span data-ttu-id="043de-150">Get-csmeetingconfiguration</span><span class="sxs-lookup"><span data-stu-id="043de-150">CsMeetingConfiguration</span></span></p></td>
<td><p><span data-ttu-id="043de-151">Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 사용자 지정 바닥글을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="043de-151">Adds a custom footer to all invitations generated by the Online Meeting Add-in for Lync 2013.</span></span> <span data-ttu-id="043de-152">사용자 지정 바닥글 텍스트 위치의 URL을 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="043de-152">You specify the URL for the location of the custom footer text.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a><span data-ttu-id="043de-153">더 이상 사용되지 않는 클라이언트 관리 매개 변수</span><span class="sxs-lookup"><span data-stu-id="043de-153">Deprecated Client Management Parameters</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="043de-154">매개 변수</span><span class="sxs-lookup"><span data-stu-id="043de-154">Parameter</span></span></th>
<th><span data-ttu-id="043de-155">Lync Server 관리 셸 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="043de-155">Lync Server Management Shell Cmdlet</span></span></th>
<th><span data-ttu-id="043de-156">설명</span><span class="sxs-lookup"><span data-stu-id="043de-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="043de-157">CustomizedHelpUrl</span><span class="sxs-lookup"><span data-stu-id="043de-157">CustomizedHelpUrl</span></span></p></td>
<td><p><span data-ttu-id="043de-158">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-158">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-159">이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-159">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="043de-160">EnableEnterpriseCustomizedHelp와 함께 사용 하는 경우이 매개 변수를 사용 하도록 설정 하면 조직에서 Lync의 도움말 메뉴를 클릭할 때 사용자 지정 된 도움말이 표시 되도록 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-160">When used in conjunction with EnableEnterpriseCustomizedHelp, this parameter enabled an organization to specify a URL so that when users clicked the Help menu in Lync, customized help would display.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-161">EnableEnterpriseCustomizedHelp</span><span class="sxs-lookup"><span data-stu-id="043de-161">EnableEnterpriseCustomizedHelp</span></span></p></td>
<td><p><span data-ttu-id="043de-162">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-162">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-163">이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-163">This parameter has been deprecated for use with Lync Server 2013.</span></span> <span data-ttu-id="043de-164">이 매개 변수를 CustomizedHelpUrl와 함께 사용 하면 조직에서 사용자 지정 도움말을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-164">When used in conjunction with CustomizedHelpUrl, this parameter enabled organizations to display customized help.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043de-165">EnableSQMData</span><span class="sxs-lookup"><span data-stu-id="043de-165">EnableSQMData</span></span></p></td>
<td><p><span data-ttu-id="043de-166">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-166">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-167">EnableSQMData 매개 변수가 Lync Server 2013에서 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-167">The EnableSQMData parameter of the Set-CSClientPolicy cmdlet has been removed in Lync Server 2013.</span></span> <span data-ttu-id="043de-168">대신 SQM(Software Quality Management) 데이터에 대한 공유 그룹 정책 설정을 사용하여 Lync 클라이언트 일반 옵션 페이지에 있는 사용자 환경 개선 옵션의 사용자 인터페이스를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-168">Instead, you can use the shared Group Policy setting for Software Quality Management (SQM) data to determine the user interface for the Customer Experience Improvement option in the Lync client General options page:</span></span></p>
<p><span data-ttu-id="043de-169">HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</span><span class="sxs-lookup"><span data-stu-id="043de-169">HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</span></span></p>
<p><span data-ttu-id="043de-170">값</span><span class="sxs-lookup"><span data-stu-id="043de-170">Values:</span></span></p>
<p><span data-ttu-id="043de-171">1 = 확인란을 선택하고 표시합니다(사용자가 확인란을 선택 취소할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="043de-171">1 = Display and select the check box (the user can clear the check box)</span></span></p>
<p><span data-ttu-id="043de-172">0 = 확인란을 선택 취소하고 비활성화합니다(사용자가 이를 무시할 수 없음)</span><span class="sxs-lookup"><span data-stu-id="043de-172">0 = Turn off and disable the check box (user can't override)</span></span></p>
<p><span data-ttu-id="043de-173">Null = 값이 Office 설치 프로그램에서 결정되며 사용자가 원할 경우 선택할 수 있도록 확인란이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="043de-173">Null = The value is determined by Office setup, and the check box is displayed for users to set as they choose</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-174">AllowExchangeContactStore</span><span class="sxs-lookup"><span data-stu-id="043de-174">AllowExchangeContactStore</span></span></p></td>
<td><p><span data-ttu-id="043de-175">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-175">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-176">이 매개 변수는 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-176">This parameter has been removed.</span></span> <span data-ttu-id="043de-177">대신 Lync Server 2013을 배포 하 고 토폴로지를 게시 하면 기본적으로 모든 사용자에 대해 통합 연락처 저장소가 사용 되도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="043de-177">Instead, when you deploy Lync Server 2013 and publish the topology, unified contact store is enabled for all users by default.</span></span> <span data-ttu-id="043de-178">이를 통해 Exchange에 유지되는 사용자의 모든 대화 상대를 Lync, Outlook 및 Outlook Web Access에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-178">This means that all a user’s contacts are kept in Exchange and are available in Lync, Outlook, and Outlook Web Access.</span></span> <span data-ttu-id="043de-179">Set-CsUserServicesPolicy cmdlet을 통해 통합 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-179">You can use the Set-CsUserServicesPolicy cmdlet to customize which users have unified contact store available.</span></span> <span data-ttu-id="043de-180">전역적으로, 사이트별로, 테넌트별로 또는 개인 및 개인 그룹별로 사용자가 통합 연락처 저장소를 사용할 수 있도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-180">You can enable users globally, by site, by tenant, or by individuals or groups of individuals.</span></span> <span data-ttu-id="043de-181">자세한 내용은 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013에서 통합 연락처 저장소에 사용자 사용</a>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="043de-181">For details, see <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Enable users for unified contact store in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043de-182">MAPIPollInterval</span><span class="sxs-lookup"><span data-stu-id="043de-182">MAPIPollInterval</span></span></p></td>
<td><p><span data-ttu-id="043de-183">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-183">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-184">이 매개 변수는 Lync 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-184">This parameter is not used by Lync 2013.</span></span> <span data-ttu-id="043de-185">이전 릴리즈에서 이 매개 변수는 클라이언트가 Exchange 공용 폴더에서 MAPI 데이터를 검색한 빈도를 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-185">In previous releases, this parameter specified how often the client retrieved MAPI data from Exchange public folders</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043de-186">DisableICE</span><span class="sxs-lookup"><span data-stu-id="043de-186">DisableICE</span></span></p></td>
<td><p><span data-ttu-id="043de-187">Set-csclientpolicy</span><span class="sxs-lookup"><span data-stu-id="043de-187">CsClientPolicy</span></span></p></td>
<td><p><span data-ttu-id="043de-188">이 매개 변수는 Lync 2013에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="043de-188">This parameter was deprecated in Lync 2013.</span></span></p></td>
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

