---
title: 'Lync Server 2013: 클라이언트 버전 구성 설정 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9db03377f8f2fc880de61639f4eedc5b1c302d21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c34da-102">Lync Server 2013에서 클라이언트 버전 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="c34da-102">View client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c34da-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c34da-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c34da-104">클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="c34da-105">전역 클라이언트 버전 구성은 Lync Server 2013와 함께 설치 되며 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="c34da-106">전역 구성을 사용하도록 설정하면 포함되어 있는 모든 클라이언트 버전 정책이 사용자의 로그온 시도 시 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-106">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="c34da-107">Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-107">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c34da-108">익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="c34da-109">Lync Server 제어판을 사용 하 여 클라이언트 버전 구성 설정을 보려면</span><span class="sxs-lookup"><span data-stu-id="c34da-109">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c34da-110">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c34da-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c34da-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c34da-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c34da-113">왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="c34da-114">보려는 클라이언트 버전 구성의 이름을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-114">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c34da-115">Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 구성 설정 보기</span><span class="sxs-lookup"><span data-stu-id="c34da-115">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c34da-116">**Get-CsClientVersionConfiguration** cmdlet을 사용 하 여 클라이언트 버전 구성 설정을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-116">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="c34da-117">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="c34da-118">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c34da-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="c34da-119">클라이언트 버전 구성 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="c34da-119">To view client version configuration information</span></span>

  - <span data-ttu-id="c34da-120">모든 클라이언트 버전 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-120">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="c34da-121">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c34da-121">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="c34da-122">자세한 내용은 [Get CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c34da-122">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

