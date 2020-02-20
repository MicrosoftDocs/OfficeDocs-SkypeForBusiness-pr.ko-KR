---
title: '4 단계: 토폴로지 병합'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 4: Merge topologies'
ms:assetid: 81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205044(v=OCS.15)
ms:contentKeyID: 48184668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c36d88626288d96cb38242943df3bc055f6cbef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-4-merge-topologies"></a><span data-ttu-id="ee5e8-102">4 단계: 토폴로지 병합</span><span class="sxs-lookup"><span data-stu-id="ee5e8-102">Phase 4: Merge topologies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee5e8-103">_**마지막으로 수정 된 항목:** 2012-03-29_</span><span class="sxs-lookup"><span data-stu-id="ee5e8-103">_**Topic Last Modified:** 2012-03-29_</span></span>

<span data-ttu-id="ee5e8-104">다음 항목에서는 Microsoft Office Communications Server 2007 R2 풀을 Microsoft Lync Server 2013 풀에 병합 하는 데 필요한 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5e8-104">The following topics outline the steps needed to merge your Microsoft Office Communications Server 2007 R2 pools to Microsoft Lync Server 2013 pools.</span></span> <span data-ttu-id="ee5e8-105">먼저 토폴로지 작성기 병합 마법사를 사용하여 토폴로지 정보를 병합합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5e8-105">First, you use the Topology Builder Merge wizard to merge topology information.</span></span> <span data-ttu-id="ee5e8-106">이 도구는 Edge Server 정보를 포함 하 여 Office Communications Server 2007 R2 환경에 대 한 정보를 수집 하 고 Lync Server 2013와 공유 되는 데이터베이스에 해당 정보를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5e8-106">This tool collects information about your Office Communications Server 2007 R2 environment, including Edge Server information, and publishes that information to a database shared with Lync Server 2013.</span></span> <span data-ttu-id="ee5e8-107">병합 된 토폴로지를 게시 한 후에는 토폴로지 작성기를 사용 하 여 Office Communications Server 2007 R2 토폴로지 정보와 새로 배포 된 Lync Server 2013 토폴로지에 대 한 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5e8-107">After you publish the merged topology, Topology Builder is used to view the Office Communications Server 2007 R2 topology information and information about the newly deployed Lync Server 2013 topology.</span></span> <span data-ttu-id="ee5e8-108">마지막으로 Lync Server 관리 셸 cmdlet을 사용하여 정책 및 구성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee5e8-108">Finally, you use Lync Server Management Shell cmdlets to import policies and configuration settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee5e8-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ee5e8-109">In This Section</span></span>

  - [<span data-ttu-id="ee5e8-110">WMI 이전 버전과의 호환성 패키지 설치</span><span class="sxs-lookup"><span data-stu-id="ee5e8-110">Install WMI Backward Compatibility package</span></span>](install-wmi-backward-compatibility-package.md)

  - [<span data-ttu-id="ee5e8-111">토폴로지 작성기 병합 마법사를 사용 하 여 병합</span><span class="sxs-lookup"><span data-stu-id="ee5e8-111">Merge using Topology Builder Merge wizard</span></span>](merge-using-topology-builder-merge-wizard.md)

  - [<span data-ttu-id="ee5e8-112">정책 및 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="ee5e8-112">Import policies and settings</span></span>](import-policies-and-settings.md)

  - [<span data-ttu-id="ee5e8-113">토폴로지 정보 확인</span><span class="sxs-lookup"><span data-stu-id="ee5e8-113">Verify topology information</span></span>](verify-topology-information.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

