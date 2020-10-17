---
title: 'Lync Server 2013: 응답 그룹에 대 한 기술 요구 사항'
description: 'Lync Server 2013: 응답 그룹에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3125ed8c732960e23970229e99bf5a8487eb96a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550324"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="2f6c3-103">Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-103">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f6c3-104">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="2f6c3-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="2f6c3-105">이 섹션에서는 응답 그룹 응용 프로그램에 대 한 다음 기술 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-105">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="2f6c3-106">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-106">Hardware requirements</span></span>

  - <span data-ttu-id="2f6c3-107">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-107">Software requirements</span></span>

  - <span data-ttu-id="2f6c3-108">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-108">Port requirements</span></span>

  - <span data-ttu-id="2f6c3-109">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-109">Audio file requirements</span></span>

  - <span data-ttu-id="2f6c3-110">응답 그룹 구성 도구 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-110">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="2f6c3-111">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-111">Hardware Requirements</span></span>

<span data-ttu-id="2f6c3-112">응답 그룹 응용 프로그램의 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-112">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="2f6c3-113">하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [server 하드웨어 플랫폼 For Lync server 2013](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="2f6c3-114">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-114">Software Requirements</span></span>

<span data-ttu-id="2f6c3-115">응답 그룹 응용 프로그램은 프런트 엔드 서버와 동일한 운영 체제 요구 사항 및 소프트웨어 필수 구성 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-115">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="2f6c3-116">소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-116">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="2f6c3-117">응답 그룹 음악 및 알림에 대해 Windows Media 오디오 (.wma) 파일을 사용 하는 경우 응답 그룹 응용 프로그램을 실행 하는 모든 프런트 엔드 서버 또는 Standard Edition 서버에 windows Server 2008 R2를 실행 하는 서버 또는 Windows server 2012 또는 Windows Server 2012 r 2를 실행 하는 서버에 대 한 Microsoft Media Foundation이 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-117">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="2f6c3-118">Windows Server 2008 R2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-118">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="2f6c3-119">오디오 요구 사항에 대한 자세한 내용은 이 섹션의 뒷 부분에 나오는 "오디오 파일 요구 사항"을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-119">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="2f6c3-120">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-120">Port Requirements</span></span>

<span data-ttu-id="2f6c3-121">응답 그룹 응용 프로그램은 다음 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-121">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="2f6c3-122">**포트 5071**     SIP 수신 대기 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-122">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="2f6c3-123">**포트 8404**     8404 communications에 사용 됨</span><span class="sxs-lookup"><span data-stu-id="2f6c3-123">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2f6c3-124">이 포트는 일치 서비스에 사용 되며, 응답 그룹 응용 프로그램을 프런트 엔드 서버가 두 개 이상 있는 풀에 배포 하는 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-124">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="2f6c3-125">이러한 포트는 <STRONG>Set-CsApplicationServer</STRONG> cmdlet을 사용하여 변경할 수 있는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-125">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="2f6c3-126">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-126">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="2f6c3-127">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-127">Audio File Requirements</span></span>

<span data-ttu-id="2f6c3-128">응답 그룹 응용 프로그램은 응답 그룹 메시지, 대기 음악 또는 IVR (대화형 음성 응답) 질문에 대 한 웨이브 (.wav) 파일 형식과 Windows Media 오디오 (.wma) 파일 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-128">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="2f6c3-129">Windows Media 오디오 파일 형식을 사용 하려면 windows Media 형식 런타임이 Windows Server 2008 R2 및 Windows Server 2008를 실행 하는 프런트 엔드 서버에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-129">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="2f6c3-130">자세한 내용은 이 섹션의 앞 부분에 있는 "소프트웨어 요구 사항"을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-130">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="2f6c3-131">지원되는 웨이브 파일 형식</span><span class="sxs-lookup"><span data-stu-id="2f6c3-131">Supported Wave File Formats</span></span>

<span data-ttu-id="2f6c3-132">모든 웨이브 파일은 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-132">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="2f6c3-133">8비트 또는 16비트 파일</span><span class="sxs-lookup"><span data-stu-id="2f6c3-133">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="2f6c3-134">LPCM(선형 펄스 부호 변조), A-Law 또는 mu-Law 형식</span><span class="sxs-lookup"><span data-stu-id="2f6c3-134">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="2f6c3-135">모노 또는 스테레오</span><span class="sxs-lookup"><span data-stu-id="2f6c3-135">Mono or stereo</span></span>

  - <span data-ttu-id="2f6c3-136">4MB 이하</span><span class="sxs-lookup"><span data-stu-id="2f6c3-136">4MB or less</span></span>

<span data-ttu-id="2f6c3-137">최상의 웨이브 파일 성능을 위해서는 16kHz/모노/16비트의 웨이브 파일을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-137">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="2f6c3-138">지원되는 Windows Media 오디오 파일 형식</span><span class="sxs-lookup"><span data-stu-id="2f6c3-138">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="2f6c3-139">Windows Media 오디오 파일을 사용할 경우 낮은 비트 전송률을 사용하고 시스템 성능이 정상인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-139">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="2f6c3-140">Microsoft Expression Encoder 4를 사용하여 파일을 Windows Media 오디오 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-140">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="2f6c3-141">수식 인코더 4를 다운로드 하려면를 참조 하세요 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="2f6c3-141">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="2f6c3-142">응답 그룹 구성 도구 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f6c3-142">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="2f6c3-143">응답 그룹 구성 도구는 다음 표에 설명 된 운영 체제 및 웹 브라우저의 조합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-143">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f6c3-p107">32비트 또는 64비트 버전의 운영 체제가 지원됩니다. 32비트 버전의 Internet Explorer만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="2f6c3-146">지원되는 운영 체제 및 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="2f6c3-146">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f6c3-147">운영 체제</span><span class="sxs-lookup"><span data-stu-id="2f6c3-147">Operating system</span></span></th>
<th><span data-ttu-id="2f6c3-148">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="2f6c3-148">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f6c3-149">Windows Vista SP(서비스 팩) 2</span><span class="sxs-lookup"><span data-stu-id="2f6c3-149">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-150">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="2f6c3-150">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="2f6c3-151">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-151">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-152">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-152">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f6c3-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="2f6c3-153">Windows 7</span></span></p>
<p><span data-ttu-id="2f6c3-154">Windows 7 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="2f6c3-154">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-155">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-155">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-156">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-156">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f6c3-157">Windows Server 2008 서비스 팩 2</span><span class="sxs-lookup"><span data-stu-id="2f6c3-157">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-158">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="2f6c3-158">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="2f6c3-159">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-159">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-160">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-160">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f6c3-161">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2f6c3-161">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="2f6c3-162">Windows Server 2008 R2 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="2f6c3-162">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-163">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-163">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-164">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-164">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="2f6c3-165">응답 그룹 에이전트 콘솔</span><span class="sxs-lookup"><span data-stu-id="2f6c3-165">Response Group Agent Console</span></span>

<span data-ttu-id="2f6c3-166">에이전트 콘솔은 다음 표에 설명된 운영 체제 및 웹 브라우저의 조합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-166">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2f6c3-p108">32비트 또는 64비트 버전의 운영 체제가 지원됩니다. 32비트 버전의 Internet Explorer만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f6c3-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="2f6c3-169">지원되는 운영 체제 및 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="2f6c3-169">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2f6c3-170">운영 체제</span><span class="sxs-lookup"><span data-stu-id="2f6c3-170">Operating system</span></span></th>
<th><span data-ttu-id="2f6c3-171">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="2f6c3-171">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f6c3-172">Windows Vista SP(서비스 팩) 2</span><span class="sxs-lookup"><span data-stu-id="2f6c3-172">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-173">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="2f6c3-173">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="2f6c3-174">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-174">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-175">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-175">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f6c3-176">Windows 7</span><span class="sxs-lookup"><span data-stu-id="2f6c3-176">Windows 7</span></span></p>
<p><span data-ttu-id="2f6c3-177">Windows 7 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="2f6c3-177">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-178">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-178">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-179">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-179">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-180">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="2f6c3-180">Firefox 10.0</span></span></p>
<p><span data-ttu-id="2f6c3-181">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="2f6c3-181">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f6c3-182">Windows Server 2008 서비스 팩 2</span><span class="sxs-lookup"><span data-stu-id="2f6c3-182">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-183">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="2f6c3-183">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="2f6c3-184">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-184">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-185">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-185">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f6c3-186">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2f6c3-186">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="2f6c3-187">Windows Server 2008 R2 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="2f6c3-187">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="2f6c3-188">Internet Explorer 8(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-188">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-189">Internet Explorer 9(기본 모드)</span><span class="sxs-lookup"><span data-stu-id="2f6c3-189">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="2f6c3-190">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="2f6c3-190">Firefox 10.0</span></span></p>
<p><span data-ttu-id="2f6c3-191">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="2f6c3-191">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

