---
title: 비즈니스용 Skype 서버용 Exchange 저장소와의 통합 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: '요약: 비즈니스용 Skype 서버에서 Exchange 저장소와의 통합을 구성하는 방법을 알아보는 이 항목을 참조하세요.'
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825068"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="22869-103">비즈니스용 Skype 서버용 Exchange 저장소와의 통합 구성</span><span class="sxs-lookup"><span data-stu-id="22869-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="22869-104">**요약:** 이 항목을 읽고 비즈니스용 Skype 서버에서 Exchange 저장소와의 통합을 구성하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="22869-105">배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용하는 경우 사용자에 대해 비즈니스용 Skype 서버 보관 정책을 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22869-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="22869-106">대신 사서함이 보류된 In-Place Exchange에 있는 사용자에 대한 보관을 지원하도록 Exchange In-Place 보류 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="22869-107">Exchange 저장소와의 통합을 구성하기 전에 비즈니스용 Skype 서버에서 보관 계획을 [읽어야 합니다.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="22869-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="22869-108">Exchange In-Place 보류 정책에 대한 자세한 내용은 Exchange 제품 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="22869-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="22869-109">Microsoft Exchange 저장소와의 통합 구성</span><span class="sxs-lookup"><span data-stu-id="22869-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="22869-110">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="22869-111">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="22869-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="22869-112">왼쪽 탐색 모음에서 **모니터링 및 보관** 을 클릭하고 **보관 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="22869-113">보관 구성 목록에서 적합한 전역, 사이트 또는 풀 구성 이름을 클릭하고 **편집**, **자세한 정보 표시** 를 차례로 클릭한 후 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="22869-114">Exchange 저장소와의 통합을 사용하도록 설정하려면 **Microsoft Exchange 통합** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="22869-115">Exchange 저장소와의 통합을 사용하지 않도록 설정하기 위해 Microsoft Exchange 통합 확인란의 **선택을** 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="22869-116">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="22869-117">비즈니스용 Skype 서버 및 Microsoft Exchange가 다른 포리스트에 배포되는 경우</span><span class="sxs-lookup"><span data-stu-id="22869-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="22869-118">Microsoft Exchange 통합을 사용하고 Microsoft Exchange Server 비즈니스용 Skype 서버와 동일한 포리스트에 배포되지 않은 경우 다음 Exchange Active Directory 특성이 비즈니스용 Skype 서버가 배포된 포리스트와 동기화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="22869-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="22869-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="22869-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="22869-120">proxyAddresses</span></span>
    
<span data-ttu-id="22869-p102">이 특성은 다중 값 특성입니다. 이 특성을 동기화할 때는 기존 값이 손실되지 않도록 값을 대체하지 않고 병합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22869-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  

