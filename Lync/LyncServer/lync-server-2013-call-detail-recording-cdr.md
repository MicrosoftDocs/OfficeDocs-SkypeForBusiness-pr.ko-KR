---
title: 'Lync Server 2013: CDR (통화 정보 기록)'
description: 'Lync Server 2013: CDR (통화 정보 기록)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call detail recording (CDR)
ms:assetid: 67726075-c77c-4191-a64f-a1cf5c7bcbb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688079(v=OCS.15)
ms:contentKeyID: 49733675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590f99fd0b8649ffb3c4df039488dc54a8f3b7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561794"
---
# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="ef5bc-103">Lync Server 2013의 CDR (통화 정보 기록)</span><span class="sxs-lookup"><span data-stu-id="ef5bc-103">Call detail recording (CDR) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef5bc-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="ef5bc-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="ef5bc-105">CDR(통화 정보 기록)은 인스턴스 메시징, VoIP(Voice over Internet Protocol) 통화, 응용 프로그램 공유, 파일 전송, 모임 등의 피어 투 피어 활동에 대한 사용 및 진단 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ef5bc-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="ef5bc-106">이러한 사용 데이터는 ROI(투자 수익)를 계산하는 데 사용하고, 진단 데이터는 피어 투 피어 활동 및 모임 관련 문제를 해결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef5bc-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="ef5bc-107">Lync Server 2013을 설치할 때 CDR에 대해 미리 정의 된 전역 구성 설정 모음도 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef5bc-107">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="ef5bc-108">이 섹션의 항목을 사용해서 CDR을 구성하십시오.</span><span class="sxs-lookup"><span data-stu-id="ef5bc-108">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ef5bc-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ef5bc-109">In This Section</span></span>

  - [<span data-ttu-id="ef5bc-110">Lync Server 2013에서 CDR 구성 정보 보기</span><span class="sxs-lookup"><span data-stu-id="ef5bc-110">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="ef5bc-111">Lync Server 2013에서 통화 정보 기록 사용</span><span class="sxs-lookup"><span data-stu-id="ef5bc-111">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="ef5bc-112">Lync Server 2013에서 CDR 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="ef5bc-112">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="ef5bc-113">Lync Server 2013에서 기존 CDR 구성 설정 모음 삭제</span><span class="sxs-lookup"><span data-stu-id="ef5bc-113">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="ef5bc-114">Lync Server 2013에서 통화 정보 기록 및 경험 수준 데이터베이스를 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="ef5bc-114">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef5bc-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef5bc-115">See Also</span></span>


[<span data-ttu-id="ef5bc-116">Lync Server 2013에서 통화 정보 기록 및 경험 수준 설정 구성</span><span class="sxs-lookup"><span data-stu-id="ef5bc-116">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

