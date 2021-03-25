---
title: 사용자가 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하는 전화 시스템을 사용하도록 설정
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
description: 이 항목에서는 사용자가 전화 시스템을 사용할 수 있도록 설정하는 방법에 대해 설명하고 있습니다. 이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다. .
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120870"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="8537e-104">사용자가 비즈니스용 Skype 서버에서 온-프레미스 PSTN 연결을 사용하는 전화 시스템을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="8537e-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="8537e-105">이 항목에서는 사용자가 전화 시스템을 사용할 수 있도록 설정하는 방법에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="8537e-106">이 항목의 단계를 수행하기 전에 다음을 읽어야 합니다. .</span><span class="sxs-lookup"><span data-stu-id="8537e-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="8537e-107">하이브리드 연결을 설정하는 방법에 대한 자세한 내용은 [비즈니스용 Skype](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 서버와 비즈니스용 Skype Online 간의 하이브리드 연결 계획 및 비즈니스용 Skype 서버와 비즈니스용 Skype Online 간에 하이브리드 연결 [배포를 참조하세요.](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="8537e-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
    
- <span data-ttu-id="8537e-108">배포 계획에 대한 자세한 내용은 [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server을 참조하세요.](plan-phone-system-with-on-premises-pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="8537e-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="8537e-109">라이선싱 및 요금제 등 전화 시스템에 대한 자세한 내용은 [PSTN Calling plans for Skype for Business을 참조하세요.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)</span><span class="sxs-lookup"><span data-stu-id="8537e-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="8537e-110">비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="8537e-111">또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="8537e-112">직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="8537e-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="8537e-113">사용자를 전화 시스템으로 이동(프레미스 PSTN 연결로)</span><span class="sxs-lookup"><span data-stu-id="8537e-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="8537e-114">사용자를 비즈니스용 Skype Online으로 이동하기 전에 사용자를 비즈니스용 Skype 서버 또는 Lync Server 2013에서 온-프레미스로 사용하도록 설정한 다음 온라인으로 이동하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="8537e-115">자세한 내용은 [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 및 Enable the users for Enterprise Voice for Enterprise Voice on-premises (performed while the users are home-premises) 섹션을 참조하십시오. [](enable-the-users-for-enterprise-voice-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="8537e-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="8537e-116">모든 사용자는 Active Directory의 모든 사용자를 프레미스에서 만들어야 합니다. 지원되는 버전의 Azure AD 커넥터를 사용하여 Microsoft 365 또는 Office 365에 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="8537e-117">Azure AD에서 직접 만든 Office 365에서 전화 시스템을 사용하도록 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="8537e-118">Azure AD에서 만든 사용자에 대해 사내 PSTN 연결을 사용하여 전화 시스템을 사용하도록 설정하려면, 해당 사용자에 대해 새 계정을 만들고, 해당 계정을 사내에서 구성한 다음, 지원되는 버전의 Azure AD 커넥터 도구를 사용하여 계정을 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="8537e-119">사용자가 온라인 PSTN 연결을 통해 전화 시스템을 사용하도록 설정한 다음 비즈니스용 Skype Online으로 이동하려면 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="8537e-120">[사용자가 Enterprise Voice(사용자가](enable-the-users-for-enterprise-voice-on-premises.md) 홈으로 있는 동안 수행)에 대해 사용자를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8537e-121">음성 라우팅 정책을 [할당합니다(사용자가](assign-a-voice-routing-policy.md) 사내에 있는 동안 수행).</span><span class="sxs-lookup"><span data-stu-id="8537e-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8537e-122">[사용자를 클라우드에 동기화하고 라이선스를](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) 할당합니다(Office 365를 사용하여 수행).</span><span class="sxs-lookup"><span data-stu-id="8537e-122">[Synchronize users to the cloud and assign licenses](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (performed using Office 365).</span></span>
    
- <span data-ttu-id="8537e-123">[비즈니스용 Skype Online으로](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) 사내 사용자를 이동(Windows PowerShell Office 365 관리자 자격 증명을 사용하여 수행)</span><span class="sxs-lookup"><span data-stu-id="8537e-123">[Move on-premises users to Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="8537e-124">[사용자가 온라인 및 Enterprise Voice 시스템](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) 음성메일(원격 PowerShell을 사용하여 수행)을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8537e-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
