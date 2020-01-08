---
title: 'Lync Server 2013: 응답 그룹에 대한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd87cb270d527753d9c6404ded4162791b542f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="895b7-102">Lync Server 2013의 응답 그룹에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="895b7-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="895b7-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="895b7-104">이 섹션에서는 응답 그룹 응용 프로그램에 대 한 다음과 같은 기술 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="895b7-105">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-105">Hardware requirements</span></span>

  - <span data-ttu-id="895b7-106">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-106">Software requirements</span></span>

  - <span data-ttu-id="895b7-107">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-107">Port requirements</span></span>

  - <span data-ttu-id="895b7-108">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-108">Audio file requirements</span></span>

  - <span data-ttu-id="895b7-109">응답 그룹 구성 도구 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="895b7-110">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-110">Hardware Requirements</span></span>

<span data-ttu-id="895b7-111">응답 그룹 응용 프로그램의 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="895b7-112">하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="895b7-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="895b7-113">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-113">Software Requirements</span></span>

<span data-ttu-id="895b7-114">응답 그룹 응용 프로그램에는 프런트 엔드 서버와 동일한 운영 체제 요구 사항 및 소프트웨어 필수 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="895b7-115">소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="895b7-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="895b7-116">응답 그룹 음악 및 알림에 대 한 Windows Media 오디오 (.wma) 파일을 사용 하는 경우 응답 그룹 응용 프로그램을 실행 하는 모든 프런트 엔드 서버 또는 Standard Edition 서버는 Windows를 실행 하는 서버에 대해 Windows Media 형식 런타임을 설치 해야 합니다. Windows Server 2012 또는 Windows Server 2012 R2를 실행 하는 서버의 경우 서버 2008 R2 또는 Microsoft 미디어 파운데이션.</span><span class="sxs-lookup"><span data-stu-id="895b7-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="895b7-117">Windows Server 2008 R2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="895b7-118">오디오 요구 사항에 대 한 자세한 내용은이 섹션의 뒷부분에 나오는 "오디오 파일 요구 사항"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="895b7-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="895b7-119">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-119">Port Requirements</span></span>

<span data-ttu-id="895b7-120">응답 그룹 응용 프로그램은 다음 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="895b7-121">\*\*\*\*   SIP 수신 요청에 사용 되는 포트 5071</span><span class="sxs-lookup"><span data-stu-id="895b7-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="895b7-122">\*\*\*\*   Interserver 통신에 사용 되는 포트 8404</span><span class="sxs-lookup"><span data-stu-id="895b7-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="895b7-123">이 포트는 일치 서비스에 사용 되며 응답 그룹 응용 프로그램이 프런트 엔드 서버가 두 개 이상 있는 풀에 배포 된 경우 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="895b7-124">이러한 포트는 <STRONG>Set CsApplicationServer</STRONG> cmdlet을 사용 하 여 변경할 수 있는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="895b7-125">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="895b7-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="895b7-126">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-126">Audio File Requirements</span></span>

<span data-ttu-id="895b7-127">응답 그룹 응용 프로그램은 응답 그룹 메시지, 대기 음악 또는 IVR (대화형 음성 응답) 질문에 대 한 웨이브 (.wav) 파일 형식과 Windows Media 오디오 (.wma) 파일 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="895b7-128">Windows Media 오디오 파일 형식의 경우 windows Media 형식 런타임이 Windows Server 2008 R2 및 Windows Server 2008를 실행 하는 프런트 엔드 서버에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="895b7-129">자세한 내용은이 섹션의 앞부분에 나오는 "소프트웨어 요구 사항"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="895b7-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="895b7-130">지원 되는 웨이브 파일 형식</span><span class="sxs-lookup"><span data-stu-id="895b7-130">Supported Wave File Formats</span></span>

<span data-ttu-id="895b7-131">모든 웨이브 파일은 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="895b7-132">8 비트 또는 16 비트 파일</span><span class="sxs-lookup"><span data-stu-id="895b7-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="895b7-133">LPCM (선형 펄스 코드 변조),-법률 또는 mu-사법 형식</span><span class="sxs-lookup"><span data-stu-id="895b7-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="895b7-134">모노 또는 스테레오</span><span class="sxs-lookup"><span data-stu-id="895b7-134">Mono or stereo</span></span>

  - <span data-ttu-id="895b7-135">4MB 이하의 경우</span><span class="sxs-lookup"><span data-stu-id="895b7-135">4MB or less</span></span>

<span data-ttu-id="895b7-136">웨이브 파일의 성능을 최적화 하기 위해 16Khz, 모노, 16 비트 웨이브 파일을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="895b7-137">지원 되는 Windows Media 오디오 파일 형식</span><span class="sxs-lookup"><span data-stu-id="895b7-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="895b7-138">Windows Media 오디오 파일을 사용 하는 경우 낮은 비트 전송률을 사용 하 고 로드 중인 시스템의 성능을 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="895b7-139">Microsoft Expression Encoder 4를 사용 하 여 파일을 Windows Media 오디오 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="895b7-140">식 인코더 4를 다운로드 하려면을 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="895b7-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="895b7-141">응답 그룹 구성 도구 요구 사항</span><span class="sxs-lookup"><span data-stu-id="895b7-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="895b7-142">응답 그룹 구성 도구는 다음 표에 설명 된 운영 체제 및 웹 브라우저의 조합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="895b7-143">32 비트 또는 64 비트 버전의 운영 체제가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-143">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="895b7-144">32 비트 버전의 Internet Explorer만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-144">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="895b7-145">지원 되는 운영 체제 및 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="895b7-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="895b7-146">운영 체제</span><span class="sxs-lookup"><span data-stu-id="895b7-146">Operating system</span></span></th>
<th><span data-ttu-id="895b7-147">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="895b7-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="895b7-148">Windows Vista 서비스 팩 (SP) 2</span><span class="sxs-lookup"><span data-stu-id="895b7-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="895b7-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="895b7-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="895b7-150">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-151">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="895b7-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="895b7-152">Windows 7</span></span></p>
<p><span data-ttu-id="895b7-153">Windows 7 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="895b7-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="895b7-154">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-155">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="895b7-156">Windows Server 2008 (서비스 팩 2)</span><span class="sxs-lookup"><span data-stu-id="895b7-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="895b7-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="895b7-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="895b7-158">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-159">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="895b7-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="895b7-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="895b7-161">Windows Server 2008 R2 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="895b7-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="895b7-162">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-163">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="895b7-164">응답 그룹 에이전트 콘솔</span><span class="sxs-lookup"><span data-stu-id="895b7-164">Response Group Agent Console</span></span>

<span data-ttu-id="895b7-165">에이전트 콘솔은 다음 표에 설명 된 운영 체제 및 웹 브라우저의 조합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="895b7-166">32 비트 또는 64 비트 버전의 운영 체제가 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-166">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="895b7-167">32 비트 버전의 Internet Explorer만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="895b7-167">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="895b7-168">지원 되는 운영 체제 및 웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="895b7-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="895b7-169">운영 체제</span><span class="sxs-lookup"><span data-stu-id="895b7-169">Operating system</span></span></th>
<th><span data-ttu-id="895b7-170">웹 브라우저</span><span class="sxs-lookup"><span data-stu-id="895b7-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="895b7-171">Windows Vista 서비스 팩 (SP) 2</span><span class="sxs-lookup"><span data-stu-id="895b7-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="895b7-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="895b7-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="895b7-173">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-174">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="895b7-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="895b7-175">Windows 7</span></span></p>
<p><span data-ttu-id="895b7-176">Windows 7 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="895b7-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="895b7-177">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-178">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="895b7-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="895b7-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="895b7-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="895b7-181">Windows Server 2008 (서비스 팩 2)</span><span class="sxs-lookup"><span data-stu-id="895b7-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="895b7-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="895b7-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="895b7-183">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-184">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="895b7-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="895b7-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="895b7-186">Windows Server 2008 R2 서비스 팩 1</span><span class="sxs-lookup"><span data-stu-id="895b7-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="895b7-187">Internet Explorer 8 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-188">Internet Explorer 9 (기본 모드)</span><span class="sxs-lookup"><span data-stu-id="895b7-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="895b7-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="895b7-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="895b7-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="895b7-190">Chrome 18.0</span></span></p></td>
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

