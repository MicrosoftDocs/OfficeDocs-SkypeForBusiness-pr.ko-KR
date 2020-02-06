---
title: 비즈니스용 Skype 서버에서 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '요약: 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818519"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="190d5-103">비즈니스용 Skype 서버에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="190d5-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="190d5-104">**요약:** 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="190d5-105">사용자가 모임 요청에서 모임 링크를 클릭 하면 모임 참가 페이지에서 비즈니스용 Skype 클라이언트가 사용자의 컴퓨터에 이미 설치 되어 있는지 여부를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="190d5-106">클라이언트가 이미 설치 된 경우에는 클라이언트가 모임을 열고 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="190d5-107">클라이언트가 설치 되어 있지 않으면 기본적으로 비즈니스용 Skype 클라이언트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="190d5-108">모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="190d5-108">Configure the meeting join page</span></span>

<span data-ttu-id="190d5-109">사용자가 다른 버전의 클라이언트와 모임에 참가할 수 있도록 하려면 모임 참가 페이지의 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="190d5-110">이러한 구성 옵션은 비즈니스용 Skype Server 제어판에서 제거 되었지만 CsWebServiceConfiguration cmdlet을 사용 하 여 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="190d5-111">**모임 참가 페이지 집합-CsWebServiceConfiguration 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="190d5-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="190d5-112">**Set-CsWebServiceConfiguration 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="190d5-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="190d5-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="190d5-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="190d5-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="190d5-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="190d5-115">이 매개 변수는 비즈니스용 Skype Server 온-프레미스 버전에서 사용할 때 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="190d5-116">True로 설정 하면 비즈니스용 Skype 외의 클라이언트 응용 프로그램을 사용 하 여 모임에 참가 하는 사용자에 게 현재 클라이언트 응용 프로그램을 사용 하 여 모임에 참가할 수 있는 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="190d5-117">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="190d5-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="190d5-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="190d5-119">이 매개 변수는 비즈니스용 Skype Server 온-프레미스 버전에서 사용할 때 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="190d5-120">True로 설정 하면 온라인 회의에 참가 하는 대체 옵션이 자동으로 확장 되어 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="190d5-121">False (기본값)로 설정 하는 경우 이러한 옵션을 사용할 수 있지만, 사용자는 자신의 옵션 목록을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="190d5-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

