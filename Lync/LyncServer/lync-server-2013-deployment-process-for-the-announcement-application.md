---
title: 'Lync Server 2013: 알림 응용 프로그램 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6282c77a93097ad09aae91dcaf493cf8b7de6f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="67686-102">Lync Server 2013의 알림 응용 프로그램에 대 한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="67686-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67686-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="67686-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="67686-104">이 섹션에서는 알림 응용 프로그램 배포와 관련 된 단계를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="67686-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="67686-105">알림을 구성 하기 전에 Enterprise Voice를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67686-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="67686-106">Enterprise Voice를 배포할 때 알림 응용 프로그램에 필요한 구성 요소를 설치 하 고 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="67686-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="67686-107">알림 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="67686-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67686-108">단계</span><span class="sxs-lookup"><span data-stu-id="67686-108">Phase</span></span></th>
<th><span data-ttu-id="67686-109">단계</span><span class="sxs-lookup"><span data-stu-id="67686-109">Steps</span></span></th>
<th><span data-ttu-id="67686-110">역할</span><span class="sxs-lookup"><span data-stu-id="67686-110">Roles</span></span></th>
<th><span data-ttu-id="67686-111">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="67686-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67686-112">알림 설정 구성</span><span class="sxs-lookup"><span data-stu-id="67686-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="67686-113">오디오 파일을 녹음하여 업로드하거나 TTS(텍스트 음성 변환)를 사용하여 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67686-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="67686-114">지정되지 않은 번호 표의 지정되지 않은 번호 범위를 구성하여 적절한 알림과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="67686-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="67686-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="67686-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="67686-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="67686-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="67686-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="67686-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="67686-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="67686-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="67686-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="67686-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="67686-120"><a href="lync-server-2013-create-an-announcement.md">Lync Server 2013에서 알림 만들기</a></span><span class="sxs-lookup"><span data-stu-id="67686-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="67686-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Lync Server 2013에서 지정 되지 않은 번호 테이블 구성</a></span><span class="sxs-lookup"><span data-stu-id="67686-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67686-122">알림 배포 확인</span><span class="sxs-lookup"><span data-stu-id="67686-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="67686-123">알림 듣기를 테스트하여 구성이 제대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67686-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="67686-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">반드시 Lync Server 2013에서 알림 배포 확인</a></span><span class="sxs-lookup"><span data-stu-id="67686-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

