---
title: 'Lync Server 2013: 알림 응용 프로그램에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8687c5b9c5f422994817910eec640cc795798d18
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="81dc8-102">Lync Server 2013의 알림 응용 프로그램에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81dc8-103">_**마지막으로 수정 된 항목:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="81dc8-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="81dc8-104">이 섹션에서는 알림 응용 프로그램에 대 한 다음과 같은 기술 요구 사항을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="81dc8-105">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-105">Hardware requirements</span></span>

  - <span data-ttu-id="81dc8-106">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-106">Software requirements</span></span>

  - <span data-ttu-id="81dc8-107">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-107">Port requirements</span></span>

  - <span data-ttu-id="81dc8-108">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="81dc8-109">하드웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-109">Hardware Requirements</span></span>

<span data-ttu-id="81dc8-110">알림 응용 프로그램의 하드웨어 요구 사항은 프런트 엔드 서버와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="81dc8-111">하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [server 하드웨어 플랫폼 For Lync server 2013](lync-server-2013-server-hardware-platforms.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="81dc8-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="81dc8-112">소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-112">Software Requirements</span></span>

<span data-ttu-id="81dc8-113">알림 응용 프로그램은 프런트 엔드 서버와 동일한 운영 체제 요구 사항 및 소프트웨어 필수 구성 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="81dc8-114">소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 서버 및 도구 운영 체제 지원을](lync-server-2013-server-and-tools-operating-system-support.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="81dc8-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="81dc8-115">알림 응용 프로그램을 실행 하는 모든 프런트 엔드 서버 또는 Standard Edition 서버에는 windows Server 2008 R2 또는 Windows Server 2012을 실행 하는 서버에 대해 Microsoft Media Foundation을 실행 하는 서버에 대해 Windows Media 형식 런타임이 설치 되어 있어야 합니다. Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="81dc8-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="81dc8-116">Windows Server 2008 r 2의 경우 windows Media 형식 런타임이 Windows 데스크톱 환경의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="81dc8-117">Windows Media 형식 런타임 또는 Microsoft Media Foundation은 알림 응용 프로그램이 공지 사항 및 음악에 대해 재생 하는 Windows Media 오디오 (.wma) 파일에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="81dc8-118">포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-118">Port Requirements</span></span>

<span data-ttu-id="81dc8-119">알림 응용 프로그램은 다음 포트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="81dc8-120">\*\*\*\*   SIP 수신 대기 요청에 사용 되는 포트 5071</span><span class="sxs-lookup"><span data-stu-id="81dc8-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81dc8-121">이 포트는 기본 설정이며 <STRONG>Set-CsApplicationServer</STRONG> cmdlet을 사용하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="81dc8-122">이 cmdlet에 대 한 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="81dc8-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="81dc8-123">오디오 파일 요구 사항</span><span class="sxs-lookup"><span data-stu-id="81dc8-123">Audio File Requirements</span></span>

<span data-ttu-id="81dc8-124">알림 응용 프로그램은 음악 및 알림에 대 한 웨이브 (.wav) 파일 형식과 Windows Media 오디오 (.wma) 파일 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="81dc8-125">알림 응용 프로그램에 대 한 오디오 파일 요구 사항은 응답 그룹 응용 프로그램의 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="81dc8-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="81dc8-126">자세한 내용은 [Lync Server 2013의 응답 그룹에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-response-group.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81dc8-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

