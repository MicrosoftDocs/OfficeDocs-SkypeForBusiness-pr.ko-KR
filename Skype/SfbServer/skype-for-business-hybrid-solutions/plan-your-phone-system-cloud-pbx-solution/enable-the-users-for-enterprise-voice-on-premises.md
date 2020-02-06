---
title: 온-프레미스 Enterprise Voice 사용자 설정
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
description: 사용자가 Office 365 (클라우드 PBX)에서 전화 시스템을 사용 하는 경우 먼저 엔터프라이즈 음성에 대해 사용 하도록 설정 하 고 전화 번호를 할당 해야 합니다. 사용자가 온-프레미스 배포에 남아 있는 동안 온-프레미스 배포를 사용 하 여이 작업을 수행 합니다.
ms.openlocfilehash: 4409de1965fbcca641dde69d70c734d1bcd3a8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802298"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="13984-104">온-프레미스 Enterprise Voice 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="13984-104">Enable the users for Enterprise Voice on premises</span></span>
 
<span data-ttu-id="13984-105">사용자가 Office 365 (클라우드 PBX)에서 전화 시스템을 사용 하는 경우 먼저 엔터프라이즈 음성에 대해 사용 하도록 설정 하 고 전화 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-105">For a user to use Phone System in Office 365 (Cloud PBX), you must first enable them for Enterprise Voice and assign them a phone number.</span></span> <span data-ttu-id="13984-106">사용자가 온-프레미스 배포에 남아 있는 동안 온-프레미스 배포를 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-106">You do this using your on-premises deployment while the user is still homed in the on-premises deployment.</span></span>
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a><span data-ttu-id="13984-107">사용자가 온-프레미스 Enterprise Voice를 사용 하도록 설정 하 고 전화 번호를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="13984-107">To enable a user for Enterprise Voice on premises and assign a phone number</span></span>

1. <span data-ttu-id="13984-108">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="13984-109">시작 메뉴 또는 바탕 화면 바로 가기를 사용 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="13984-109">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="13984-110">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype Server 제어판을 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13984-110">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="13984-111">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-111">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="13984-112">**사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-112">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="13984-113">표에서 Enterprise Voice에 사용할 비즈니스용 Skype Online 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-113">In the table, click the Skype for Business Online user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="13984-114">**편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-114">On the **Edit** menu, click **Show Details**.</span></span>
    
7. <span data-ttu-id="13984-115">**전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-115">Under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="13984-116">**줄 URI**를 클릭 하 고 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="13984-116">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="13984-117">그런 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-117">Then click **Commit**.</span></span>
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a><span data-ttu-id="13984-118">온-프레미스에서 엔터프라이즈 음성을 사용할 때의 특별 고려 사항</span><span class="sxs-lookup"><span data-stu-id="13984-118">Special considerations when enabling users for Enterprise Voice on premises</span></span>

<span data-ttu-id="13984-119">경우에 따라 엔터프라이즈 음성에 대 한 사용자가 전화를 걸고 받을 수 있도록 하는 방법을 수정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13984-119">In some cases, you may need to modify the way you enable users for Enterprise Voice to make sure that they can successfully make and receive calls.</span></span> <span data-ttu-id="13984-120">배포에 다음 조건을 충족 하는 사용자가 있는 경우 엔터프라이즈 음성에 대 한 사용자를 사용 하도록 설정 된 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-120">If you have users in your deployment that meet the following conditions, perform the steps included to enable the user for Enterprise Voice.</span></span>
  
- <span data-ttu-id="13984-121">온-프레미스 광고에서 사용자를 만든 다음 비즈니스용 skype 또는 엔터프라이즈 음성에 대해 사용 하도록 설정 하지 않고 비즈니스용 skype Online과 동기화 하는 경우, 각 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행 하 여 환경의 값 \< \> 을 실제 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="13984-121">If a user is created in your on-premises AD and then synchronized with Skype for Business Online without being enabled for Skype for Business or for Enterprise Voice and do not have a LineURI set, run the following cmdlets for each affected user, replacing the values in \< \> with actual values for your environment:</span></span>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="13984-122">사용자가 온-프레미스 비즈니스용 Skype를 이미 사용 하도록 설정 되어 있지만 Enterprise Voice에 대해 사용 하도록 설정 되지 않았거나, 비즈니스용 Skype Online으로 이동 하기 전에 LineURI를 할당 하지 않은 경우 각 사용자에 대해 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-122">If a user is already enabled for Skype for Business on premises, but was not enabled for Enterprise Voice or assigned a LineURI before being moved to Skype for Business Online, run the following cmdlet for each user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- <span data-ttu-id="13984-123">온-프레미스 비즈니스용 Skype에서 사용자를 이미 사용 하도록 설정 했지만 Enterprise Voice에서 사용할 수 없는 경우에도 해당 사용자에 대해 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13984-123">If a user is already enabled in Skype for Business on premises but not enabled for Enterprise Voice, even if already assigned a LineURI, run the following cmdlet for each affected user:</span></span>
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


