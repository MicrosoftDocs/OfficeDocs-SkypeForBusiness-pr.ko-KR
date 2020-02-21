---
title: 'Lync Server 2013: 기존 웹 서비스 구성 설정 삭제'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Web Service configuration settings
ms:assetid: c2b96f4c-4b07-48e6-9ca6-55bc0e0cf5a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182582(v=OCS.15)
ms:contentKeyID: 48185333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a6b1ddb7d4bf36186bec0ade8cacf75b15e8b70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5b9b1-102">Lync Server 2013에서 기존 웹 서비스 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="5b9b1-102">Delete existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b9b1-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5b9b1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5b9b1-104">웹 서비스 구성 설정을 삭제 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-104">Follow these steps to delete web service configuration settings.</span></span>

<div>

## <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="5b9b1-105">웹 서비스 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="5b9b1-105">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="5b9b1-106">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5b9b1-107">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5b9b1-108">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5b9b1-109">왼쪽 탐색 표시줄에서 **보안**, **웹 서비스**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-109">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="5b9b1-110">**웹 서비스** 페이지의 검색 필드에 삭제할 정책의 이름 일부나 전체를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-110">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="5b9b1-111">정책 목록에서 원하는 정책을 클릭하고 **편집**을 클릭한 다음 **삭제**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-111">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="5b9b1-112">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-112">Click **OK**.</span></span>

</div>

<div>

## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5b9b1-113">Windows PowerShell Cmdlet을 사용 하 여 웹 서비스 구성 설정 삭제</span><span class="sxs-lookup"><span data-stu-id="5b9b1-113">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5b9b1-114">Windows PowerShell 및 **set-cswebserviceconfiguration** cmdlet을 사용 하 여 웹 서비스 구성 설정을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-114">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="5b9b1-115">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-115">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5b9b1-116">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="5b9b1-117">웹 서비스 구성 설정의 특정 컬렉션을 삭제하려면</span><span class="sxs-lookup"><span data-stu-id="5b9b1-117">To delete a specific collection of web service configuration settings</span></span>

  - <span data-ttu-id="5b9b1-118">다음 명령은 Redmond 사이트에 적용된 웹 서비스 보안 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-118">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
        Remove-CsWebServiceConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="5b9b1-119">사이트 범위에 적용 된 모든 웹 서비스 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="5b9b1-119">To delete all of the web service configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="5b9b1-120">다음 명령은 서비스 범위에 적용된 모든 웹 서비스 보안 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-120">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
        Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration

</div>

<div>

## <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="5b9b1-121">인증서 인증을 허용 하는 모든 웹 서비스 구성 설정을 삭제 하려면</span><span class="sxs-lookup"><span data-stu-id="5b9b1-121">To delete all of the web service configuration settings that allow certificate authentication</span></span>

  - <span data-ttu-id="5b9b1-122">다음 명령은 인증서 인증을 사용할 수 있도록 허용하는 모든 웹 서비스 보안 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-122">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
        Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration

</div>

<span data-ttu-id="5b9b1-123">자세한 내용은 [Remove-set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b9b1-123">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWebServiceConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b9b1-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b9b1-124">See Also</span></span>


[<span data-ttu-id="5b9b1-125">Lync Server 2013 제어판에서 인증 구성</span><span class="sxs-lookup"><span data-stu-id="5b9b1-125">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

