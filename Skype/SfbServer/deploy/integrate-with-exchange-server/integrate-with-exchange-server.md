---
title: Exchange Server와 비즈니스용 Skype 서버 통합
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: '요약: Exchange Server 2016 또는 Exchange Server 2013 및 비즈니스용 Skype 서버용 통합 단계를 검토 합니다.'
ms.openlocfilehash: ad8921c9c4c5c54809aa8323f60314dfc0826061
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791656"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="e585c-103">Exchange Server와 비즈니스용 Skype 서버 통합</span><span class="sxs-lookup"><span data-stu-id="e585c-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="e585c-104">**요약:** Exchange Server 2013 이상 및 비즈니스용 Skype Server의 통합 단계를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="e585c-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="e585c-105">Exchange Server 2013 이상 및 비즈니스용 Skype 서버는 호환 되 고 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e585c-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="e585c-106">예를 들어 비즈니스용 Skype 사용자 현재 상태 정보는 Microsoft Outlook에서 보고할 수 있습니다. 마찬가지로 비즈니스용 Skype는 사용자의 Outlook 일정에 액세스할 수 있으며, 사용자에 게 예정 된 모임이 있고 모임 중 사용자의 현재 상태를 사용 중으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e585c-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="e585c-107">비즈니스용 Skype 서버를 실행 하기 위해 Exchange Server를 실행할 필요는 없지만, 두 제품을 함께 사용 하는 경우에는 서로 다른 사용자의 경험을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e585c-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="e585c-108">이 설명서는 비즈니스용 Skype Server 및 2016 Exchange server 2013 통합에 대 한 정보를 제공 하지만, 이러한 두 제품의 초기 설정과 구성은 이미 발생 한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e585c-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="e585c-109">비즈니스용 Skype 서버를 배포 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 기술 센터](https://go.microsoft.com/fwlink/p/?LinkId=246127)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e585c-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="e585c-110">Exchange Server 배포에 대 한 자세한 내용은 해당 버전의 Exchange에 대 한 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e585c-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="e585c-111">비즈니스용 Skype Server의 온-프레미스 설치를 Microsoft Exchange Online과 통합 하는 경우 비즈니스용 [Skype server 및 Outlook Web App 간 통합 구성을](outlook-web-app.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e585c-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="e585c-112">비즈니스용 Skype Online과 Exchange Server 온-프레미스를 통합 하는 경우 비즈니스용 [Skype online 및 온-프레미스 간 OAuth 구성을](oauth-with-online-and-on-premises.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e585c-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e585c-113">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="e585c-113">In this section</span></span>

[<span data-ttu-id="e585c-114">비즈니스용 Skype 서버 및 Exchange Server에서 파트너 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="e585c-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="e585c-115">Exchange Server 아카이빙 사용을 위해 비즈니스용 Skype 서버 구성</span><span class="sxs-lookup"><span data-stu-id="e585c-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="e585c-116">보관된 비즈니스용 Skype 데이터를 검색하도록 SharePoint Server 구성</span><span class="sxs-lookup"><span data-stu-id="e585c-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="e585c-117">통합 연락처 저장소를 사용하도록 비즈니스용 Skype 서버 2015 구성</span><span class="sxs-lookup"><span data-stu-id="e585c-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="e585c-118">비즈니스용 Skype 서버에서 고해상도 사진 사용 구성</span><span class="sxs-lookup"><span data-stu-id="e585c-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="e585c-119">비즈니스용 Skype 서버 2015 음성 사서함에 대해 Exchange Server 2013 통합 메시징 구성</span><span class="sxs-lookup"><span data-stu-id="e585c-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="e585c-120">비즈니스용 Skype 서버 및 Microsoft Outlook Web App 2013 통합</span><span class="sxs-lookup"><span data-stu-id="e585c-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="e585c-121">비즈니스용 Skype Server 용 클라이언트 컴퓨터에서 개인 연락처 저장소 구성</span><span class="sxs-lookup"><span data-stu-id="e585c-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="e585c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e585c-122">See also</span></span>

[<span data-ttu-id="e585c-123">비즈니스용 Skype 및 Exchange 통합 계획</span><span class="sxs-lookup"><span data-stu-id="e585c-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
