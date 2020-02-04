---
title: 전화 접속 액세스 번호 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a13fdf36dcd36dc71df8ffa06c273c2b2b0f0292
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="74984-102">전화 접속 액세스 번호 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="74984-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74984-103">_**마지막으로 수정한 주제:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="74984-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="74984-104">전화 접속 액세스 번호를 마이그레이션하려면 두 단계가 필요 합니다. 다이얼 플랜 및 기타 전화 접속 액세스 번호 설정을 마이그레이션하고 **CsLegacyConfiguration** Cmdlet ( [가져오기-정책 및 설정](import-policies-and-settings.md)에서 완료 됨)을 실행 하 여 연락처 개체를 마이그레이션하기 위해 **csapplicationendpoint** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74984-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="74984-105">전화 접속 액세스 번호를 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="74984-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="74984-106">Office Communications Server 2007 R2 관리 도구를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74984-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="74984-107">콘솔 트리에서 포리스트 노드를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 클릭 한 다음 **회의 수행자 속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74984-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="74984-108">**Access 전화 번호** 탭에서 **풀로 서비스** 를 클릭 하 여 연결 된 풀을 기준으로 access 전화 번호를 정렬 하 고 마이그레이션하는 풀에 대 한 모든 액세스 번호를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="74984-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="74984-109">각 액세스 번호에 대 한 SIP URI를 식별 하려면 액세스 번호를 두 번 클릭 하 여 **회의 수행자 번호 편집** 대화 상자를 열고 **SIP URI**아래를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74984-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="74984-110">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74984-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="74984-111">각 전화 접속 액세스 번호를 Lync Server 2013에서 호스팅하는 풀로 이동 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="74984-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="74984-112">Office Communications Server 2007 R2 관리 도구의 **Access 전화 번호** 탭에서 마이그레이션할 Office Communications Server 2007 R2 풀에 대 한 전화 접속 액세스 번호가 남아 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74984-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

