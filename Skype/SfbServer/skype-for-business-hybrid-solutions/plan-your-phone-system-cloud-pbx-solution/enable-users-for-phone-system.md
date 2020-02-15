---
title: 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하는 Office 365에서 사용자가 전화 시스템을 사용할 수 있도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
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
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 이 항목에서는 온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템용 사용자를 설정 하는 방법에 대해 설명 합니다. 이 항목의 단계를 수행 하기 전에 다음을 읽어야 합니다.
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050190"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="11510-104">비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하는 Office 365에서 사용자가 전화 시스템을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="11510-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="11510-105">이 항목에서는 온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템용 사용자를 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="11510-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="11510-106">이 항목의 단계를 수행 하기 전에 다음을 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11510-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="11510-107">하이브리드 연결을 설정 하는 방법에 대 한 자세한 내용은 비즈니스용 skype [서버 및 비즈니스용 Skype online의 하이브리드 연결 계획](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) 및 비즈니스용 skype [서버 및 비즈니스용 skype online 간 하이브리드 연결 배포](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11510-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="11510-108">배포 계획에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용 하는 Office 365의 전화 시스템 계획](plan-phone-system-with-on-premises-pstn-connectivity.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="11510-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="11510-109">라이선스 및 요금제를 포함 하 여 Office 365에서 전화 시스템에 대 한 자세한 내용은 [비즈니스용 Skype에 대 한 PSTN 통화 요금제](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="11510-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="11510-110">온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="11510-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="11510-111">사용자를 비즈니스용 Skype Online으로 이동 하기 전에 비즈니스용 Skype 서버 또는 Lync Server 2013에서 온-프레미스 사용자를 사용 하도록 설정한 다음 온라인으로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="11510-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="11510-112">자세한 내용은 [비즈니스용 Skype 서버 및 비즈니스용 Skype Online의 하이브리드 연결 계획](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) 및 사용자가 온-프레미스에서 [Enterprise Voice For 프레미스를 사용 하도록 설정](enable-the-users-for-enterprise-voice-on-premises.md) 의 특수 고려 사항 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="11510-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="11510-113">모든 사용자는 온-프레미스 Active Directory에 만들어져 지원 되는 Azure AD Connector 버전을 사용 하 여 Office 365로 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11510-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="11510-114">Azure AD에서 직접 만든 Office 365에서 전화 시스템에 대 한 사용자를 사용 하도록 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11510-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="11510-115">Azure AD에서 만든 사용자에 대해 온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템을 사용 하도록 설정 하려면 온-프레미스 AD에서 해당 사용자에 대 한 새 계정을 만들고, 온-프레미스에 계정을 구성한 다음, 계정을 사용 하 여 동기화 해야 합니다. 지원 되는 버전의 Azure AD Connector 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="11510-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="11510-116">온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템용 사용자를 설정한 다음이를 비즈니스용 Skype Online으로 이동 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11510-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="11510-117">사용자가 온-프레미스에서 [Enterprise Voice를 사용 하도록 설정](enable-the-users-for-enterprise-voice-on-premises.md) 합니다 (사용자가 내부에 있는 동안 수행 됨).</span><span class="sxs-lookup"><span data-stu-id="11510-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="11510-118">[음성 라우팅 정책 할당](assign-a-voice-routing-policy.md) (사용자가 온-프레미스에 있는 동안 수행 됨)</span><span class="sxs-lookup"><span data-stu-id="11510-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="11510-119">[사용자를 클라우드와 동기화 하 고 라이선스](synchronize-users-to-the-cloud-and-assign-licenses.md) (Office 365을 사용 하 여 수행)를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="11510-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="11510-120">온 [-프레미스 사용자를 비즈니스용 Skype Online으로 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) 합니다 (Windows PowerShell 온-프레미스를 사용 하지만 Office 365 관리자 자격 증명 사용).</span><span class="sxs-lookup"><span data-stu-id="11510-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="11510-121">Office 365 음성 메일 (원격 PowerShell을 사용 하 여 수행) [에서 Enterprise Voice online 및 전화 시스템에 대해 사용자를 사용 하도록 설정](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="11510-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

