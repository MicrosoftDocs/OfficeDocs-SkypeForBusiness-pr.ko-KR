---
title: 부하를 실행할 토폴로지 프로 비전
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="4d41f-102">부하를 실행할 토폴로지 프로 비전</span><span class="sxs-lookup"><span data-stu-id="4d41f-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d41f-103">_**마지막으로 수정한 주제:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="4d41f-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="4d41f-104">부하를 실행할 토폴로지 프로 비전</span><span class="sxs-lookup"><span data-stu-id="4d41f-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="4d41f-105">Lync Server 2013의 기존 설정 및 구성에 따라 환경에서 다음과 같이 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="4d41f-106">Windows PowerShell 실행 정책을 무제한으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="4d41f-107">실행 정책 설정을 확인 하려면 Lync Server 관리 셸을 열고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="4d41f-108">이 명령이 무제한 값을 반환 하지 않으면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="4d41f-109">Lync Server 2013을 효과적으로 구성 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="4d41f-110">Lync Server 2013 토폴로지 (예: 컴퓨터 이름, 서비스 인스턴스, 사이트 이름 및 정책)에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="4d41f-111">응답 그룹 헌트 그룹과 같은 그룹에 만든 일부 사용자 (예: SIP Uri)를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="4d41f-112">명령줄에서 스크립트를 실행 하려면 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="4d41f-113">일반적으로이 패키지의 스크립트 중 하나를 실행 한 후에는 스크립트의 결과 추적이 scriptname \<\>$h $ m $ x (으)로 명명 된 스크립트와 같은 경로에 있는 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="4d41f-114">예를 들어 12:15 P.M.에 ArchivingPolicy를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="4d41f-115">ArchivingPolicy121500와 같은 로그 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d41f-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="4d41f-116">마지막으로, 서버를 구성 하는 예제를 제공 했지만 부하 실행을 완료 한 후에는 구성을 수정 하거나 삭제 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d41f-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

