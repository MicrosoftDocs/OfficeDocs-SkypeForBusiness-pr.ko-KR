---
title: 'Lync Server 2013: 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c575a861644c27a0dba93790667ece9b973211e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="575b3-102">Lync Server 2013에서 클라이언트 버전 관리 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="575b3-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="575b3-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="575b3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="575b3-104">클라이언트 버전 구성 설정은 전역으로 또는 특정 사이트에 대해 클라이언트 버전 제어를 설정/해제 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="575b3-105">전역 클라이언트 버전 구성은 Lync Server 2013을 사용 하 여 설치 되며, 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="575b3-106">전역 구성을 사용 하도록 설정 하면 사용자가 로그온을 시도할 때 현재 위치에 있는 모든 클라이언트 버전 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="575b3-107">클라이언트 버전 제어가 발생 하지 않도록 하려면 전역 클라이언트 버전 구성을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="575b3-108">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="575b3-109">익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="575b3-110">Lync Server 제어판을 사용 하 여 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="575b3-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="575b3-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="575b3-112">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="575b3-113">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="575b3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="575b3-114">왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="575b3-115">다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-115">Do the following:</span></span>
    
      - <span data-ttu-id="575b3-116">클라이언트 버전 관리를 전역적으로 사용 하거나 사용 하지 않도록 설정 하려면 **글로벌** 구성을 두 번 클릭 한 다음 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="575b3-117">특정 사이트에 대 한 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정 하려면 **새로 만들기**를 클릭 하 고 사이트를 선택한 다음 **확인**을 클릭 하 고 사이트에 대 한 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="575b3-118">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 관리 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="575b3-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="575b3-119">**-CsClientVersionConfiguration** cmdlet을 사용 하 여 클라이언트 버전 관리를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="575b3-120">이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="575b3-121">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="575b3-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="575b3-122">클라이언트 버전 관리를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="575b3-122">To enable client versioning</span></span>

  - <span data-ttu-id="575b3-123">**Enabled** 속성을 True ($True)로 설정 하 여 클라이언트 버전 관리를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="575b3-124">클라이언트 버전 관리를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="575b3-124">To disable client versioning</span></span>

  - <span data-ttu-id="575b3-125">**Enabled** 속성을 False ($False)로 설정 하 여 클라이언트 버전 관리를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575b3-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="575b3-126">자세한 내용은 [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="575b3-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

