---
title: 'Lync Server 2013: 알림 신청 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2b1e9f8dd78b299a8e89e958f5b1c03acdffb7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="5d261-102">Lync Server 2013의 알림 신청에 대 한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="5d261-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d261-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5d261-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5d261-104">이 섹션에서는 알림 신청 배포 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d261-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="5d261-105">알림을 구성 하기 전에 엔터프라이즈 음성을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d261-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="5d261-106">엔터프라이즈 음성을 구축할 때 알림 응용 프로그램에 필요한 구성 요소를 설치 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d261-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="5d261-107">알림 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="5d261-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d261-108">단계의</span><span class="sxs-lookup"><span data-stu-id="5d261-108">Phase</span></span></th>
<th><span data-ttu-id="5d261-109">방법은</span><span class="sxs-lookup"><span data-stu-id="5d261-109">Steps</span></span></th>
<th><span data-ttu-id="5d261-110">역할</span><span class="sxs-lookup"><span data-stu-id="5d261-110">Roles</span></span></th>
<th><span data-ttu-id="5d261-111">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="5d261-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d261-112">알림 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5d261-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5d261-113">오디오 파일을 기록 및 업로드 하거나 텍스트 음성 변환 (TTS)을 사용 하 여 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d261-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="5d261-114">지정 하지 않은 번호 표에서 할당 되지 않은 번호 범위를 구성 하 고 적절 한 공지와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d261-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d261-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5d261-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5d261-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d261-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5d261-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d261-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5d261-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5d261-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="5d261-119">Csviewadministrator</span><span class="sxs-lookup"><span data-stu-id="5d261-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5d261-120"><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013에서 알림 만들기</a></span><span class="sxs-lookup"><span data-stu-id="5d261-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5d261-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Lync Server 2013에서 지정되지 않은 번호 테이블 구성</a></span><span class="sxs-lookup"><span data-stu-id="5d261-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d261-122">공지 사항 배포 확인</span><span class="sxs-lookup"><span data-stu-id="5d261-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="5d261-123">알림을 청취 하 여 테스트를 수행 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d261-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="5d261-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">) Lync Server 2013에서 알림 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="5d261-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

