---
title: 'Lync Server 2013: 중앙 관리 저장소 복제 상태'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4212e8616916f6a2a256530a7a0b74c9811f166d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="6f594-102">Lync Server 2013의 중앙 관리 저장소 복제 상태</span><span class="sxs-lookup"><span data-stu-id="6f594-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f594-103">_**마지막으로 수정한 주제:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="6f594-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="6f594-104">관리자가 일부 종류의 Lync Server를 변경 하는 경우 (예: 관리자가 새 음성 정책을 만들거나 주소록 서버 구성 설정을 변경 하는 경우) 변경 내용이 중앙 관리 저장소에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="6f594-105">그런 다음에는 Lync Server services 또는 서버 역할을 실행 하는 모든 컴퓨터에 변경 내용을 복제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="6f594-106">데이터를 복제하기 위해 중앙 관리 서버에서 실행되는 Master Replicator는 변경된 구성 데이터의 스냅샷을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="6f594-107">그런 다음이 스냅숏의 복사본을 Lync Server 서비스 또는 서버 역할을 실행 하는 각 컴퓨터에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="6f594-108">이러한 컴퓨터에서는 복제 에이전트가 스냅샷을 수신하고 변경된 데이터를 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="6f594-109">그런 다음 에이전트는 Master Replicator에 최신 복제 상태를 알리는 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="6f594-110">CsManagementStoreReplicationStatus cmdlet을 사용 하 여 조직의 Lync Server 컴퓨터 (또는 모든)에 대 한 복제 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="6f594-111">이 cmdlet을 실행할 수 있는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="6f594-111">Who can run this cmdlet?</span></span> <span data-ttu-id="6f594-112">기본적으로 다음 그룹의 구성원은 CsManagementStoreReplicationStatus cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6f594-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="6f594-113">이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f594-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="6f594-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f594-114">See Also</span></span>


[<span data-ttu-id="6f594-115">Get-CsManagementStoreReplicationStatus</span><span class="sxs-lookup"><span data-stu-id="6f594-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

