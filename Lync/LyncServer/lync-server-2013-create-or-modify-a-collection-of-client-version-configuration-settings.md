---
title: 클라이언트 버전 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f70e1d29cd6cd8de3a323829772eab1f9c3452
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3e1ea-102">Lync Server 2013에서 클라이언트 버전 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3e1ea-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e1ea-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3e1ea-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3e1ea-104">클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="3e1ea-105">전역 클라이언트 버전 구성은 Lync Server를 사용 하 여 설치 되며, 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="3e1ea-106">개별 사이트에 대 한 클라이언트 버전 구성 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="3e1ea-107">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 구성 설정을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="3e1ea-108">익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="3e1ea-109">Lync Server 제어판을 사용 하 여 클라이언트 버전 구성 설정을 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="3e1ea-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3e1ea-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3e1ea-111">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3e1ea-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3e1ea-113">왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="3e1ea-114">**클라이언트 버전 구성** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="3e1ea-115">새 구성을 만들려면 **새로**만들기를 클릭 하 고 사이트를 선택한 다음 **확인** 이름을 클릭 하 고 설정을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="3e1ea-116">구성을 수정 하려면 구성을 선택 하 고 **편집**을 클릭 한 다음 **자세한 정보 표시**를 클릭 하 고 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3e1ea-117">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 구성 설정 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3e1ea-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3e1ea-118">**새-csclientversionconfiguration** cmdlet을 사용 하 여 클라이언트 버전 구성 설정을 만든 후에는 **csclientversionconfiguration** cmdlet을 사용 하 여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="3e1ea-119">이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3e1ea-120">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="3e1ea-121">클라이언트 버전 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3e1ea-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="3e1ea-122">다음 명령은 Redmond 사이트에 적용 된 클라이언트 버전 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="3e1ea-123">이 예에서는 Redmond 사이트에 대해 클라이언트 버전 관리를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="3e1ea-124">사이트에 대해 클라이언트 버전 관리를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="3e1ea-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="3e1ea-125">이 명령은 Redmond 사이트에 대 한 클라이언트 버전 관리를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="3e1ea-126">조직 전체에서 클라이언트 버전 관리를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="3e1ea-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="3e1ea-127">이 예에서는 조직에서 사용 중인 모든 클라이언트 버전 구성 설정에 대해 클라이언트 버전 관리를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="3e1ea-128">자세한 내용은 [새-csclientversionconfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) 및 [csclientversionconfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) Cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e1ea-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

