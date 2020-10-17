---
title: 'Lync Server 2013: 통화 대기에 사용 되는 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21335597f0910e18a5afe36898c7d0eff6c1a338
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502395"
---
# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="62000-102">Lync Server 2013의 통화 대기에 사용 되는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="62000-102">Components used by Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62000-103">_**마지막으로 수정 된 항목:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="62000-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="62000-104">통화 대기 응용 프로그램은 Enterprise Voice를 배포할 때 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62000-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="62000-105">음성 정책을 구성 하 여 통화 대기를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="62000-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="62000-106">다음 Lync Server 2013 구성 요소는 통화 대기 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="62000-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="62000-107">**응용 프로그램 서비스**     응용 프로그램 서비스는 통화 대기 응용 프로그램 등의 통합 통신 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="62000-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="62000-108">응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 모든 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62000-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="62000-109">**통화 대기 응용 프로그램**     통화 대기 응용 프로그램은 응용 프로그램 서비스에서 호스팅하는 통합 통신 응용 프로그램 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="62000-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="62000-110">Enterprise Voice를 배포할 때 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62000-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="62000-111">통화 대기 공원를 검색 하 고 통화 대기 궤도를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="62000-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="62000-112">**음악-보류-파일**     음악을 사용 하는 경우 통화가 파킹 되는 동안 음악 파일이 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62000-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="62000-113">기본 음악 파일은 통화 대기 응용 프로그램을 설치할 때 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62000-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="62000-114">**파일 저장소**     통화 대기 응용 프로그램은 파일 저장소를 사용 하 여 사용자 지정 오디오 파일을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="62000-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="62000-115">**Lync Server 제어판**     Lync Server 제어판을 사용 하 여 통화 대기 궤도 테이블을 구성 하 고 사용자에 대해 통화 대기를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62000-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="62000-116">**Lync Server 관리 셸**     모든 통화 대기 응용 프로그램 구성은 Lync Server 관리 셸 cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62000-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

