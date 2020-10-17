---
title: 'Lync Server 2013: 디스크 사용량 확인'
description: 'Lync Server 2013: 디스크 사용 현황을 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7eddde772d156f0a416dab381efe1ab33ee202f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571004"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="4f1df-103">Lync Server 2013에서 디스크 사용 확인</span><span class="sxs-lookup"><span data-stu-id="4f1df-103">Checking disk usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f1df-104">_**마지막으로 수정 된 항목:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="4f1df-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="4f1df-105">하드 디스크 드라이브는 Lync Server 2013 배포의 중요 한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-105">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="4f1df-106">충분 한 여유 디스크 볼륨이 없으면 운영 체제와 Lync Server 2013 데이터베이스 모두 올바르게 작동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-106">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="4f1df-107">매일 Lync Server 2013 백 엔드 데이터베이스 통계를 모니터링 하 여 서버에 디스크 공간이 부족 한 상태를 유지 하 고 필요에 따라 저장소 리소스를 추가 하는 준비를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-107">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="4f1df-108">운영 체제, 프로그램 파일, 데이터베이스 및 트랜잭션 로그를 호스트 하는 디스크의 공간을 검사 하는 것 외에도 Lync Server 2013 백 엔드)에서는 다음과 같은 중요 한 데이터를 포함 하는 파일 공유에 대 한 디스크 공간이 포함 된 파일 시스템의 사용을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-108">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="4f1df-109">모임 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="4f1df-109">Meeting content</span></span>

  - <span data-ttu-id="4f1df-110">모임 콘텐츠 메타 데이터</span><span class="sxs-lookup"><span data-stu-id="4f1df-110">Meeting content metadata</span></span>

  - <span data-ttu-id="4f1df-111">모임 준수 로그</span><span class="sxs-lookup"><span data-stu-id="4f1df-111">Meeting compliance logs</span></span>

  - <span data-ttu-id="4f1df-112">응용 프로그램 데이터 파일 (응용 프로그램 서버 구성 요소에서 내부적으로 사용 됨)</span><span class="sxs-lookup"><span data-stu-id="4f1df-112">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="4f1df-113">그룹 채팅 서버 웹 서비스 및 규정 준수 폴더 (그룹 채팅 웹 서비스에 업로드 된 파일을 저장 하기 위해)</span><span class="sxs-lookup"><span data-stu-id="4f1df-113">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="4f1df-114">그룹 채팅 준수 XML 파일 (그룹 채팅 준수 기록 포함)</span><span class="sxs-lookup"><span data-stu-id="4f1df-114">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="4f1df-115">업데이트 파일 (장치 업데이트 서비스용)</span><span class="sxs-lookup"><span data-stu-id="4f1df-115">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="4f1df-116">주소록 파일</span><span class="sxs-lookup"><span data-stu-id="4f1df-116">Address Book files</span></span>

<span data-ttu-id="4f1df-117">Lync Server 2013에는 이전에 나열 된 파일 공유에 있는 파일 외에도 데이터베이스 및 트랜잭션 로그를 저장 하기 위한 하드 디스크 공간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-117">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="4f1df-118">저장소 리소스가 부족 하 여 Lync Server 2013 배포가 영향을 받지 않도록 하기 위해 정기적으로 디스크 공간을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-118">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="4f1df-119">각 Lync Server 2013 볼륨의 사용 가능한 디스크 공간에 대 한 통계 정보와 데이터베이스 및 트랜잭션 로그 파일의 예상 증가를 비교 하 고 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-119">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="4f1df-120">이렇게 하면 저장소 리소스가 필요할 때 용량 계획을 수립 하 고 저장소를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-120">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="4f1df-121">문제 해결 및 재해 복구 상황을 수용할 수 있도록 하려면 사용 가능한 볼륨 공간이 데이터베이스 크기의 110% 보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-121">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="4f1df-122">다음 방법을 사용하여 사용 가능한 디스크 공간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-122">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="4f1df-123">**System Center Operations Manager**     System Center Operations Manager를 사용 하 여 볼륨 공간이 제한 되어 있을 때 관리자에 게 경고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-123">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="4f1df-124">**스크립트 실행**     사용 가능한 하드 디스크 공간이 20% 미만이 면 메시지를 보내는 스크립트를 실행 하 여 디스크 공간을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-124">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="4f1df-125">TechNet의 Microsoft 스크립트 센터에서 예제 스크립트를 찾을 수 있습니다. [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="4f1df-125">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="4f1df-126">**Windows 탐색기**     Windows 탐색기를 사용 하 여 Lync Server 2013 로그 및 데이터베이스를 저장 하는 볼륨에서 디스크 공간을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f1df-126">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

