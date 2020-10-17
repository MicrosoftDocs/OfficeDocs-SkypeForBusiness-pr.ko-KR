---
title: 'Lync Server 2013: DFS 파일 저장소 구성'
description: 'Lync Server 2013: DFS 파일 저장소를 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d70ae93db188ec51d04dd33d6c3cb5659db5a2c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564384"
---
# <a name="configure-dfs-file-storage-for-lync-server-2013"></a><span data-ttu-id="67649-103">Lync Server 2013에 대해 DFS 파일 저장소 구성</span><span class="sxs-lookup"><span data-stu-id="67649-103">Configure DFS file storage for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67649-104">_**마지막으로 수정 된 항목:** 2016-05-23_</span><span class="sxs-lookup"><span data-stu-id="67649-104">_**Topic Last Modified:** 2016-05-23_</span></span>

<span data-ttu-id="67649-105">Lync Server 2013에서는 DFS (분산 파일 시스템)에서 파일 공유를 사용할 지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-105">Lync Server 2013 supports using file shares on a Distributed File System (DFS).</span></span> <span data-ttu-id="67649-106">Windows Server 2008 용 DFS에 대 한 자세한 내용은 Windows Server 2008에 대 한 DFS 단계별 가이드를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835) . DFS를 사용 하려면 Lync Server 2013에 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-106">For details about DFS for Windows Server 2008, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).To use a DFS, Lync Server 2013 requires the following:</span></span>

  - <span data-ttu-id="67649-107">네임스페이스가 도메인 기반이어야 함</span><span class="sxs-lookup"><span data-stu-id="67649-107">Namespaces are domain based</span></span>

  - <span data-ttu-id="67649-108">모든 네임스페이스 서버가 Windows 2008 이상을 실행해야 함</span><span class="sxs-lookup"><span data-stu-id="67649-108">All namespace servers are running a minimum of Windows 2008</span></span>

<span data-ttu-id="67649-109">Lync Server 2013을 설치 하려면 공유 폴더에 대 한 사용 권한이 관리자에 게 모든 권한을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-109">Lync Server 2013 setup requires that permissions on shared folder allow full access to Administrator.</span></span> <span data-ttu-id="67649-110">그러면 Lync Server 2013에서 NTFS 파일 권한을 사용 하 여 폴더에 ACL을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-110">Lync Server 2013 will then use NTFS file permissions to ACL the folders.</span></span> <span data-ttu-id="67649-111">상속된 DFS 공유 사용 권한은 액세스를 제한하는 데 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67649-111">Inherited DFS share permissions will not be used to restrict access.</span></span>

<span data-ttu-id="67649-112">파일 공유 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync Server 2013의 파일 저장소 지원을](lync-server-2013-file-storage-support.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="67649-112">For more details about File Share requirements, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="67649-113">비 DFS 공유 구성에 대 한 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67649-113">You may be looking for information on configuring a non-DFS share.</span></span> <span data-ttu-id="67649-114">그렇다면 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013에 대 한 하드웨어 설정을</A>확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="67649-114">If so, check out <A href="lync-server-2013-hardware-setup.md">Hardware setup for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="67649-115">다음 절차에서는 DFS 설정 가이드에 설명된 대로 DFS 네임스페이스 마법사를 사용하여 공유 폴더 사용 권한을 올바르게 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-115">The following procedure describes how to correctly configure shared folder permissions using the DFS Namespace Wizard (as described in DFS setup guide).</span></span>

<div>

## <a name="to-configure-shared-folder-permissions"></a><span data-ttu-id="67649-116">공유 폴더 사용 권한을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="67649-116">To configure shared folder permissions</span></span>

1.  <span data-ttu-id="67649-117">**시작**을 클릭하고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **DFS 관리**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **DFS Management**.</span></span>

2.  <span data-ttu-id="67649-118">DFS 관리 스냅인의 콘솔 트리에서 해당 네임스페이스 서버(예: filesrv1.contoso.com)를 마우스 오른쪽 단추로 클릭한 다음 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-118">In the console tree of the DFS Management snap-in, right-click the namespace server (for example filesrv1.contoso.com), and then click **Edit Settings**.</span></span>

3.  <span data-ttu-id="67649-119">**공유 폴더 사용 권한**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-119">Select **Shared Folder Permissions**.</span></span>

4.  <span data-ttu-id="67649-120">**사용자 지정 권한 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-120">Select **Use Custom Permissions**.</span></span>

5.  <span data-ttu-id="67649-121">관리자 그룹에 대해 **허용** 아래에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-121">For the Administrator group, select the following under **Allow**:</span></span>
    
      - <span data-ttu-id="67649-122">**모든 권한**</span><span class="sxs-lookup"><span data-stu-id="67649-122">**Full Control**</span></span>
    
      - <span data-ttu-id="67649-123">**변경 사항**</span><span class="sxs-lookup"><span data-stu-id="67649-123">**Change**</span></span>
    
      - <span data-ttu-id="67649-124">**읽기**</span><span class="sxs-lookup"><span data-stu-id="67649-124">**Read**</span></span>

6.  <span data-ttu-id="67649-125">**적용**을 클릭한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="67649-125">Click **Apply**, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

