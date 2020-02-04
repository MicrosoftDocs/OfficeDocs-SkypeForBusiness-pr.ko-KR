---
title: 'Lync Server 2013: 평가판 버전에서 업데이트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b4cc704a77f824cbf7b2ec8ab4920c25454f3c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="abfbc-102">Lync Server 2013의 평가판 버전에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="abfbc-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abfbc-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="abfbc-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="abfbc-104">Microsoft Lync Server 2013의 평가판 버전을 설치한 경우 최종적으로 해당 설치를 소프트웨어의 라이선스 복사본으로 업데이트 해야 합니다. 평가판 버전은 설치 후 180 일이 지나면 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="abfbc-105">그러나 평가판 버전을 완전히 제거한 다음 라이선스 버전을 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="abfbc-106">대신 유효한 라이선스 키를 가져온 후 lync server 프런트 엔드 서버, 디렉터 또는 Edge 서버로 작동 하는 각 컴퓨터에서 다음 절차를 수행 하 여 Lync Server 2013의 평가판 버전을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="abfbc-107">모니터링 서버 또는 보관 서버와 같은 다른 서버 역할을 수행 하는 컴퓨터를 업데이트 하지 않아도 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="abfbc-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="abfbc-108">Microsoft Lync Server 2013의 평가판 버전에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="abfbc-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="abfbc-109">Lync Server 2013의 평가판 버전에서 라이선스를 받은 소프트웨어 버전으로 컴퓨터를 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="abfbc-110">**Microsoft Lync Server 2013의 평가판 버전에서 업데이트**</span><span class="sxs-lookup"><span data-stu-id="abfbc-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="abfbc-111">로컬 관리자로 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="abfbc-112">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="abfbc-113">Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="abfbc-114">파일 서버 .msi에 대 한 전체 경로를 지정 해야 할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="abfbc-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="abfbc-115">이 파일은 Lync Server 볼륨 미디어 설치 파일의 설정 폴더에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="abfbc-116">설치 프로그램이 실행을 완료 한 후 명령 프롬프트에서 다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="abfbc-117">Lync Server의 평가 복사본을 실행 하는 다른 프런트 엔드 서버, 디렉터 또는 Edge 서버에 대해이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="abfbc-118">이 절차는 Lync Server 미디어 설치 파일을 사용 하 여 배포한 지사 서버 에서도 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="abfbc-119">Lync Server의 평가판 버전이 지정 된 컴퓨터에서 실행 중인지 확실 하지 않은 경우 Lync Server Management Shell 내에서 다음 명령을 실행 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="abfbc-120">[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet은 로컬 컴퓨터를 분석 하 고 다음 중 하나를 다시 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="abfbc-121">Lync Server 볼륨 라이선스 키가 컴퓨터에 설치 되어 있는지, 업데이트가 필요 하지 않음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="abfbc-122">Lync Server 평가 라이선스 키가 설치 되어 있는지 확인 하 고 컴퓨터를 업데이트 해야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="abfbc-123">컴퓨터에 볼륨 라이선스 키가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-123">That no volume license key is required on the computer.</span></span> <span data-ttu-id="abfbc-124">평가판 버전을 사용 허가를 받은 버전으로 업데이트 하는 것은 프런트 엔드 서버, 디렉터 및 Edge 서버 에서만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="abfbc-124">Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

