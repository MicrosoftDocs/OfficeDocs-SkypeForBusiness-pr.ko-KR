---
title: 'Lync Server 2013: 모범 사례 분석기에 대 한 업데이트 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd05761a1c107ac72c7b9c3242fb18a5a3c7a27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="7b492-102">Lync Server 2013에서 모범 사례 분석기에 대 한 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="7b492-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b492-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7b492-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7b492-104">모범 사례 분석기를 시작 하면 도구는 도구에 대 한 최신 업데이트를 검색할 수 있는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="7b492-105">업데이트를 사용할 수 있는 경우 업데이트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="7b492-106">업데이트를 다운로드 하지 않도록 선택 하거나 모범 사례 분석기에서 인터넷에 액세스할 수 없는 경우 컴퓨터에 이미 있는 버전을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b492-107">인터넷에 액세스 하는 데 프록시 인증이 필요한 경우 모범 사례 분석기에서 다운로드할 새 업데이트에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="7b492-108">그러나 Microsoft 다운로드 센터에서 최신 버전의 RtcBPA를 수동으로 다운로드할 수 있습니다 <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span><span class="sxs-lookup"><span data-stu-id="7b492-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="7b492-109">파일을 다운로드 한 후 모범 사례 분석기를 업데이트 하려는 컴퓨터로 복사 하 고 .msi 파일을 사용 하 여 해당 컴퓨터에 새 버전의 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="7b492-110">모범 사례 분석기 규칙을 업데이트 하려면 로컬 컴퓨터의 관리자로 도구를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="7b492-111">관리자 그룹의 구성원 인 계정을 사용 하 여 로그온 하지 않은 상태에서 업데이트가 검색 되는 경우 모범 사례 분석기를 닫은 후 다음 절차를 사용 하 여 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="7b492-112">모범 사례 분석기를 관리자 권한으로 열어 업데이트를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="7b492-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="7b492-113">모범 사례 분석기가 설치 되어 있는 컴퓨터에서 **시작**을 클릭 하 고 **Microsoft Lync Server 2013**를 가리킨 다음 **모범 사례 분석기**를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="7b492-114">관리자 그룹의 구성원 인 계정의 자격 증명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b492-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

