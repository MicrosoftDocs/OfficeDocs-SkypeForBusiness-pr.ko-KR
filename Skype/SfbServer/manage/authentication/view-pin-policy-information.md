---
title: 비즈니스용 Skype 서버에서 PIN 정책 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '요약: 비즈니스용 Skype 서버에 대 한 사용자의 PIN 정책 정보를 봅니다.'
ms.openlocfilehash: c61c55f97abc661558089c1d26ee4f5537fcf36b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991953"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="4cfeb-103">비즈니스용 Skype 서버에서 PIN 정책 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4cfeb-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="4cfeb-104">**요약:** 비즈니스용 Skype 서버에 대 한 사용자의 PIN 정책 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="4cfeb-105">**Pin (고정 정책** ) 탭을 사용 하 여 IP 전화기로 비즈니스용 Skype에 연결 하는 사용자의 PIN (개인 식별 번호) 인증을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="4cfeb-106">PIN 인증을 사용 하려면 웹 서비스 설정에서 **Pin 인증 사용** 이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="4cfeb-107">다음 단계에 따라 사용자 수준 또는 사이트 수준 PIN 정책을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4cfeb-108">비즈니스용 Skype Server 제어판의 PIN 정책에 대 한 정보를 보려면</span><span class="sxs-lookup"><span data-stu-id="4cfeb-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4cfeb-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="4cfeb-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="4cfeb-110">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="4cfeb-111">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="4cfeb-112">**고정 정책** 페이지에서 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4cfeb-113">Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 보기</span><span class="sxs-lookup"><span data-stu-id="4cfeb-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4cfeb-114">Windows PowerShell 및 CsPinPolicy cmdlet을 사용 하 여 PIN 정책을 볼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="4cfeb-115">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4cfeb-116">원격 Windows PowerShell을 사용 하 여 비즈니스용 Skype Server에 연결 하는 방법에 대 한 자세한 내용은 블로그 문서 ["빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"](https://go.microsoft.com/fwlink/p/?linkId=255876)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="4cfeb-117">이 프로세스는 비즈니스용 Skype 서버에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="4cfeb-118">핀 정책 보기</span><span class="sxs-lookup"><span data-stu-id="4cfeb-118">To view PIN policies</span></span>

<span data-ttu-id="4cfeb-119">모든 PIN 정책에 대 한 정보를 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="4cfeb-120">이는 다음과 같은 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="4cfeb-121">자세한 내용은 Get-help cmdlet에 대 한 도움말 항목 [CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4cfeb-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4cfeb-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cfeb-122">See also</span></span>

[<span data-ttu-id="4cfeb-123">비즈니스용 Skype 서버에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4cfeb-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
