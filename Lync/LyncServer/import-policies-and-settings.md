---
title: 정책 및 설정 가져오기
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a><span data-ttu-id="e783a-102">정책 및 설정 가져오기</span><span class="sxs-lookup"><span data-stu-id="e783a-102">Import policies and settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e783a-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e783a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e783a-104">Office Communications Server 2007 R2 토폴로지 정보를 Lync Server 2013 파일럿 풀과 통합 한 후에는 Lync Server 2013 Management Shell cmdlet을 실행 하 여 Office Communications Server 2007 R2 정책 및 구성 설정을 마이그레이션해야 합니다. 을 (를) Lync Server 2013 파일럿 풀로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-104">After you merge your Office Communications Server 2007 R2 topology information with your Lync Server 2013 pilot pool, you need to run a Lync Server 2013 Management Shell cmdlet to migrate your Office Communications Server 2007 R2 policies and configuration settings to your Lync Server 2013 pilot pool.</span></span>

<span data-ttu-id="e783a-105">**CsLegacyConfiguration** cmdlet은 정책, 음성 경로, 다이얼 플랜, Communicator Web Access Url 및 Lync Server 2013에 대 한 전화 접속 액세스 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-105">The **Import-CsLegacyConfiguration** cmdlet imports policies, voice routes, dial plans, Communicator Web Access URLs, and dial-in access numbers to Lync Server 2013.</span></span>

<div>

## <a name="to-migrate-policies-and-settings"></a><span data-ttu-id="e783a-106">정책 및 설정을 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="e783a-106">To migrate policies and settings</span></span>

1.  <span data-ttu-id="e783a-107">Lync Server 2013 프런트 엔드 서버에서 Lync Server Management Shell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-107">On the Lync Server 2013 Front End server, start the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="e783a-108">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-108">At the command line, type the following:</span></span>
    
        Import-CsLegacyConfiguration
    
    <span data-ttu-id="e783a-109">정책을 가져온 후에는 다음 절차를 사용 하 여 Lync Server 제어판에서 가져온 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-109">After the policies are imported, use the procedure that follows to see the imported policies in the Lync Server Control Panel .</span></span>

</div>

<div>

## <a name="to-view-imported-policies"></a><span data-ttu-id="e783a-110">가져온 정책을 보려면</span><span class="sxs-lookup"><span data-stu-id="e783a-110">To view imported policies</span></span>

1.  <span data-ttu-id="e783a-111">Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-111">Open Lync Server 2013 Control Panel.</span></span>

2.  <span data-ttu-id="e783a-112">**음성 라우팅을** 클릭 하 고 가져온 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-112">Click **Voice Routing** and view the imported policies.</span></span>

3.  <span data-ttu-id="e783a-113">**회의** 를 클릭 하 고 가져온 정책을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-113">Click **Conferencing** and view the imported policies.</span></span>

4.  <span data-ttu-id="e783a-114">**페더레이션 및 외부 액세스** 를 클릭 하 고 가져온 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-114">Click **Federation and External Access** and view the imported policies.</span></span>

5.  <span data-ttu-id="e783a-115">**모니터링 및 보관** 을 클릭 하 고 가져온 정책을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e783a-115">Click **Monitoring and Archiving** and view the imported policies.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

