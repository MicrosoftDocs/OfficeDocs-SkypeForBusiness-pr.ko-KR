---
title: 'Lync Server 2013: 할당 되지 않은 번호에 대 한 알림 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6442ed90050df22df77c41773619bedb5ee3ff72
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="81eb3-102">Lync Server 2013에서 할당 되지 않은 번호에 대 한 알림 구성</span><span class="sxs-lookup"><span data-stu-id="81eb3-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81eb3-103">_**마지막으로 수정 된 항목:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="81eb3-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="81eb3-104">알림 응용 프로그램은 할당 되지 않은 확장명 (조직에 적합 하지만 사용자나 전화에 할당 되지 않은 확장명)에 대 한 호출을 구성할 수 있도록 하는 Enterprise Voice 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="81eb3-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="81eb3-105">예를 들어 지정되지 않은 번호로의 통화에 대해 메시지를 재생하거나 다른 대상으로 전달하도록 구성하거나 이 두 가지를 모두 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81eb3-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="81eb3-106">알림 응용 프로그램은 Enterprise Voice를 배포할 때 프런트 엔드 서버 또는 Standard Edition 서버에 응답 그룹 응용 프로그램의 기능으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81eb3-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="81eb3-107">오디오 파일을 업로드하거나 TTS(텍스트 음성 변환)를 구성하고 지정되지 않은 번호 테이블을 구성하여 알림을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81eb3-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="81eb3-108">이 섹션에서는 Lync Server 알림을 구성 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="81eb3-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="81eb3-109">이 예제에서는 알림과 관련 된 계획 섹션을 이미 읽고 enterprise Edition 서버 또는 Standard Edition server를 엔터프라이즈 Voice와 함께 배포 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81eb3-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="81eb3-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="81eb3-110">In This Section</span></span>

  - [<span data-ttu-id="81eb3-111">Lync Server 2013의 알림 구성 선행 조건 및 역할</span><span class="sxs-lookup"><span data-stu-id="81eb3-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="81eb3-112">Lync Server 2013의 알림 응용 프로그램에 대 한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="81eb3-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="81eb3-113">Lync Server 2013에서 알림 만들기</span><span class="sxs-lookup"><span data-stu-id="81eb3-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="81eb3-114">Lync Server 2013에서 지정 되지 않은 번호 테이블 구성</span><span class="sxs-lookup"><span data-stu-id="81eb3-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="81eb3-115">반드시 Lync Server 2013에서 알림 배포 확인</span><span class="sxs-lookup"><span data-stu-id="81eb3-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81eb3-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81eb3-116">See Also</span></span>


[<span data-ttu-id="81eb3-117">Lync Server 2013의 통화 관리 기능 계획</span><span class="sxs-lookup"><span data-stu-id="81eb3-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

