---
title: 'Lync Server 2013: 백업 위치 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6d8f91af650e68348a35e9f485f5ca5f54093fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="4b436-102">Lync Server 2013의 백업 위치 설정</span><span class="sxs-lookup"><span data-stu-id="4b436-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b436-103">_**마지막으로 수정한 주제:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="4b436-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="4b436-104">Lync Server의 첫 번째 백업을 수행 하기 전에 백업을 저장 하 고 유지 관리 하기 위해 필요한 하드웨어 및 소프트웨어를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b436-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="4b436-105">미디어 및 콘텐츠에 대 한 액세스 권한을 적절 하 게 확보 하 고 백업할 각 서버와 백업 미디어 간에 네트워크 연결을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b436-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="4b436-106">백업 및 복원 전략에 사용 하는 미디어 및 위치를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b436-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="4b436-107">일반 백업에 사용 하는 위치는 로컬 또는 원격 일 수 있지만, 보안이 유지 되어야 하며, 백업 및 복원에 대해 액세스 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b436-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="4b436-108">원격 위치를 사용 하 여 기본 사이트의 치명적 이벤트를 보호 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4b436-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="4b436-109">개별 구성 요소를 설정 하 고 테스트 한 후 각 서버에서 백업에 대 한 접근성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b436-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

