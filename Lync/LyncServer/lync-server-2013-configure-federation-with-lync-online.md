---
title: 'Lync Server 2013: Lync Online을 사용 하 여 페더레이션 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfeffc8a72d26167b9771e6437d21ba55c8f5636
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525955"
---
# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="18f0c-102">Lync Online을 사용 하 여 Lync Server 2013의 페더레이션 구성</span><span class="sxs-lookup"><span data-stu-id="18f0c-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18f0c-103">_**마지막으로 수정 된 항목:** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="18f0c-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="18f0c-104">온-프레미스 배포와 비즈니스용 Skype Online 간의 상호 운용성을 구성 하려면이 섹션의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="18f0c-105">비즈니스용 Skype 온라인과의 페더레이션에 대 한 온-프레미스에 지 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="18f0c-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="18f0c-106">페더레이션에서는 온-프레미스 배포의 사용자가 조직의 Microsoft 365 또는 Office 365 사용자와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-106">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="18f0c-107">페더레이션을 구성 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="18f0c-108">공유 SIP 주소 공간에 대 한 비즈니스용 Skype Online 테 넌 트 구성</span><span class="sxs-lookup"><span data-stu-id="18f0c-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="18f0c-109">SIP (Session 착수 프로토콜) 주소는 전화 번호나 전자 메일 주소와 마찬가지로 네트워크의 각 사용자에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="18f0c-110">Lync 사용자를 온-프레미스에서 비즈니스용 Skype Online으로 이동 하기 전에 공유 세션 시작 프로토콜 (SIP) 주소 공간을 온-프레미스 배포와 공유 하도록 Microsoft 365 또는 Office 365 조직을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Microsoft 365 or Office 365 organization to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="18f0c-111">이 구성을 구성 하지 않으면 다음과 같은 오류 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="18f0c-112">Move-CsUser: HostedMigration fault: Error = (510), Description = (이 사용자의 테 넌 트는 공유 sip 주소 공간에 대해 사용 하도록 설정 되지 않았습니다.)</span><span class="sxs-lookup"><span data-stu-id="18f0c-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="18f0c-113">공유 SIP 주소 공간을 구성 하려면 비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정한 후 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="18f0c-114">비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정 하려면 먼저 비즈니스용 Skype 온라인 모듈 for Windows PowerShell을 설치 해야 [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911) 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="18f0c-115">모듈을 설치한 후에는 다음 cmdlet을 사용 하 여 원격 세션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18f0c-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

<span data-ttu-id="18f0c-116">비즈니스용 Skype Online을 사용 하 여 원격 PowerShell 세션을 설정 하는 방법에 대 한 자세한 내용은 [Windows PowerShell을 사용 하 여 비즈니스용 Skype online에 연결](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18f0c-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="18f0c-117">비즈니스용 Skype Online PowerShell 모듈을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell을 사용 하 여 비즈니스용 Skype online 관리](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18f0c-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18f0c-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18f0c-118">See Also</span></span>


[<span data-ttu-id="18f0c-119">새-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="18f0c-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
