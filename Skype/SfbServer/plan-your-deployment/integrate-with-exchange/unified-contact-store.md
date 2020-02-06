---
title: 비즈니스용 Skype 서버에서 통합 된 연락처 저장소에 대 한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '요약: 비즈니스용 Skype 서버를 Exchange 2013와 통합할 계획을 진행 하는 동안이 항목을 검토 하세요.'
ms.openlocfilehash: fbc361dab4414ea2add286144be48b922a9d9247
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815876"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="c7dc1-103">비즈니스용 Skype 서버의 통합 연락처 저장소 계획</span><span class="sxs-lookup"><span data-stu-id="c7dc1-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c7dc1-104">**요약:** 비즈니스용 Skype 서버와 Exchange 2013 또는 2016을 통합 하기 위해 계획 하는 동안이 항목을 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="c7dc1-105">통합 된 대화 상대 저장소는 모든 Microsoft Office 제품에서 일관적인 연락처 환경을 제공 하 고, 사용자가 Exchange 2013에 모든 연락처 정보를 저장할 수 있도록 하 고, 비즈니스용 Skype, Exchange, Outlook에서 전체적으로 정보를 사용할 수 있도록 합니다. 및 Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="c7dc1-106">통합 연락처 저장소 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7dc1-106">Requirements for unified contact store</span></span>

<span data-ttu-id="c7dc1-107">비즈니스용 Skype 서버에서 통합 된 연락처 저장소를 구현 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="c7dc1-108">비즈니스용 Skype 서버 및 Exchange 2013 또는 2016을 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="c7dc1-109">Skype for Business Server에서 Exchange 2013 또는 2016으로 연락처를 마이그레이션하려면 사용자는 비즈니스용 Skype를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="c7dc1-110">사용자 사서함은 Exchange 2013으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="c7dc1-111">비즈니스용 Skype Server와 Exchange 2013 또는 2016 간에 서버 간 인증이 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c7dc1-112">비즈니스용 Skype 서버와 Exchange 2013 또는 2016 간의 인증 설정에 대 한 자세한 요구 사항은 운영 설명서의 비즈니스용 [Skype 서버에서 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리](../../manage/authentication/server-to-server-and-partner-applications.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7dc1-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7dc1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7dc1-113">See also</span></span>

[<span data-ttu-id="c7dc1-114">비즈니스용 Skype 서버에서 통합 된 연락처 저장소 배포</span><span class="sxs-lookup"><span data-stu-id="c7dc1-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)
