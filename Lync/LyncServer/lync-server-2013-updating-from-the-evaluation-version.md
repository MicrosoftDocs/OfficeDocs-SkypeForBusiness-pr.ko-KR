---
title: 'Lync Server 2013: 평가 버전에서 업데이트'
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
ms.openlocfilehash: 91633832ec75e666653e5fc97c09df4c851078dc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="88124-102">Lync Server 2013의 평가 버전에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="88124-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88124-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="88124-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="88124-104">Microsoft Lync Server 2013 평가 버전을 설치한 경우 결국에는 해당 설치를 소프트웨어 라이선스 복사본으로 업데이트 해야 합니다. 이는 평가판 버전이 설치 후 180 일이 지나면 만료 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="88124-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="88124-105">그러나 평가용 버전을 완전히 제거한 다음 라이선스 버전을 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88124-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="88124-106">대신 유효한 라이선스 키를 얻은 후 Lync Server 프런트 엔드 서버, 디렉터 또는에 지 서버 역할을 하는 각 컴퓨터에서 다음 절차를 수행 하 여 Lync Server 2013의 평가 버전을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88124-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="88124-107">모니터링 서버 또는 보관 서버와 같은 다른 서버 역할을 수행 하는 컴퓨터는 업데이트할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88124-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="88124-108">Microsoft Lync Server 2013의 평가 버전에서 업데이트</span><span class="sxs-lookup"><span data-stu-id="88124-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="88124-109">Lync Server 2013의 평가 버전에서 라이선스 버전의 소프트웨어를 사용 하 여 컴퓨터를 업데이트 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="88124-110">**Microsoft Lync Server 2013의 평가 버전에서 업데이트**</span><span class="sxs-lookup"><span data-stu-id="88124-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="88124-111">로컬 관리자로 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="88124-112">**시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 관리 셸을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="88124-113">Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="88124-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="88124-114">server.msi 파일의 전체 경로를 지정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88124-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="88124-115">이 파일은 Lync Server 볼륨 미디어 설치 파일의 설치 폴더에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88124-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="88124-116">설치 실행이 완료되면 명령 프롬프트에 다음을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="88124-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="88124-117">Lync Server의 평가용 복사본을 실행 하는 다른 모든 프런트 엔드 서버, 디렉터 또는에 지 서버에서이 절차를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="88124-118">이 절차는 Lync Server 미디어 설치 파일을 사용 하 여 배포 된 모든 지점 서버 에서도 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="88124-119">Lync Server의 평가 버전이 지정 된 컴퓨터에서 실행 되 고 있는지 잘 모르는 경우 Lync Server 관리 셸에서 다음 명령을 실행 하 여이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88124-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="88124-120">[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet은 로컬 컴퓨터를 분석하여 다음 중 하나를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="88124-121">Lync Server volume license 키가 컴퓨터에 설치 되어 있는지 여부는 업데이트 하지 않아도 된다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="88124-122">Lync Server 평가 라이선스 키가 설치 되었는지, 즉 컴퓨터를 업데이트 해야 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="88124-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="88124-p104">해당 볼륨 라이센스 키는 컴퓨터에 필요하지 않습니다. 프런트 엔드 서버, 디렉터 및 에지 서버만 평가판 버전에서 정식 버전으로 업데이트하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88124-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

