---
title: 비즈니스용 Skype 서버에서 PIN 정책 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '요약: 비즈니스용 Skype 서버에 대한 사용자의 PIN 정책 정보를 볼 수 있습니다.'
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806528"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="92a3d-103">비즈니스용 Skype 서버에서 PIN 정책 정보 보기</span><span class="sxs-lookup"><span data-stu-id="92a3d-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="92a3d-104">**요약:** 비즈니스용 Skype 서버에 대한 사용자의 PIN 정책 정보를 본다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="92a3d-105">**PIN** 정책 탭을 사용하여 IP 전화로 비즈니스용 Skype에 연결하는 사용자의 PIN(개인 식별 번호) 인증을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="92a3d-106">PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="92a3d-107">사용자 수준 또는 사이트 수준 PIN 정책을 수정하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="92a3d-108">비즈니스용 Skype 서버 제어판에서 PIN 정책에 대한 정보를 보기 위해</span><span class="sxs-lookup"><span data-stu-id="92a3d-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="92a3d-109">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="92a3d-110">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="92a3d-111">왼쪽 탐색 모음에서 **보안** 을 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="92a3d-112">**PIN 정책** 페이지에서 정책을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="92a3d-113">cmdlet을 사용하여 PIN Windows PowerShell 보기</span><span class="sxs-lookup"><span data-stu-id="92a3d-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="92a3d-114">또한 PIN 정책은 Windows PowerShell cmdlet을 사용하여 Get-CsPinPolicy 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="92a3d-115">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92a3d-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="92a3d-116">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92a3d-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="92a3d-117">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="92a3d-118">PIN 정책을 보시다</span><span class="sxs-lookup"><span data-stu-id="92a3d-118">To view PIN policies</span></span>

<span data-ttu-id="92a3d-119">모든 PIN 정책에 대한 정보를 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="92a3d-120">그러면 다음과 같은 정보가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="92a3d-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="92a3d-121">자세한 내용은 [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="92a3d-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="92a3d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92a3d-122">See also</span></span>

[<span data-ttu-id="92a3d-123">비즈니스용 Skype 서버에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="92a3d-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
