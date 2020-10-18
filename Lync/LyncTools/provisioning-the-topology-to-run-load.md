---
title: 부하를 실행할 토폴로지 프로 비전
description: 부하를 실행할 토폴로지를 프로 비전 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da482fde949675acc1722305433b95b7a6a6b523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578414"
---
# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="244c9-103">부하를 실행할 토폴로지 프로 비전</span><span class="sxs-lookup"><span data-stu-id="244c9-103">Provisioning the Topology to Run Load</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="244c9-104">_**마지막으로 수정 된 항목:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="244c9-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

<span data-ttu-id="244c9-105">기존 설정 및 Lync Server 2013의 구성에 따라 사용자 환경에서 다음과 같은 사항을 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="244c9-106">Windows PowerShell 실행 정책을 무제한으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="244c9-107">실행 정책 설정을 확인 하려면 Lync Server 관리 셸을 열고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="244c9-108">이 명령이 무제한 값을 반환 하지 않으면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="244c9-109">Lync Server 2013를 효과적으로 구성 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="244c9-110">Lync Server 2013 토폴로지 (예: 컴퓨터 이름, 서비스 인스턴스, 사이트 이름 및 정책)에 익숙해져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="244c9-111">응답 그룹 헌트 그룹 (예: SIP Uri)과 같은 그룹에 만들어진 일부 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="244c9-112">명령줄에서 스크립트를 실행 하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="244c9-113">일반적으로이 패키지의 스크립트 중 하나를 실행 하면 스크립트의 결과 추적은 \<scriptname\> $h $ m $s.txt 라는 스크립트를 호출한 경로에 있는 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="244c9-114">예를 들어 오후 12:15 시 ArchivingPolicy.ps1 실행</span><span class="sxs-lookup"><span data-stu-id="244c9-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="244c9-115">ArchivingPolicy121500.txt와 같은 로그 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="244c9-116">마지막으로 서버를 구성 하는 예제를 제공 했지만 부하를 모두 실행 한 후에 구성을 수정 하거나 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="244c9-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

