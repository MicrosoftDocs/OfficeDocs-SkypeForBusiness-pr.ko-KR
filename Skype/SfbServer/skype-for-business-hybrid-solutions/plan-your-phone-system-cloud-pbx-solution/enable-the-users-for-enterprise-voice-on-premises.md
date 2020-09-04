---
title: 사용자가 온-프레미스 Enterprise Voice를 사용 하도록 설정
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
description: 전화 시스템 (클라우드 PBX)을 사용 하는 사용자는 먼저 Enterprise Voice에 대해이를 사용 하도록 설정 하 고 전화 번호를 할당 해야 합니다. 이 작업은 온-프레미스 배포를 사용 하 고 사용자가 온-프레미스 배포에 여전히 속해 있는 동안에는 수행 해야 합니다.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359194"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="20b6d-104">사용자가 온-프레미스 Enterprise Voice를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="20b6d-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="20b6d-105">전화 시스템 (클라우드 PBX)을 사용 하는 사용자는 먼저 Enterprise Voice에 대해이를 사용 하도록 설정 하 고 전화 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-105">For a user to use Phone System (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="20b6d-106">이 작업은 온-프레미스 배포를 사용 하 고 사용자가 온-프레미스 배포에 여전히 속해 있는 동안에는 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>

> [!Important]
> <span data-ttu-id="20b6d-107">비즈니스용 Skype Online은 서비스에 더 이상 액세스할 수 없게 되 고, 2021 년 7 월 31 일에 만료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-107">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="20b6d-108">또한 비즈니스용 Skype 서버 또는 클라우드 Connector Edition과 비즈니스용 Skype Online을 통해 온-프레미스 환경 간의 PSTN 연결이 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-108">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="20b6d-109">[직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-109">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="20b6d-110">사용자에 게 Enterprise Voice 온-프레미스를 사용 하도록 설정 하 고 전화 번호를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="20b6d-110">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="20b6d-111">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="20b6d-112">시작 메뉴 또는 바탕 화면 바로 가기를 사용 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-112">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="20b6d-113">브라우저 창을 연 다음 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-113">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="20b6d-114">왼쪽 탐색 모음에서 **사용자**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="20b6d-115">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="20b6d-116">표에서 Enterprise Voice를 사용 하도록 설정 하려는 비즈니스용 Skype Online 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-116">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="20b6d-117">**편집** 메뉴에서 **자세한 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-117">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="20b6d-118">**전화 통신**아래에서 **Enterprise Voice**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-118">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="20b6d-119">**줄 URI**를 클릭 하 고 정규화 된 고유 전화 번호를 입력 합니다 (예: tel-+ 14255550200).</span><span class="sxs-lookup"><span data-stu-id="20b6d-119">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="20b6d-120">그런 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-120">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="20b6d-121">온-프레미스에서 Enterprise Voice를 사용 하도록 설정할 때 특별히 고려할 사항</span><span class="sxs-lookup"><span data-stu-id="20b6d-121">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="20b6d-122">경우에 따라 엔터프라이즈 음성에 대 한 사용자가 전화를 걸고 받을 수 있도록 하는 방법을 수정 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-122">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="20b6d-123">배포에 다음 조건을 충족 하는 사용자가 있는 경우에는 포함 된 단계를 수행 하 여 Enterprise Voice에 대해 사용자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-123">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="20b6d-124">온-프레미스 AD에 사용자를 만든 후 비즈니스용 Skype 또는 Enterprise Voice를 사용 하도록 설정 하지 않고 비즈니스용 Skype Online과 동기화 하 고 LineURI를 설정 하지 않은 경우에는 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행 하 여 해당 값을 \< \> 환경의 실제 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-124">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="20b6d-125">온-프레미스 비즈니스용 Skype를 이미 사용 하도록 설정 했지만 비즈니스용 Skype Online으로 이동 하기 전에 LineURI를 할당 하지 않은 경우 각 사용자에 대해 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-125">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="20b6d-126">온-프레미스 비즈니스용 Skype에서 사용자가 이미 사용 하도록 설정 되어 있으 나 Enterprise Voice를 사용 하도록 설정 되지 않은 경우에도 해당 하는 각 사용자에 대해 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b6d-126">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


