---
title: 'Lync Server 2013: 알림의 구성 필수 구성 요소 및 역할'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531695"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="8c256-102">Lync Server 2013의 알림 구성 선행 조건 및 역할</span><span class="sxs-lookup"><span data-stu-id="8c256-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c256-103">_**마지막으로 수정 된 항목:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="8c256-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="8c256-104">공지는 Enterprise Voice 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="8c256-105">이 항목에서는 알림 및 구성 작업을 수행 하는 데 필요한 역할 할당을 구성 하기 전에 필요한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="8c256-106">이 섹션에서는 공지 사항 관련 계획 설명서를 읽어야 하는 것으로 가정 합니다 ( [Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md)참조).</span><span class="sxs-lookup"><span data-stu-id="8c256-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="8c256-107">알림 구성 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8c256-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="8c256-108">알림 응용 프로그램을 사용 하려면 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="8c256-109">응용 프로그램 서비스</span><span class="sxs-lookup"><span data-stu-id="8c256-109">Application service</span></span>

  - <span data-ttu-id="8c256-110">응답 그룹 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="8c256-110">Response Group application</span></span>

  - <span data-ttu-id="8c256-111">오디오 파일을 보관할 파일 저장소</span><span class="sxs-lookup"><span data-stu-id="8c256-111">File Store, to hold audio files</span></span>

<span data-ttu-id="8c256-112">이러한 구성 요소는 모두 Enterprise Voice를 배포할 때 기본적으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="8c256-113">알림 구성 역할</span><span class="sxs-lookup"><span data-stu-id="8c256-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="8c256-114">다음 관리 도구를 사용하여 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="8c256-115">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="8c256-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="8c256-116">Lync Server 관리 셸</span><span class="sxs-lookup"><span data-stu-id="8c256-116">Lync Server Management Shell</span></span>

<span data-ttu-id="8c256-117">알림 응용 프로그램을 구성 하려면 다음 관리 역할 중 하나가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="8c256-118">**CsVoiceAdministrator**     이 관리자 역할은 알림 설정을 비롯 하 여 모든 음성 관련 설정 및 정책을 만들고 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="8c256-119">**Csserveradministrator**     이 관리자 역할은 서버 및 서비스를 관리 및 모니터링 하 고 문제를 해결 하 고 모든 알림 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="8c256-120">**Csadministrator**     이 관리자 역할은 모든 관리 작업을 수행 하 고 모든 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="8c256-121">**Csviewonly 관리자**     이 관리자 역할은 배포를 보고 배포 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c256-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c256-122">관리 사용자 권한에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어 계획</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c256-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c256-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c256-123">See Also</span></span>


[<span data-ttu-id="8c256-124">Lync Server 2013에서 Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="8c256-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="8c256-125">Lync Server 2013의 통화 관리 기능 계획</span><span class="sxs-lookup"><span data-stu-id="8c256-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

