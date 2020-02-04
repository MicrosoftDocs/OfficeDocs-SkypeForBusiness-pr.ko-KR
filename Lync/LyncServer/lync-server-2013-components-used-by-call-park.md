---
title: 'Lync Server 2013: 통화 대기에 사용되는 구성 요소'
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
ms.openlocfilehash: ae458d7ef3245e366e4f2bdd61f192401909213b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="61f35-102">Lync Server 2013의 통화 대기에 사용되는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="61f35-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61f35-103">_**마지막으로 수정한 주제:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="61f35-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="61f35-104">전화 공원 응용 프로그램은 엔터프라이즈 음성을 배포할 때 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="61f35-105">음성 정책을 구성 하 여 통화 파킹 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="61f35-106">다음 Lync Server 2013 구성 요소는 통화 공원 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="61f35-107">**응용 프로그램 서비스**   응용 프로그램 서비스는 통화 공원 응용 프로그램과 같은 통합 커뮤니케이션 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="61f35-108">응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 모든 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="61f35-109">**통화 대기 응용**   프로그램 통화 공원 응용 프로그램은 응용 프로그램 서비스에 의해 호스팅되는 통합 커뮤니케이션 응용 프로그램 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="61f35-110">엔터프라이즈 음성을 구축할 때 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="61f35-111">대기 공원에서 통화를 검색 하 고 통화 공원 orbits를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="61f35-112">**음악-보류-파일**   음악을 사용 하는 경우, 통화가 파킹 되는 동안 음악 파일이 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="61f35-113">기본 음악 파일은 통화 공원 응용 프로그램이 설치 된 경우에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="61f35-114">**파일 저장소**   통화 공원 응용 프로그램에서 파일 저장소를 사용 하 여 사용자 지정 오디오 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="61f35-115">**Lync server 제어판**   lync server 제어판을 사용 하 여 통화 공원 표를 구성 하 고 사용자를 위한 통화 공원을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="61f35-116">**Lync server 관리 셸**   모든 통화 공원 응용 프로그램 구성은 Lync server management shell cmdlet을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61f35-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

