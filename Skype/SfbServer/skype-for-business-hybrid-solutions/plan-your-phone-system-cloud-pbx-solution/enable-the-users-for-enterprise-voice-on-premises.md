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
description: 사용자가 전화 시스템(클라우드 PBX)을 사용하려면 먼저 해당 사용자를 사용하도록 설정하고 Enterprise Voice 번호를 할당해야 합니다. 사용자가 여전히 사내 배포에 있는 동안에는 이 작업을 위해 사내 배포를 사용할 수 있습니다.
ms.openlocfilehash: b26e51ba316c63e0f992b843a7763586d7e9b575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098594"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="f71ea-104">사용자가 프레미스에서 Enterprise Voice 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="f71ea-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="f71ea-105">사용자가 전화 시스템(클라우드 PBX)을 사용하려면 먼저 해당 사용자를 사용하도록 설정하고 Enterprise Voice 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="f71ea-106">사용자가 여전히 사내 배포에 있는 동안에는 이 작업을 위해 사내 배포를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="f71ea-107">비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="f71ea-108">또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="f71ea-109">직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="f71ea-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="f71ea-110">사용자가 프레미스에서 Enterprise Voice 번호를 할당할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="f71ea-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="f71ea-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f71ea-112">시작 메뉴 또는 데스크톱 바로 가기를 사용하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="f71ea-113">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f71ea-114">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f71ea-115">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="f71ea-116">표에서 비즈니스용 Skype Online 사용자 계정을 클릭하여 비즈니스용 Skype를 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f71ea-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="f71ea-117">편집 **메뉴에서** 자세한 정보 **표시를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f71ea-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="f71ea-118">전화 **통신에서** 에서 를 **Enterprise Voice.**</span><span class="sxs-lookup"><span data-stu-id="f71ea-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="f71ea-119">줄 **URI를 클릭하고** 고유한 정규화된 전화 번호(예: tel:+14255550200)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="f71ea-120">그런 다음 **커밋을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f71ea-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="f71ea-121">사용자가 Enterprise Voice 때의 특별한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f71ea-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="f71ea-122">경우에 따라 사용자가 전화를 걸고 받을 수 있도록 사용자를 Enterprise Voice 방법을 수정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="f71ea-123">배포에 다음 조건을 충족하는 사용자가 있는 경우 사용자가 다음 조건을 충족할 수 있도록 하는 단계를 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f71ea-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="f71ea-124">사용자가 비즈니스용 Skype 또는 비즈니스용 Skype를 사용하도록 설정되지 않고 비즈니스용 Skype Online과 동기화된 후Enterprise Voice LineURI 집합이 없는 경우 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행하여 해당 환경의 값을 실제 값으로 \< \> 바니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="f71ea-125">사용자가 비즈니스용 Skype Online으로 이동하기 전에 이미 비즈니스용 Skype를 사용할 수 있지만 Enterprise Voice 사용할 수 없는 경우 각 사용자에 대해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="f71ea-126">사용자가 이미 비즈니스용 Skype on premises에서 사용하도록 설정되어 있지만 Enterprise Voice LineURI가 이미 할당된 경우에도 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f71ea-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```