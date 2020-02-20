---
title: 'Lync Server 2013: 기존 등록자 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19f127efa6e2cab04434dd8de6e541897d50483f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="55244-102">Lync Server 2013에서 기존 등록자 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="55244-102">Delete existing Registrar configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55244-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="55244-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="55244-104">등록자를 삭제 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-104">Follow these steps to delete a Registrar.</span></span>

<div>

## <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="55244-105">등록자 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="55244-105">To delete Registrar configuration settings</span></span>

1.  <span data-ttu-id="55244-106">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="55244-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="55244-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="55244-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55244-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="55244-109">왼쪽 탐색 표시줄에서 **보안**, **등록자**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-109">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>

4.  <span data-ttu-id="55244-110">**등록자** 페이지의 검색 필드에 삭제할 등록자의 이름 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-110">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>

5.  <span data-ttu-id="55244-111">목록에서 원하는 등록자를 클릭 하 고 **편집**을 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-111">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="55244-112">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-112">Click **OK**.</span></span>

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="55244-113">Windows PowerShell Cmdlet을 사용 하 여 등록자 구성 설정 제거</span><span class="sxs-lookup"><span data-stu-id="55244-113">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="55244-114">Windows PowerShell 및 **Remove-CsProxyConfiguration** cmdlet을 사용 하 여 등록자 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55244-114">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="55244-115">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55244-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="55244-116">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55244-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="55244-117">특정 등록자 보안 설정 집합을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="55244-117">To remove a specific set of Registrar security settings</span></span>

  - <span data-ttu-id="55244-118">다음 명령은에 지 서버 atl-edge-011.litwareinc.com에 적용 된 등록자 보안 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-118">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="55244-119">사이트 범위에 적용 된 모든 등록자 보안 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="55244-119">To remove all of the Registrar security settings applied to the site scope</span></span>

  - <span data-ttu-id="55244-120">다음 명령은 등록자 서비스에 적용 된 모든 등록자 보안 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-120">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="55244-121">NTLM 인증을 허용 하는 모든 등록자 보안 설정을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="55244-121">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

  - <span data-ttu-id="55244-122">다음 명령은 클라이언트 인증에 NTLM을 사용할 수 있도록 허용 하는 모든 등록자 보안 설정을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="55244-122">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

<span data-ttu-id="55244-123">자세한 내용은 [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55244-123">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

