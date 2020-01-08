---
title: 'Lync Server 2013: 통화 대기에 대한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c03c3b99e911766d2c60eec2a5515b3750d29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="8fd4c-102">Lync Server 2013의 통화 대기에 대한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fd4c-103">_**마지막으로 수정한 주제:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8fd4c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8fd4c-104">이 섹션에서는 통화 파킹에 대 한 다음과 같은 기술 요구 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="8fd4c-105">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-105">Hardware requirements</span></span>

  - <span data-ttu-id="8fd4c-106">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-106">Software requirements</span></span>

  - <span data-ttu-id="8fd4c-107">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-107">Port requirements</span></span>

  - <span data-ttu-id="8fd4c-108">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="8fd4c-109">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-109">Hardware Requirements</span></span>

<span data-ttu-id="8fd4c-110">통화 공원 응용 프로그램의 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="8fd4c-111">하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에 대 한 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="8fd4c-112">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-112">Software Requirements</span></span>

<span data-ttu-id="8fd4c-113">통화 공원 응용 프로그램에는 프런트 엔드 서버와 동일한 운영 체제 요구 사항 및 소프트웨어 필수 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="8fd4c-114">소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="8fd4c-115">통화 공원 응용 프로그램을 배포 하는 모든 프런트 엔드 서버와 Standard Edition 서버는 windows Server 2008 R2 또는 Windows Server 2012를 실행 하는 서버에 대 한 Microsoft Media Foundation을 실행 하는 서버용 Windows Media 형식 런타임을 설치 해야 합니다. Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="8fd4c-116">Windows Server 2008 R2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="8fd4c-117">Windows Media 오디오 (.wma) 파일에는 음악을 저장할 때 재생 되는 파킹에 대 한 기본 설정 또는 Microsoft Media Foundation이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="8fd4c-118">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-118">Port Requirements</span></span>

<span data-ttu-id="8fd4c-119">통화 공원 응용 프로그램은 다음 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="8fd4c-120">\*\*\*\*   SIP 수신 요청에 사용 되는 포트 5075.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fd4c-121">이 포트는 <STRONG>Set CsApplicationServer</STRONG> cmdlet을 사용 하 여 변경할 수 있는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="8fd4c-122">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="8fd4c-123">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="8fd4c-123">Audio File Requirements</span></span>

<span data-ttu-id="8fd4c-124">통화 공원 응용 프로그램은 음악을 저장할 때 Windows Media 오디오 (.wma) 파일만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="8fd4c-125">Microsoft Expression Encoder 4를 사용 하 여 음악을 저장할 때 파일을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="8fd4c-126">식 인코더 4를 다운로드 하려면에서 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)"식 인코더 4"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="8fd4c-127">이 도구를 사용 하 여 파일을 .wma 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="8fd4c-128">통화 대기 파일에 권장 되는 형식은 미디어 오디오 9, 44 kHz, 16 비트, 모노, CBR, 32 kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8fd4c-129">44 kHz에 녹음 한 경우에도 변환 된 파일은 휴대폰을 통해 16 kHz 에서만 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fd4c-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

