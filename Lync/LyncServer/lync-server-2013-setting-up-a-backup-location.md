---
title: 'Lync Server 2013: 백업 위치 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fe9ddd835d569aca129d53de2a44e2a00b39794
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="fb691-102">Lync Server 2013의 백업 위치 설정</span><span class="sxs-lookup"><span data-stu-id="fb691-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb691-103">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="fb691-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="fb691-104">Lync Server의 첫 번째 백업을 수행 하기 전에 백업을 저장 하 고 유지 관리 하기 위해 필요한 하드웨어 및 소프트웨어를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb691-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="fb691-105">필요에 따라 미디어 및 콘텐츠에 대한 액세스 권한을 얻고 백업할 각 서버와 백업 미디어 간의 네트워크 연결을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb691-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="fb691-106">사용 하는 미디어와 위치는 백업 및 복원 전략에서 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb691-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="fb691-107">일반 백업에 사용 하는 위치는 로컬 또는 원격 일 수 있지만 안전 하며 백업 및 복원에 대 한 액세스 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb691-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="fb691-108">기본 사이트에서 치명적 이벤트 로부터 보호 하려면 원격 위치를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fb691-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="fb691-109">개별 구성 요소를 설정 및 테스트한 후에는 각 서버에서 백업에 대한 접근성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fb691-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

