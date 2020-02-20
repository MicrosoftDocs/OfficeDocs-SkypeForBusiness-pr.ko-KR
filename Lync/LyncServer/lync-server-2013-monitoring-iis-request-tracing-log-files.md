---
title: 'Lync Server 2013: IIS 요청 추적 로그 파일 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring IIS request tracing log files
ms:assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690034(v=OCS.15)
ms:contentKeyID: 48185215
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1377eabd4ffc199fe7a9014d28f153aba10afa4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-iis-request-tracing-log-files-in-lync-server-2013"></a><span data-ttu-id="4d932-102">Lync Server 2013에서 IIS 요청 추적 로그 파일 모니터링</span><span class="sxs-lookup"><span data-stu-id="4d932-102">Monitoring IIS request tracing log files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d932-103">_**마지막으로 수정 된 항목:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="4d932-103">_**Topic Last Modified:** 2013-02-14_</span></span>

    This topic applies to deployments supporting Lync 2010 Lync Mobile clients only, and is intended for the Mobility Service (Mcx).

<span data-ttu-id="4d932-104">Mcx (Lync Server Mobility Service)에 대 한 IIS (인터넷 정보 서비스) 요청 추적을 사용 하도록 설정 하면 생성 되는 로그 파일은 하루에 최대 3gb의 디스크 공간을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d932-104">When you enable Internet Information Services (IIS) request tracing for the Lync Server Mobility Service (Mcx), the log files that are generated can consume up to three gigabytes of disk space per day.</span></span> <span data-ttu-id="4d932-105">IIS 추적 로깅은 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d932-105">IIS trace logging is enabled by default.</span></span> <span data-ttu-id="4d932-106">프런트 엔드 서버를 모니터링 하 여 디스크 공간이 부족 하지 않은지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d932-106">You should monitor the Front End Servers to make sure that they do not run out of disk space.</span></span>

<span data-ttu-id="4d932-107">기본적으로 IIS 는%\\inetpub\\\\%의 로그 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d932-107">By default, IIS stores the log files at %SystemDrive%\\inetpub\\logs\\LogFiles.</span></span>

<span data-ttu-id="4d932-108">전체 서버에 대해 IIS 요청 추적을 해제하려면 명령줄에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4d932-108">To turn off IIS request tracing for an entire server, at the command line, type the following:</span></span>

    %SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True

<span data-ttu-id="4d932-109">**HttpLogging** 명령에 대 한 자세한 내용은를 [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d932-109">For details about the **httpLogging** command, see [https://go.microsoft.com/fwlink/p/?linkId=234927](https://go.microsoft.com/fwlink/p/?linkid=234927).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

