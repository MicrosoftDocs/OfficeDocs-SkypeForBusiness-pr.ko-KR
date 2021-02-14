---
title: 사용자가 프레미스에서 Enterprise Voice 사용하도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 사용자가 전화 시스템(클라우드 PBX)을 사용하려면 먼저 사용자가 전화 Enterprise Voice 사용하도록 설정하고 전화 번호를 할당해야 합니다. 이 작업을 위해 사용자가 여전히 On-premises 배포에 있는 동안에는 해당 배포를 사용할 수 있습니다.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359194"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="da5a7-104">사용자가 프레미스에서 Enterprise Voice 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="da5a7-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="da5a7-105">사용자가 전화 시스템(클라우드 PBX)을 사용하려면 먼저 사용자가 전화 Enterprise Voice 사용하도록 설정하고 전화 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="da5a7-106">이 작업을 위해 사용자가 여전히 On-premises 배포에 있는 동안에는 해당 배포를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="da5a7-107">비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="da5a7-108">또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 더 이상 지원되지 않는 모든 비즈니스용 Skype 환경 간의 PSTN 연결도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="da5a7-109">직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="da5a7-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="da5a7-110">사용자가 프레미스에서 Enterprise Voice 번호를 할당할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="da5a7-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="da5a7-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="da5a7-112">시작 메뉴 또는 데스크톱 바로 가기를 사용하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="da5a7-113">브라우저 창을 연 다음 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="da5a7-114">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="da5a7-115">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="da5a7-116">표에서 비즈니스용 Skype Online 사용자 계정을 클릭하여 비즈니스용 Skype를 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="da5a7-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="da5a7-117">편집 **메뉴에서** 세부 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da5a7-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="da5a7-118">전화 **통신에서** 다음을 **Enterprise Voice.**</span><span class="sxs-lookup"><span data-stu-id="da5a7-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="da5a7-119">줄 **URI를** 클릭하고 고유한 정규화된 전화 번호(예: tel:+14255550200)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="da5a7-120">그런 다음 **커밋을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="da5a7-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="da5a7-121">사용자가 프레미스에서 사용할 수 있도록 설정하는 Enterprise Voice 고려 사항</span><span class="sxs-lookup"><span data-stu-id="da5a7-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="da5a7-122">경우에 따라 사용자가 전화를 걸고 받을 수 있도록 사용자를 Enterprise Voice 방법을 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="da5a7-123">배포에 다음 조건을 충족하는 사용자가 있는 경우 포함된 단계를 수행하여 사용자가 해당 작업을 수행할 수 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="da5a7-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="da5a7-124">사용자가 비즈니스용 Skype 또는 비즈니스용 Skype를 사용하도록 설정되지 않고 비즈니스용 Skype Online과 동기화된 후 Enterprise Voice LineURI가 설정되어 있지 않은 경우 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행하여 해당 환경의 값을 실제 값으로 바니다. \< \></span><span class="sxs-lookup"><span data-stu-id="da5a7-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="da5a7-125">사용자가 비즈니스용 Skype Online으로 이동하기 전에 이미 비즈니스용 Skype를 사용할 수 있지만 Enterprise Voice 사용하도록 설정되지 않은 경우 각 사용자에 대해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="da5a7-126">사용자가 이미 비즈니스용 Skype에서 사용하도록 설정되어 있지만 Enterprise Voice 사용하도록 설정되지 않은 경우 이미 LineURI가 할당된 경우에도 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="da5a7-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


