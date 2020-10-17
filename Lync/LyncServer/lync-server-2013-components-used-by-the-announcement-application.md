---
title: 'Lync Server 2013: 알림 응용 프로그램에서 사용 되는 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84fb2d57e03965acff9d647854b86d7a5a528246
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517715"
---
# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="37407-102">Lync Server 2013의 알림 응용 프로그램에서 사용 되는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="37407-102">Components used by the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37407-103">_**마지막으로 수정 된 항목:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="37407-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="37407-104">Lync Server 2013에서 알림 응용 프로그램은 응답 그룹 응용 프로그램의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="37407-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="37407-105">Enterprise Voice를 배포 하면 알림 응용 프로그램이 자동으로 설치 되 고 응답 그룹 응용 프로그램과 함께 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37407-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="37407-106">이 섹션에서는 알림 응용 프로그램을 지 원하는 구성 요소에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="37407-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="37407-107">알림 응용 프로그램 구성 요소</span><span class="sxs-lookup"><span data-stu-id="37407-107">Announcement Application Components</span></span>

<span data-ttu-id="37407-108">다음 Lync Server 구성 요소는 알림 응용 프로그램을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="37407-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="37407-109">**응용 프로그램 서비스**     응용 프로그램 서비스는 통합 커뮤니케이션 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37407-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="37407-110">응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 모든 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37407-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="37407-111">**응답 그룹 응용 프로그램**     응답 그룹 응용 프로그램은 응용 프로그램 서비스에서 호스팅하는 통합 통신 응용 프로그램 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="37407-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="37407-112">지정 되지 않은 전화 번호 범위가 알림에 라우팅되도록 구성 된 경우 응답 그룹 응용 프로그램은 전화 번호에 대 한 통화를 라우팅하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="37407-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="37407-113">모든 범위가 Exchange UM (통합 메시징)으로 라우팅되도록 구성 된 경우에는 응답 그룹 응용 프로그램이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37407-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="37407-114">**오디오 파일**     오디오 파일은 알림에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37407-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="37407-115">**파일 저장소**     알림 응용 프로그램은 파일 저장소를 사용 하 여 오디오 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="37407-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="37407-116">**Lync Server 제어판**     Lync Server 제어판을 사용 하 여 지정 되지 않은 번호 테이블을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37407-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="37407-117">**Lync Server 관리 셸**     Lync Server 관리 셸 cmdlet을 사용 하 여 알림 설정 및 할당 되지 않은 번호 테이블을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37407-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

