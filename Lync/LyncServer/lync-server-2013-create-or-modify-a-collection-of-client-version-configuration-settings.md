---
title: 클라이언트 버전 구성 설정 컬렉션 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84df13c7abbc98cbb90c5b59a6b0717deb855e28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="73c1c-102">Lync Server 2013에서 클라이언트 버전 구성 설정 컬렉션 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="73c1c-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73c1c-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="73c1c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="73c1c-104">클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="73c1c-105">전역 클라이언트 버전 구성은 Lync Server와 함께 설치 되며 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="73c1c-106">개별 사이트에 대 한 클라이언트 버전 구성 설정을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="73c1c-107">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 구성 설정을 만들거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="73c1c-108">익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="73c1c-109">Lync Server 제어판을 사용 하 여 클라이언트 버전 구성 설정을 만들거나 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="73c1c-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="73c1c-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="73c1c-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="73c1c-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73c1c-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="73c1c-113">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="73c1c-114">**클라이언트 버전 구성** 페이지에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="73c1c-115">새 구성을 만들려면 **새로 만들기**를 클릭 하 고 사이트를 선택한 다음 **확인** 이름을 클릭 하 고 설정을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="73c1c-116">구성을 수정 하려면 구성을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 하 고 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="73c1c-117">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 구성 설정 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="73c1c-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="73c1c-118">**새 csclientversionconfiguration** cmdlet을 사용 하 여 클라이언트 버전 구성 설정을 만들고, **Set-csclientversionconfiguration** cmdlet을 사용 하 여 변경 내용을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="73c1c-119">이러한 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="73c1c-120">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73c1c-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="73c1c-121">클라이언트 버전 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="73c1c-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="73c1c-122">다음 명령은 Redmond 사이트에 적용 된 클라이언트 버전 구성 설정의 새 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="73c1c-123">이 예제에서는 Redmond 사이트에 대해 클라이언트 버전 관리를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="73c1c-124">사이트에 대 한 클라이언트 버전 관리를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="73c1c-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="73c1c-125">이 명령은 Redmond 사이트에 대 한 클라이언트 버전 관리를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="73c1c-126">조직 전체에서 클라이언트 버전 관리를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="73c1c-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="73c1c-127">이 예제에서는 조직에서 사용 중인 모든 클라이언트 버전 구성 설정에 대해 클라이언트의 버전 관리를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73c1c-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="73c1c-128">자세한 내용은 [새 csclientversionconfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) 및 [csclientversionconfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) Cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73c1c-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

