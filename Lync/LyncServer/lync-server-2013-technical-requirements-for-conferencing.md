---
title: Lync Server 2013 회의에 대한 기술 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="5f499-102">Lync Server 2013의 회의에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f499-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f499-103">_**마지막으로 수정한 주제:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="5f499-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="5f499-104">Lync Server 2013, 전화 접속 회의, A/V 회의, 인스턴트 메시징 (IM) 회의, 웹 회의 기능은 항상 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="5f499-105">이 섹션에서는 이러한 서버에 대 한 하드웨어 및 소프트웨어 요구 사항과 지원 되는 collocation에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="5f499-106">전화 접속 회의는 다양 한 구성 요소를 포함 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="5f499-107">일부 구성 요소는 전화 접속 회의 및 엔터프라이즈 음성 구성 요소에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="5f499-108">이 섹션에서는 전화 접속 회의와 관련 된 구성 요소의 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="5f499-109">중재 서버 및 PSTN (공개 통신 네트워크) 게이트웨이 요구 사항에 대 한 자세한 내용은 계획 설명서의 [lync server 2013에서 중재 서버에 대 한 Lync server 2013 및 구성 요소 및 토폴로지의](lync-server-2013-components-and-topologies-for-mediation-server.md) [중재 서버 구성 요소](lync-server-2013-mediation-server-component.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f499-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="5f499-110">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f499-110">Hardware Requirements</span></span>

<span data-ttu-id="5f499-111">웹 회의와 A/V 회의는 프런트 엔드 서버와 collocated, 서버 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="5f499-112">하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f499-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="5f499-113">또한 전화 접속 회의에 필요한 다음 구성 요소에는 프런트 엔드 서버와 동일한 하드웨어 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="5f499-114">응용 프로그램 서비스</span><span class="sxs-lookup"><span data-stu-id="5f499-114">Application service</span></span>

  - <span data-ttu-id="5f499-115">회의 수행자 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="5f499-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="5f499-116">회의 알림 신청</span><span class="sxs-lookup"><span data-stu-id="5f499-116">Conferencing Announcement application</span></span>

<span data-ttu-id="5f499-117">프런트 엔드 서버에 대 한 하드웨어 요구 사항은 다음 표에 요약 되어 있는 Lync Server 2013의 다른 여러 서버 역할에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="5f499-118">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f499-118">Software Requirements</span></span>

<span data-ttu-id="5f499-119">웹 회의와 A/V 회의는 프런트 엔드 서버와 collocated, 서버 소프트웨어 요구 사항은 프런트 엔드 서버와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="5f499-120">소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f499-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5f499-121">웹 회의의 경우, Lync Server 2013에는 Office Web Apps 및 Office Web Apps 서버 (이전의 WAC Server)가 필요 하며, PowerPoint 프레젠테이션을 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="5f499-122">자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f499-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="5f499-123">전화 접속 회의의 경우 응용 프로그램 서비스, 회의 수행자 응용 프로그램, 회의 알림 응용 프로그램은 프런트 엔드 서버와 동일한 운영 체제 요구 사항을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="5f499-124">소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f499-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5f499-125">회의 수행자 응용 프로그램 및 회의 알림 응용 프로그램을 실행 하려면 Windows Media 형식 런타임이 프런트 엔드 서버에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="5f499-126">Windows Media 형식 런타임은 대기 중인 음악, 기록 된 이름 및 프롬프트에 사용 되는 WMA (Windows Media audio) 파일을 재생 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="5f499-127">Windows Server 2012 및 Windows Server 2012 R2를 제외 하 고, 설치 프로그램을 실행할 때 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 자동 설치 되지만 컴퓨터를 다시 시작 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="5f499-128">따라서 설치 프로그램을 실행 하기 전에 Windows Media 형식 런타임을 포함 하는 Windows 데스크톱 환경의 일부로 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="5f499-129">Windows Server 2012 및 Windows Server 2012 R2에는 Microsoft Media Foundation이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="5f499-130">전화 접속 회의의 포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f499-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="5f499-131">다음 표에서는 전화 접속 회의에 사용 되는 포트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-131">The following table describes the ports that are used by dial-in conferencing.</span></span> <span data-ttu-id="5f499-132">부하 분산 장치를 사용 하는 경우 풀에서 실행 되는 응용 프로그램에서 사용 되는 포트에 대해 부하 분산이 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-132">If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="5f499-133">이러한 포트는 **Set CsApplicationServer** cmdlet을 사용 하 여 변경할 수 있는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="5f499-134">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f499-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f499-135">풀에 있는 동일한 응용 프로그램의 모든 인스턴스가 동일한 SIP 수신 대기 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="5f499-136">전화 접속 회의에 사용 되는 포트</span><span class="sxs-lookup"><span data-stu-id="5f499-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f499-137">포트 번호</span><span class="sxs-lookup"><span data-stu-id="5f499-137">Port number</span></span></th>
<th><span data-ttu-id="5f499-138">설명</span><span class="sxs-lookup"><span data-stu-id="5f499-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f499-139">5072</span><span class="sxs-lookup"><span data-stu-id="5f499-139">5072</span></span></p></td>
<td><p><span data-ttu-id="5f499-140">SIP 수신 요청에 대해 회의 수행자 응용 프로그램에서 사용 됨</span><span class="sxs-lookup"><span data-stu-id="5f499-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f499-141">5073</span><span class="sxs-lookup"><span data-stu-id="5f499-141">5073</span></span></p></td>
<td><p><span data-ttu-id="5f499-142">SIP 수신 요청에 대해 회의 알림 응용 프로그램에서 사용 됨</span><span class="sxs-lookup"><span data-stu-id="5f499-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="5f499-143">전화 접속 회의를 위해 지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="5f499-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="5f499-144">다음 클라이언트를 사용 하 여 전화 접속 액세스를 지 원하는 온-프레미스 회의를 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="5f499-145">Lync 2013에 대 한 온라인 모임 추가 기능 (Lync 2013 또는 참석자를 설치할 때 자동으로 설치 됨)</span><span class="sxs-lookup"><span data-stu-id="5f499-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="5f499-146">전화 접속 회의 설정 페이지 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f499-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="5f499-147">전화 접속 회의 설정 페이지는 다음 표에 설명 된 운영 체제 및 웹 브라우저의 조합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f499-148">32 비트 및 64 비트 버전의 운영 체제가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="5f499-149">지원 되는 운영 체제 및 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="5f499-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f499-150">운영 체제</span><span class="sxs-lookup"><span data-stu-id="5f499-150">Operating system</span></span></th>
<th><span data-ttu-id="5f499-151">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="5f499-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f499-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="5f499-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="5f499-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="5f499-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="5f499-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="5f499-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="5f499-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="5f499-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f499-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5f499-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="5f499-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="5f499-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="5f499-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="5f499-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="5f499-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="5f499-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f499-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="5f499-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="5f499-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="5f499-161">Firefox</span></span></p>
<p><span data-ttu-id="5f499-162">Safari</span><span class="sxs-lookup"><span data-stu-id="5f499-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="5f499-163">전화 접속 회의를 위한 오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f499-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="5f499-164">Lync Server 2013는 전화 접속 회의를 위한 음성 프롬프트 및 음악 사용자 지정을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="5f499-165">그러나 기본 오디오 파일을 변경 해야 하는 강력한 비즈니스 요구 사항이 있는 경우 microsoft [Office Communications Server 2007 R2에서 전화 접속 오디오 회의에 대 한 음성 프롬프트 또는 음악 파일을 사용자 지정 하는 방법에 대 한](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)자세한 내용은 microsoft 기술 자료 문서 961177을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f499-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="5f499-166">또한 [Microsoft Lync Server 회의 수행자 사용자 지정 음성 메시지](http://go.microsoft.com/fwlink/p/?linkid=396880) 관리 유틸리티를 사용 하 여 전화 발신자가 사용자 지정 프롬프트를 사용 하 여 Lync 모임에 참가 하는 경우 다른 모임 입력 환경을 제공 하는 데 사용 되는 기본 음성 메시지를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="5f499-167">사용자 지정 음성 메시지는 Lync Server 2010 또는 Lync Server 2013 (Enterprise 또는 Standard Edition)를 실행 하는 서버에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="5f499-168">회의 수행자 응용 프로그램 및 회의 알림 신청에는 대기 중인 음악, 기록 된 이름 및 오디오 프롬프트 파일에 대 한 다음과 같은 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="5f499-169">WMA (Windows Media Audio) 파일 형식</span><span class="sxs-lookup"><span data-stu-id="5f499-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="5f499-170">16 비트 모노</span><span class="sxs-lookup"><span data-stu-id="5f499-170">16-bit mono</span></span>

  - <span data-ttu-id="5f499-171">48 kbps 2-CBR 통과 (상수 비트 전송률)</span><span class="sxs-lookup"><span data-stu-id="5f499-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="5f499-172">음성 수준-24DB</span><span class="sxs-lookup"><span data-stu-id="5f499-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="5f499-173">전화 접속 회의에 대 한 사용자 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5f499-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="5f499-174">전화 접속 회의 사용자는 자신의 계정에 고유한 전화번호 또는 내선 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="5f499-175">이 요구 사항은 전화 접속 회의 중에 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f499-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="5f499-176">엔터프라이즈 사용자 (즉, 조직 내 Active Directory 도메인 서비스 자격 증명 및 Lync Server 계정이 있는 사용자)의 전화 번호 (또는 확장명)와 PIN (개인 식별 번호)을 입력 하 여 다음 방법으로 회의에 전화를 걸 수 있습니다. 인증 된 사용자.</span><span class="sxs-lookup"><span data-stu-id="5f499-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

