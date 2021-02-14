---
title: 비즈니스용 Skype 서버에서 IIS 요청 추적 로그 파일 모니터링
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '요약: 레거시 클라이언트에 대한 비즈니스용 Skype 서버 2015 지원의 Mcx(Mobility Service)에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 5fb9e66efa468e8755fe369c3ce4f2a4b8979e57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823508"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a><span data-ttu-id="312c8-103">비즈니스용 Skype 서버에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="312c8-103">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="312c8-104">**요약:** 레거시 클라이언트에 대한 비즈니스용 Skype 서버 2015 지원의 Mcx(Mobility Service)에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-104">**Summary:** Learn about the Mobility Service (Mcx) in Skype for Business Server 2015 support for legacy clients.</span></span>
  
<span data-ttu-id="312c8-105">이 항목은 Lync 2010 Lync Mobile 클라이언트를 지원하는 배포에만 적용하며 Mcx(Mobility Service)를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-105">This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).</span></span>

> [!NOTE]
> <span data-ttu-id="312c8-106">레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-106">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="312c8-107">모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-107">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="312c8-108">MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-108">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="312c8-109">비즈니스용 Skype 서버 모바일 서비스(Mcx)에 대해 IIS(인터넷 정보 서비스) 요청 추적을 사용하도록 설정하면 생성되는 로그 파일은 하루에 최대 3기가바이트의 디스크 공간을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-109">When you enable Internet Information Services (IIS) request tracing for the Skype for Business Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="312c8-110">IIS 추적 로깅은 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-110">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="312c8-111">프런트 엔드 서버가 디스크 공간이 모두 손실되지 않는지 모니터링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-111">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span> 
  
<span data-ttu-id="312c8-112">IIS에서는 로그 파일이 기본적으로 %SystemDrive%\inetpub\logs\LogFiles에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-112">By default, IIS stores the log files at %SystemDrive%\inetpub\logs\LogFiles.</span></span>
  
<span data-ttu-id="312c8-113">전체 서버에 대해 IIS 요청 추적을 해제하려면 명령줄에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="312c8-113">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

<span data-ttu-id="312c8-114">**httpLogging** 명령에 대한 자세한 내용은 명령 [참조를 참고합니다.](https://go.microsoft.com/fwlink/p/?linkId=234927)</span><span class="sxs-lookup"><span data-stu-id="312c8-114">For details about the **httpLogging** command, see [the command reference](https://go.microsoft.com/fwlink/p/?linkId=234927).</span></span>
  

