---
title: 비즈니스용 Skype에서 IIS 요청 추적 로그 파일 모니터링
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '요약: 레거시 클라이언트에 대 한 비즈니스용 Skype 서버 2015 지원의 모바일 서비스 (Mcx)에 대해 알아보세요.'
ms.openlocfilehash: f519a04f878caf953c54873a6a704232245b344b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992183"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="a467b-103">비즈니스용 Skype에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="a467b-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a467b-104">**요약:** 레거시 클라이언트에 대 한 비즈니스용 Skype 서버 2015 지원의 모바일 서비스 (Mcx)에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a467b-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="a467b-105">이 항목은 Lync 2010 Lync 모바일 클라이언트를 지 원하는 배포에 적용 되며, 모바일 서비스 (Mcx) 용으로 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="a467b-106">이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="a467b-107">현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="a467b-108">MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="a467b-109">Mcx (비즈니스용 Skype Server Mobility Service)에 대 한 IIS (인터넷 정보 서비스) 요청 추적을 사용 하도록 설정 하면 생성 되는 로그 파일은 하루에 최대 3gb의 디스크 공간을 소모할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="a467b-110">IIS 추적 로깅은 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="a467b-111">프런트 엔드 서버를 모니터링 하 여 디스크 공간이 부족 한지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="a467b-112">기본적으로 IIS 는%SystemDrive%\inetpub\logs\LogFiles.에서 로그 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="a467b-113">전체 서버에 대해 IIS 요청 추적을 해제 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a467b-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="a467b-114">**HttpLogging** 명령에 대 한 자세한 내용은 [명령 참조](https://go.microsoft.com/fwlink/p/?linkId=234927)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a467b-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

