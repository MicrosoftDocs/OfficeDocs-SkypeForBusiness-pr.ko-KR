---
title: 비즈니스용 Skype 서버에서 모임 참가 페이지 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '요약: 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성하는 방법을 알아보십시오.'
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828038"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="a6d78-103">비즈니스용 Skype 서버에서 모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="a6d78-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="a6d78-104">**요약:** 비즈니스용 Skype 서버에서 모임 참가 페이지를 구성하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="a6d78-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="a6d78-105">사용자가 모임 요청에서 모임 링크를 클릭하면 모임 참가 페이지에서 비즈니스용 Skype 클라이언트가 사용자 컴퓨터에 이미 설치되어 있는지 여부를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="a6d78-106">클라이언트가 이미 설치된 경우 클라이언트가 열리고 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="a6d78-107">클라이언트가 설치되어 있지 않은 경우 기본적으로 비즈니스용 Skype 클라이언트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="a6d78-108">모임 참가 페이지 구성</span><span class="sxs-lookup"><span data-stu-id="a6d78-108">Configure the meeting join page</span></span>

<span data-ttu-id="a6d78-109">사용자가 다른 버전의 클라이언트와 모임에 참가하도록 허용하려는 경우 모임 참가 페이지의 동작을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="a6d78-110">이러한 구성 옵션은 비즈니스용 Skype 서버 제어판에서 제거했지만 이 cmdlet을 사용하여 Set-CsWebServiceConfiguration 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="a6d78-111">**모임 참가 페이지 Set-CsWebServiceConfiguration 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="a6d78-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="a6d78-112">**Set-CsWebServiceConfiguration 매개 변수**</span><span class="sxs-lookup"><span data-stu-id="a6d78-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="a6d78-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="a6d78-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6d78-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="a6d78-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="a6d78-115">이 매개 변수는 비즈니스용 Skype 서버의 On-프레미스 버전에서 더는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="a6d78-116">True로 설정하면 비즈니스용 Skype가 다른 클라이언트 응용 프로그램을 사용하여 모임에 참가하는 사용자에게 현재 클라이언트 응용 프로그램을 사용하여 모임에 참가할 수 있는 기회가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="a6d78-117">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="a6d78-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="a6d78-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="a6d78-119">이 매개 변수는 비즈니스용 Skype 서버의 On-프레미스 버전에서 더는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="a6d78-120">True로 설정하면 온라인 회의 참가를 위한 대체 옵션이 자동으로 확장되어 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="a6d78-121">False(기본값)로 설정하면 이러한 옵션을 사용할 수 있지만 사용자가 직접 옵션 목록을 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d78-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

